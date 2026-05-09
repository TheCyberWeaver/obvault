 #exercise  
# 4.1 Applying the [[Master Theorem|master theorem]]
a)
$a=4, b=1$
$1<\log_{2}4=2$
According to the third case of the master theorem $T(n)\leq O(n^{\log_{2}4})\leq O(n^{2})$

b)
$a=1, b=1$
$1>\log_{2}1=0$
According to the first case of the master theorem $T(n)\leq O(n)$

c)
$a=4, b=2$
$2= \log_{2}4=2$
According to the second case of the master theorem $T(n)\leq O(n^{\log_{2}4}\log n)\leq O(n^{2}\log n)$

# 4.2 Asymptotic notations
a)
![[Pasted image 20251016222246.png]]
b)
![[Pasted image 20251016222315.png|508]]

# 4.3 One-Looped Sort
a)

| Iteration | i after iteration | A |
| --------: | ----------------: | ------------------------ |
| 1 | 1 | [10, 20, 30, 40, 50, 25] |
| 2 | 2 | [10, 20, 30, 40, 50, 25] |
| 3 | 3 | [10, 20, 30, 40, 50, 25] |
| 4 | 4 | [10, 20, 30, 40, 50, 25] |
| 5 | 5 | [10, 20, 30, 40, 50, 25] |
| 6 | 4 | [10, 20, 30, 40, 25, 50] |
| 7 | 3 | [10, 20, 30, 25, 40, 50] |
| 8 | 2 | [10, 20, 25, 30, 40, 50] |
| 9 | 3 | [10, 20, 25, 30, 40, 50] |
| 10 | 4 | [10, 20, 25, 30, 40, 50] |
| 11 | 5 | [10, 20, 25, 30, 40, 50] |
| 12 | 6 | [10, 20, 25, 30, 40, 50] |
b)
**Invariant**: At the moment when the variable $i$ gets incremented to a new value $i = k$ for the first time, the first k elements of the array are sorted in increasing order.
**Base**: $k=1$, The first one element (or $A[0]$) is always sorted
**IS**: $k\to k+1$
- If $A[k]\geq A[k-1]$, then the first $k$ elements $A[0\dots k-1]$ are already sorted. Then $i$ is incremented to $k+1$, so that the next new position will be inspected.
- If $A[k]< A[k-1]$, then the algorithm swaps $A[k]$ and $A[k+1]$ and $i$ is set to $i-1$. This step repeatedly moves the current unsorted element to the left, until it gets to the right position. After the element gets to the right position, the first $k$ elements $A[0\dots k-1]$ are sorted. $i$ will then be continuously incremented until it meets a new value $i=k+1$, so that the next new position will be inspected.
By induction, every time $i$ is increased to k, $A[0\dots k-1]$ is sorted.

c)
$O(n^{2})$

# 4.4 Searching for the summit
a)

---
$B[0]\leftarrow-\infty$
$B[1\dots n]\leftarrow A[1\dots n]$
$B[n+1]\leftarrow -\infty$
while $l\leq r$ do:
$\quad m\leftarrow \left\lfloor \frac{l+r}{2} \right\rfloor$
$\quad$if $B[m]>B[m+1] \text{ and } B[m]>B[m-1]$ then
$\qquad$return $m$
$\quad$else if $B[m-1]<B[m]<B[m+1]$
$\qquad$$l\leftarrow m+1$
$\quad$else
$\qquad$$r\leftarrow m-1$
return -1

---
The code uses binary search to find the summit. In each iteration the search space for the summit is halved. Thus, we must have the worst-case running time $O(\log n)$

b)
Again, we can first find the summit $k$ in $O(\log n)$ time. Then we use binary search to try to find $x$ in the sorted array $A[1\dots k]$, which takes $O(\log n)$ time. If we don't find $x$ in the first part of the array, we then perform binary search on the second part $A[k+1\dots n]$, which is also sorted and also takes $O(\log n)$ time. Since each step requires at most $O(\log n)$ time, the worst-case running time of our algorithm is $O(\log n)$.
# 4.5 Counting function calls in loops
a)
$T(n)=\frac{(\lfloor \log_{2}n \rfloor+1)\lfloor \log_{2}n \rfloor}{2}$
$\Theta((\log n)^{2})$

b)
$T(n)=4\cdot2T\left( \frac{n}{2} \right)+n^{2}\cdot2n=8T\left( \frac{n}{2} \right)+2n^{3}$
According to the [[Master Theorem]], 
$T(n)=\Theta(n^{3}\log n)$
