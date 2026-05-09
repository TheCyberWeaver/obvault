Haskell 提供了一系列类型类（如 Functor、Applicative、Monad、Category 等）直接对应或源自范畴论的重要概念。这些抽象不仅有助于代码复用和模块化，更体现了深刻的数学含义。下面我们逐一解释这些类型类与范畴论概念的对应关系，并结合简单的代码实例来加深理解。

# Functor 类型类（函子）

在范畴论中，**函子**是在两个范畴之间映射结构的映射：它将一个范畴中的每个对象映射到另一个范畴中的一个对象，同时将态射映射为态射，并且保持恒等态射和组合运算。特别地，**自函子**是映射范畴到自身的函子。Haskell 中的 `Functor` 类型类正是范畴 **Hask** 上的自函子概念。`Functor` 类型类定义如下：


```haskell
class Functor f where
	fmap :: (a -> b) -> f a -> f b
```

该定义表明：`f` 是一个类型构造器（`* -> *` _kinding_）时，它是一个函子，需要提供 `fmap` 来把**源范畴 Hask**中的态射`(a->b)`映射为**目标范畴（也是 Hask）** 中的态射`(f a -> f b)`。这里类型构造器 `f` 扮演函子在对象上的映射：给定任意类型 `a`，它产生一个新类型 `f a`；而 `fmap` 则对应将任意函数 `a->b` 映射为 `f a->f b`。必须满足函子公理：`fmap id = id`（映射恒等函数得到恒等函数）以及 `fmap (g . h) = fmap g . fmap h`（映射复合函数等于依次映射后再复合）。这些正是函子保持范畴结构（单位元和组合）的要求。

一个典型例子是 `Maybe` 类型构造器，它可以视为 Hask 上的一个自函子。`Maybe` 将任意类型 `T` 对应到类型 `Maybe T`，同时我们为其定义 `fmap` 来映射函数en.wikibooks.org：

```haskell
instance Functor Maybe where
 fmap f (Just x) = Just (f x)
 fmap _ Nothing = Nothing
```

在此实例中，`fmap` 接受一个函数 `f :: a -> b`，如果 `Maybe` 值是 `Just x`，则将其内部值应用 `f` 后包裹回 `Just`；如果是 `Nothing`，则仍返回 `Nothing`。这样，`fmap` 实现了从 `a->b` 到 `Maybe a->Maybe b` 的映射，恰好满足函子的定义要求。使用示例：`fmap (+1) (Just 2)` 结果为 `Just 3`，而 `fmap (+1) Nothing` 则仍为 `Nothing`。`Functor` 抽象使我们能够编写与具体容器无关的**可映射**操作，例如可以定义一个多态函数通过 `fmap` 对任意 Functor 作用，从而同时适用于列表、`Maybe`、树等各种函子结构。

值得注意的是，Haskell 中的 `Data.Functor` 模块正是定义在 **Hask** 上的自函子类型类。正如以上所示，对于具体的 Functor 实例，**对象映射**由类型构造器本身完成（比如 `Maybe`），而**态射映射**由 `fmap` 完成。函子这一抽象源自范畴论，但在日常 Haskell 编程中非常常用，为各种数据结构提供了一种统一的“可映射”接口。

---
# Applicative 类型类（内积函子/单元函子）

**Applicative** 是 Functor 的增强，它在函子的基础上增加了“将带有上下文的函数应用于带有上下文的值”的能力。Applicative 类型类定义如下：

```haskell
class Functor f => Applicative f where
 pure :: a -> f a
 (<*>) :: f (a -> b) -> f a -> f b
```

