下面通过一个综合示例，展示 Functor、Applicative、Monad 三种抽象是如何在 Haskell 中配合使用的。考虑一个简单的场景：我们想从配置中读取两个整数，然后将它们相加，但在读取过程中可能会失败（比如键不存在）。我们可以使用 `Maybe` Monad 来处理可能的失败，通过组合 Functor 和 Applicative 的功能来方便地进行计算：

```haskell
import Data.Maybe (fromMaybe)

-- 假设的配置读取函数
lookupInt :: String -> Maybe Int
lookupInt key = ... -- （这里省略实现，假设从配置中取整数）

-- 使用 Functor 提升纯函数到带上下文的计算
incrementConfig :: String -> Maybe Int
incrementConfig key = (+1) <$> lookupInt key
-- (<$>) 是 fmap 的别名，将 lookupInt 返回的 Maybe Int 中的值加1

-- 使用 Applicative 同时读取两个配置项并相加
addConfigs :: String -> String -> Maybe Int
addConfigs key1 key2 = (+) <$> lookupInt key1 <*> lookupInt key2
-- (<*>) 将第一个 Maybe 中的函数应用到第二个 Maybe 中的值

-- 使用 Monad 串联多个步骤的计算
combinedCalc :: String -> String -> Maybe Int
combinedCalc key1 key2 = do
 x <- lookupInt key1 -- Monad: 取出第一个配置值，若 Nothing 则传播
 y <- incrementConfig key2 -- Monad: 取出第二个配置值并在 Monad 内部加1
 return (x + y) -- 返回相加结果（自动包装为 Just 或 Nothing）

```

在上述代码中：

- `incrementConfig` 利用 Functor (`<$>`) 将普通加法函数提升为可作用于 `Maybe` 的函数，实现读取配置值后加 1 的操作。如果配置缺失导致 `lookupInt key` 返回 `Nothing`，那么 `fmap` 会让结果依然是 `Nothing`（因为无法对不存在的值加1）。
 
- `addConfigs` 使用 Applicative (`<$>` 和 `<*>`) 实现**并行的**计算：同时读取两个配置项，并将它们相加。如果任意一个配置项不存在，整个结果就是 `Nothing`；只有当两个都是 `Just` 时才会得到 `Just` 的和。这体现了 Applicative 可以方便地组合独立的效果。
 
- `combinedCalc` 则使用 Monad 的 `do` 表达式串联步骤：首先读取 `key1` 对应的值赋给 `x`，如果失败直接返回 `Nothing`；接着在 Monad 上下文中调用前面的 `incrementConfig key2`（这实际上使用了先 Functor 再 Monad 的组合能力），取得 `y`；最后返回 `x+y`。这里，`do` 表达式背后用到了 `>>=` 来传递 `x` 和 `y`，使我们无需手动检查 `Nothing`，逻辑更清晰。
 

通过这个例子可以看到，Functor 提供了对**单一上下文**中的值进行映射的能力，Applicative 提供了处理**独立多个上下文**的手段，而 Monad 则允许表达**顺序依赖的上下文计算**。它们各自对应的范畴论结构（函子、带单位元的函子、幺半群）确保了这些操作符满足良好的代数规律，使我们能够在代码中放心地组合它们而不引入歧义或不一致。