#eth 
$$
T(n)=a\cdot T\left( \frac{n}{b}\right)+n^{c}
$$
- $c>\log _{b}a\implies T(n)=O(n^{c})$
- $c=\log _{b}a\implies T(n)=O(n^{c}\log n)$
- $c<\log _{b}a\implies T(n)=O(n^{\log _{b}a})$

### Example

$T(n)=2T\left( \frac{n}{2}+O(n) \right)$
- $a=2$ 
- $b=2$
- $c=1$
$\implies T(n)=O(n\log n)$

$T(n)=4T\left( \frac{n}{2}+O(n) \right)$
- $a=4$ 
- $b=2$
- $c=1$
$\implies T(n)=O(n^{2})$


