 #exercise 
# 6.1
##### a)
![[f77c3826e909b8a43e9a048d44b8aacc.jpg|512]]
##### b) 

# 6.3
![[824628872c87d805150814384b7dc1ac.jpg|256]]
##### a)
```
A(n):
	if(n<=4)return n
	return A(n-1)+A(n-3)+2*A(n-4)
```

##### b)
Let T(n) be calls made by REC-A(n). For n≥5, 
$T(n) ≥ T(n-1)+T(n-3)+T(n-4) ≥ 3·T(n-4)$. 
Thus $T(n) ≥ 3^{⌊(n-4)/4⌋} > Ω((3^{1/4})^n)$ with $C=3^{1/4}\approx1.316>1$.
###### Another approach
$C^{n}\geq C^{n-1}+C^{n-3}+C^{n-4}+O(1)$
$C^{4}\geq C^{2}+C+2$


##### c)
```
M[1...n] initialized with -1
M[1]=1; M[2]=2; M[3]=3; M[4]=4;
MEMO-A(n, M):
 if M[n]!=-1 return M[n]
 M[n] <- MEMO-A(n-1,M) + MEMO-A(n-3,M) + 2*MEMO-A(n-4,M)
 return M[n]
```
Time $O(n)$
With memorization one compute $A_{k}$​ for each $k=1\dots n$ exactly once, which gives $O(n)$
##### d)
1. **DP table**: one array `DP[1..n]`. `DP[i] = A_i`.
2. **Entry formula**: 
 1. Base cases: `DP[1]=1, DP[2]=2, DP[3]=3, DP[4]=4`. 
 2. For `i≥5`: `DP[i] = DP[i-1] + DP[i-3] + 2*DP[i-4]`.
3. **Order**: increasing `i = 5…n`.
4. **Extracting solution**: return `DP[n]`.
5. **Run time**: $O(n)$
pseudo code:
```
A(n):
	array A[1...n]
	if(n<=4)return n
	for i <- 5...n:
 A[i] <- A[i-1]+A[i-3]+2*A[i-4]
	return A[n]
```
# 6.4
##### a)
$n=7$, $k=4$, $b=[1,3,4,5]$
$OPT=2$ with $3+4=7$
The output of algorithm 1: $3$

##### b)
$O(n\cdot k)$
**explanation**: The outer loop runs for $N=1$ to n (n iterations). For each $N$, the inner loop scans all $k$ coin types and does $O(1)$ work per coin. In total, we get $O(n\cdot k)$

##### c)
**IH**: $f(n)$ in the algorithm gives $OPT(n)$ 
**Base**: $n=0$ 
$f(0)=0$
this is true because if the total value is 0, then we need no coins
**IS**: Assume $f(n),\; n\in[N-1]$ are already computed.
We can then obtain the best choosing strategy ($OPT(N)$) by selecting one coin and a optimal choosing strategy from $OPT(n),\; n\in[N-1]$ (which is determined by the coin we chose). The algorithm iterate through all possible coins and finds the choosing strategy with least coins. Thus, after each outer iteration, $f(n)$ must have the value of $OPT(n)$

##### d)

```
array f[0...n] <- undefined
f[0] <- 0
findOPT(n):
	if f[n] is undefined then
 return f[n]
	best <- INF
	for i <- 1...k do
 if b[i]<=n then
 best <- min(best, 1 + findOPT(n − b[i]))
	f[n] <- best
	return f[n]

Print(findOPT(N))
```