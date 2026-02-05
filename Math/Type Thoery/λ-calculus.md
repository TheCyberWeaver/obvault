## Function Definition

Let $\Phi$ be an expression that uses $x$ (suppose we have $\Phi=x+x$ here)
Assume we have $\Phi:B$ and $x:A$ ($\Phi$ has type $B$ and $x$ has type $A$)

### Normally
$f(x):\equiv \Phi$ (we define $f$ to be ${} x+x {}$)

Then $f(2)$ is judgmentally equal to $2+2$

### λ-abstraction
If we do not want to introduce a name for the function, we can write
$$
\lambda(x:A).\Phi
$$
Thus we have: $\lambda(x:A).\Phi:A\to B$  (This anonymous function has type $A\to B$)
In this specific example (both type $A,B$ are $\mathbb{N}$) we have $(\lambda(x:\mathbb{N}).x+x):\mathbb{N}\to \mathbb{N}$

Another notation is: $(x\mapsto\Phi):A\to B$

> [!NOTE]
> This is the concept of anonymous function in Haskell

## Apply Function

$$
(\lambda x.\Phi)(a)\equiv\Phi'
$$
In the example above
$(\lambda x.x+x)(2)\equiv2+2$


### Dummy variables
Let's define $f(x):\equiv\lambda y.x+y$
What is $f(y)$?
it is $\lambda z.y+z$ (note that $\lambda y.y+y$ would be wrong), because the $y$ inside is a "local variable"


## Currying
For a function that has two inputs: $f(x,y):\equiv \Phi$

Suppose it has type $f:(A\to B)\to C$
Currying allows us to write it as $f:A\to(B\to C)$

This means we allow $f(x,y)$ to be written as $f(x)(y)$

Using $\lambda$ abstraction this corresponds to $f:\equiv\lambda x.\lambda y.\Phi$ or even written as ($f:\equiv x\mapsto y\mapsto\Phi$)
#### Example
Let $\Phi$ be $x+y$, then we would have $f(2)\equiv 2+y$