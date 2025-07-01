---
aliases: ["Haskell 和范畴论的对应"]
tags: [Haskell, CategoryTheory, FunctionalProgramming, TypeSystem]
created: 2025-06-20
---

## 目录

- [[#引言|引言]]
- [[#范畴论核心概念与 Haskell 中的对应|范畴论核心概念与 Haskell 中的对应]]
- [[Haskell 类型类与范畴论概念的映射|Haskell 类型类与范畴论概念的映射]]
    - [[Haskell 类型类与范畴论概念的映射#Functor 类型类（函子）|Functor 类型类（函子）]]
    - [[Haskell 类型类与范畴论概念的映射#Applicative 类型类（内积函子/单元函子）|Applicative 类型类（内积函子/单元函子）]]
    - [[Haskell 类型类与范畴论概念的映射#Monad 类型类（单子）|Monad 类型类（单子）]]
    - [[Haskell 类型类与范畴论概念的映射#Category 类型类（范畴抽象）|Category 类型类（范畴抽象）]]
- [[Haskell Example|Haskell 实例：范畴论抽象在代码中的应用]]
- [[Haskell 语言设计中的范畴论思想|Haskell 语言设计中的范畴论思想]]

---

## 引言
Haskell 是一门以函数式为核心的编程语言，其类型系统和抽象机制深受数学思想影响。其中，范畴论提供了分析**类型与函数关系**的强大工具，有助于解释 Haskell 中许多看似神秘的概念。在范畴论视角下，我们可以将 Haskell 看作一个[[Category Theory Intro#What is a Category|范畴]]（通常称为 **Hask**），并将 Haskell 的类型、函数以及一系列抽象（Functor、Monad 等）与范畴论中的对象、态射和函子等一一对应起来。

---

## 范畴论核心概念与 Haskell 中的对应

**范畴论**研究数学结构及其之间的关系。它的核心概念包括**对象**（Objects）、**态射**（Morphisms，又称[[Category Theory Intro#Difference between Morphism and Function|箭头]]）、**范畴**（Category）、**函子**（Functor）、**自然变换**（Natural Transformation）和**幺半范畴**（Monoidal Category）等。下表总结了这些概念在 Haskell 中的对应关系：

| **范畴论概念**                        | **Haskell 对应**                                                                                                                                                                                              |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **对象（Object）**                   | 类型（Type），可以视为该类型所有值的集合。例如，`Int`、`Bool`、`String` 等类型可看作对象。                                                                                                                                                   |
| **态射（Morphism）**                 | 函数（Function），表示对象之间的映射，即类型 `A` 到类型 `B` 的纯函数 `A -> B。每个态射有确定的源对象和目标对象，例如函数 `f :: A -> B` 是从对象 `A` 到 `B` 的一个态射。                                                                                               |
| **范畴（Category）**                 | 拥有上述对象和态射，并封闭于态射的组合且存在单位态射的结构。Haskell 的类型和函数构成范畴 **Hask**：对象是所有 Haskell 类型，态射是所有 Haskell 函数，函数组合 `.` 作为态射合成，`id` 作为单位态射。Hask 满足范畴公理（结合律和单位元律）。                                                              |
| **函子（Functor）**                  | 范畴间的映射：在 Haskell 中体现为 **类型构造器**（将类型映射为类型）及其上的 `fmap` 函数（将函数映射为函数）。也就是 Haskell 的 `Functor` 类型类实例（通常是从 Hask 到 Hask 的自函子）。例如，`Maybe` 类型构造器把类型 `T` 对应到类型 `Maybe T`，而 `fmap` 可以将函数 `A->B` 映射为 `Maybe A->Maybe B。 |
| **自然变换（Natural Transformation）** | 函子之间的“态射”：在 Haskell 中可表示为一种多态函数，类型形式一般为 `∀a. F a -> G a`，要求对所有态射保持自然性（即满足交换律）。直观理解，自然变换为每个对象 `a` 提供从 `F a` 到 `G a` 的映射，并与函子作用交换。                                                                            |
| **幺半范畴（Monoidal Category）**      | 带有“张量乘积”与单位对象的范畴。在 Haskell 中，**直积类型**（如 `(A, B)`）是范畴 Hask 的笛卡尔积，单位对象是单位类型 `()`，因此 Hask 是一个幺半范畴（严格的**单元范畴**），其“乘积”即笛卡尔积满足结合律并有单位元。这为在该范畴上的函子提供了额外的结构，比如 Applicative 和 Monad（后文将详述）。                          |
## Category Hask 
![[Pasted image 20250620112059.png]]
上述图示展示了一个简单范畴：
- 对象：`A`、`B`、`C`  
- 恒等态射：三条 loop  
- 非恒等态射：`f :: C -> B` 和 `g :: A -> B`

范畴须满足：
1. **组合** 且满足结合律  
2. 每个对象都有恒等态射作为**单位元**

在 **Hask** 范畴中：

- 函数组合使用 `(.)`，对应范畴中的态射合成  
- `id` 函数对应各类型上的恒等态射  
- 对于任意函数  
```haskell
  f :: A -> B
  g :: B -> C
  h :: C -> D
```

有

```haskell
(h . g) . f = h . (g . f)    -- 结合律
id . f     = f . id     = f  -- 单位元律
```

- 由于 `id` 是多态的，可视作各具体类型上的恒等态射；通过指定类型可以将其“单态化”以对应范畴论中的单一对象上的恒等箭头。

总之，**Hask** 可视为一个范畴，其中“对象”是类型，“态射”是函数，为后续讨论 Functor、Monad 等概念奠定基础。