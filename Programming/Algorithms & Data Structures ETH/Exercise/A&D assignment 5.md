#eth #exercise 
# 5.1 Max-Heap operations
![[1cdcfdb15c9a62101c5eda1ddff2f69c.jpg|343]]
# 5.2 Guessing an interval
Choosing two integers $1\leq a<b\leq200$ has $\begin{pmatrix}200 \\ 2 \end{pmatrix}$ ways:
$\begin{pmatrix}200 \\ 2\end{pmatrix}= \frac{200\cdot199}{2}=19900$
Alice has in total 19900 choices. 
Consider Bob's strategy as a decision tree, and each leaf corresponds to a win for Bob. For each question Bob can only halve the search room in the worst case. Thus, in the best algorithm, the search tree is in a complete binary tree, and the height is at least $\lceil \log_{2}19900 \rceil=15$ which is greater than $12$, meaning Bob's always-win strategy in 12 attempts does not exists.
# 5.3 Counting function calls in recursive functions
a)
$O(n^{\log_{2}3})$

b)
function $h(n)$
$O(n)$

function $k(n)$
$O(n)$

# 5.4 Bubble sort invariant
a)
after j-th iteration, the last j elements are sorted and are bigger than all the elements before
b)
1. after the first generation the last element is sorted (or the last element is the largest element)
	We prove this by induction over the inner loop:
	- IH: the largest element is in the interval $A[i+1,\dots, n]$ after $i$ iteration
	- Base case ($i=1$): After comparing $A[1]$ and $A[2]$, the larger of the two elements moves to position 2. Therefore, $A[1]$ cannot be the largest element. The largest element must be inside $A[2,\dots ,n]$
	- IS: $i\to i+1$
		- After comparing $A[i]$ and $A[i+1]$, the larger of the two elements moves to position $A[i+1]$. Therefore, $A[i]$ cannot be the largest element. The largest element must be inside $A[i+1,\dots ,n]$
	By induction, after the first outer loop, the largest element is in $A[n-1+1,\dots ,n]$ and thus must be the last element of the array
2. Assume the last j elements are sorted and are bigger than all the elements before. In the next iteration the largest element of $A[1,\dots,n-j]$ will be moved to the end of this array, meaning $A[n-j,\dots,n]$ ($j+1$ elements) are now sorted and are bigger than all the elements before.
3. after $n$ outer iterations, the last $n$ elements are sorted, and therefore, all the elements in array $A$ are sorted.

# 5.5
a)
a doubly linked list can be used to implement [[Stack|stack]] efficiently.
let pointer `head` always points to the top of the stack
- push(x): $O(1)$ 
	- create a new node `n` with value $x$
	- Set `n.prev=head`
	- Set `head.next=n`
	- Set `head=n`
- pop: $O(1)$
	- set `head=head.prev`
b)
a doubly linked list can be used to implement queue efficiently.
- `head` → points to the first element.
- `tail` → points to the last element.
- enqueue: $O(1)$
	- create a new node `n` with value $x$
	- Set `n.prev=tail`
	- Set `tail.next=n`
	- Set `tail=n`
- dequeue: $O(1)$
	- Set `head=head.next`
	- Set `head.prev = nullptr`