`pure` 将一个普通值放入函子的上下文中（例如将值包装到 `Just`中或单元素列表中），`<*>` 则将函子内包含的函数作用于另一个函子内的值[thzt.github.io](https://thzt.github.io/2016/01/11/monad-in-hask-category/#:~:text=fmap%20%3A%3A%20%28a%20,f%20b)。Applicative 要求满足若干公理（如同态性、交换性等），确保其行为与直观的函数应用一致。

从范畴论角度来看，Applicative 对应了**单元（幺）函子和范畴乘积**的概念。具体而言，Applicative 函子等价于在笛卡尔积单元范畴上**具有张量态射的**（强）** 挠性幺半函子。这意味着 Applicative 函子不仅是一个自函子，还与底层范畴的乘积结构相容：`pure` 对应将恒等元映射到函子（类似恒等函子的自然变换），`<*>` 则对应函子在乘积上的一种映射，使得 `f (a⊗b) -> f a ⊗ f b` 形式的转换成为可能。简单来说，在 Hask （一个以笛卡尔积为张量的幺半范畴）中，Applicative 函子允许我们在独立计算的结果之间进行组合操作，这在数学上对应函子保持该范畴的**单元结构**。

举例来说，列表 `[]` 构造器是一个 Applicative Functor：`pure x` 产生单元素列表 `[x]`，而 `<*>` 实现笛卡尔积式的组合，例如：

```haskell
pure (+) <*> [1,2] <*> [10,20] -- 结果为 [11,21,12,22]
```

这里 `[1,2]` 和 `[10,20]` 两个列表的组合产生了所有可能的和。同样地，`Maybe` 也是 Applicative：`pure x = Just x`，而 `<*>` 会在任一参数为 `Nothing` 时产出 `Nothing`，否则就应用内部函数。例如：

```haskell
pure (+) <*> Just 3 <*> Just 4 -- 结果为 Just 7
pure (+) <*> Nothing <*> Just 4 -- 结果为 Nothing
```

在这些操作中，可以看出 Applicative 允许我们对多个带有上下文的值进行运算，而无需显式地拆解上下文，从而提供了一种简洁的方式组合独立的效果或计算。

---
# Monad 类型类（单子）

**Monad** 可以看作是带有额外结构的 Applicative（当然也是 Functor）。范畴论中，单子（Monad）起源于对**范畴的自函子上的幺半群**结构的研究：用精练的话来说：

> _“Monad 是范畴 C 上的自函子范畴中的一个幺半群。”

简单解释即：给定范畴 C，考虑所有从 C 到 C 的函子所构成的范畴（对象是这些自函子，态射是函子之间的自然变换）。在这个函子范畴中可以定义函子的复合作为“乘法”，恒等函子作为“单位”。满足单子公理的函子就对应于其中的**幺半群（Monoid）对象**。对于 Hask 来说，单子就是**在 Hask 自函子范畴中的幺半群**，其中函子的复合`F ◦ F`对应 monoid 的“乘法”，恒等函子对应“单位元”。这正是常被引用的定义：“**Monad 就是 Endofunctor（自函子）范畴上的幺半群**”。

Haskell 中 Monad 类型类的定义为：

```haskell
class Applicative m => Monad m where
 return :: a -> m a
 (>>=) :: m a -> (a -> m b) -> m b
```

其中 `return` （在 Haskell 2010 标准中使用，后来的版本中已将同义的 `pure` 视作更可取的名称）将普通值放入单子的上下文中，`>>=`（bind）则把一个**包含上下文的值**与一个**会产出该上下文的函数**组合，产生新的上下文值。如果我们定义 `join :: m (m a) -> m a` 来直接“消除”一层上下文，那么 `m >>= f` 实质上等价于 `join (fmap f m)`，即先用 `f` 映射再扁平化。因此，可以将 `return` 对应单子中的单位自然变换 η，将 `join` 对应结合自然变换 μ。Monad 需要遵循三条定律（左单位、右单位和结合律），对应范畴论中幺半群的单位元和结合律公理：

- **左单位**：`return a >>= k ≡ k a` （将纯值引入单子再绑定，等同于直接应用函数）
 
- **右单位**：`m >>= return ≡ m` （将单子值绑定到 return，不改变原值）
 
- **结合律**：`(m >>= k) >>= h ≡ m >>= (\x -> k x >>= h)` （连续两次绑定的先后顺序不影响结果）
 

在范畴论语言中，上述定律正对应 `η` 和 `μ` 满足 monoid 的单位元和结合律性质。这样，Monad 可以被视为在**计算上下文**中**串联运算**的抽象模型。

实践中，Monad 是 Haskell 里极为重要的概念，用于抽象各种带有**序列化效果**的计算。例如，`Maybe` Monad 表示可能失败的计算，`IO` Monad 表示带有输入输出副作用的计算，`[]` Monad 表示非确定性计算（列表推导）等。以下是一个使用 `Maybe` Monad 的简单示例，利用 **do 表达式**（语法糖）来串联多步计算：

```haskell
safeDivide :: Double -> Double -> Maybe Double
safeDivide _ 0 = Nothing
safeDivide x y = Just (x / y)

calc :: Double -> Double -> Double -> Maybe Double
calc x y z = do
 r1 <- safeDivide x y -- x/y，可能失败
 r2 <- safeDivide r1 z -- (x/y)/z，可能失败
 return r2 -- 将结果包装回 Maybe
```
在上述代码中，如果任意一步产生 `Nothing`（如除以零失败），整个计算就短路返回 `Nothing`；否则会依次将结果传递下去，最终得到 `Just` 包裹的结果。这正体现了 Monad 的作用：通过 `>>=` 隐藏了显式的判错或状态传递逻辑，以**可组合**的方式把计算步骤串联起来。用范畴论的话说，每个类型构造器 `m` 的 Monad 实例确立了一个 **Kleisli 范畴**：对象仍是类型，但态射不再是普通函数 `a->b`，而是形如 `a -> m b` 的**单子函数**；Kleisli 范畴中的态射组合就是通过 `>>=`（或 `>=>`）来实现。事实上，Haskell 提供了 `Control.Category` 中对 Kleisli 的 `Category` 实例，可以将 Monad 看作生成了一个**新范畴**，其中范畴的合成即 Monad bind。比如，对于任意 Monad `m`，Kleisli 范畴的恒等态射是 `return :: a -> m a`，两个 Kleisli 态射 `f :: a -> m b` 和 `g :: b -> m c` 的组合是 `\x -> f x >>= g`。这再次印证了“单子是自函子范畴上的幺半群”这一说法：`return` 提供单位（单位态射），`>>=` 提供了类似“乘法”的组合操作，它们满足与范畴恒等和复合相同的规则，从而在抽象上扮演了**可结合的计算序列**的角色。

---
# Category 类型类（范畴抽象）

Haskell 的 `Category` 类型类直接对应范畴论中“范畴”的抽象概念。虽然在通常编程中我们默认使用函数组合和 `id` 来表示范畴（Hask）的结构，但 `Category` 类型类允许我们抽象出“一般化的态射”和“组合”。其定义如下（来自模块 `Control.Category`）：

```haskell
class Category cat where
 id :: cat a a
 (.) :: cat b c -> cat a b -> cat a c

```

这个定义与数学上范畴的公理惊人地一致：`id` 提供每个对象上的恒等态射，`(.)` 提供态射合成的运算。任何 `Category` 实例需要满足和先前 Hask 范畴相同的单位元与结合律：对于任意态射 `f :: cat a b` 和 `g :: cat b c`，都有 `f . id = f = id . f`；对于适当类型的 `f, g, h`，有 `(h . g) . f = h . (g . f)。

**函数范畴**只是 `Category` 的一个实例：Haskell 已内置 `instance Category (->)`，其中 `id = \x -> x`，组合 `(.)` 就是普通的函数复合。但是，我们可以用 `Category` 来表示比函数更一般的组合关系。例如，前面提到的 **Kleisli** 箭头就是 `Category` 的实例：`instance Monad m => Category (Kleisli m)`，它的 `id` 是 `return`，而组合 `(.)` 定义为 Kleisli 箭头的连接。再如，在**箭头（Arrow）** 框架中，我们处理的是更一般的计算结构（带有输入输出的进程），这些 Arrow 也往往是某种 `Category` 的实例，可以在不脱离抽象的情况下使用 `.` 和 `id` 组合它们。

通过 `Category` 类型类，Haskell 将“**可组合的抽象计算**”提炼为统一接口，使我们能够在不局限于具体实现（函数、Kleisli 箭头等）的情况下谈论“态射”和“范畴”。这是对范畴论的直接致敬：**Category 类确保了我们自定义的组合符号遵循范畴论公理，从而可以无缝地应用数学中的范畴理论直觉来推理代码**。

