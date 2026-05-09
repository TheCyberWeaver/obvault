 #exercise 
# 7.1. 1-3 sub set sums 

1. **Dimensions**: The table is two dimensional and has a size of $(n+1)\cdot (d+1)$
2. **Subproblems**: the entry `dp[i][j]` is a boolean value that determines whether $i$ is a 1-3 subset sum of $\{ 1,\dots ,A_{j} \}$ 
3. **Recursion**:
	1. Base Case: `dp[0][0]` is true and all other values are false
	2. Normal Case: the entry `dp[i][j]` is true if `dp[i-1][j]`,`d[i-1][j-A[i]]` or `d[i-1][j-3*A[i]]` is true.
 - Justification: Correct because the last decision for item `i` is exactly one of: 
 1. don't take
 2. take `1·A[i]`
 3. take `3·A[i]`
 4. and the remainder depends on the first `i-1` items. Since we assume we have already calculated all the cases with `i-1`, we get whether `dp[i][j]` is achievable.
4. **Calculation order**: Increase `i` from `1..n`. For each `i`, increase `j` from `0..b`. Each state only depends on row `i-1`, already computed.
5. **Extracting the solution**: take the value in `dp[n][b]`
6. **Running time**: $O(b\cdot n)$

# 7.2. Longest ascending subsequence
##### a)
```
dp[i]=max(dp[j] for all j=1...n and A[j]<=A[i])+1
dp[1]=1
```

##### b)
DP-table

| `i` | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `dp[i]` | 1 | 2 | 1 | 1 | 3 | 2 | 3 | 4 | 4 |
Answer: $4$

# 7.4 String counting
1. **Dimensions**: The table is three dimensional and has a size of $(n+1)\cdot (k+1)\cdot2$
2. **Subproblems**: the entry `dp[i][j][l]` means the number of binary strings $S$ with following properties:
	1. has length `i` 
	2. has `k` "11" in the string
	3. the last bit is `l` (0 or 1)
3. **Recursion**:
	1. Base Case: 
 1. `dp[1][0][0]=1`
 2. `dp[1][0][1]=1`
	2. Normal Case: 
 1. `dp[i][j][0]=dp[i-1][j][0]+dp[i-1][j][1]`
 2. `dp[i][j][1]=dp[i-1][j][0]+dp[i-1][j-1][1]` 
4. **Calculation order**: 
```
for i in 1..n:
	for j in 0..k:
 dp[i][j][0]=dp[i-1][j][0]+dp[i-1][j][1]
 if j>0:
 dp[i][j][1]=dp[i-1][j][0]+dp[i-1][j-1][1]
 else:
 dp[i][j][1]=dp[i-1][j][0]
```
5. **Extracting the solution**: take the value of `dp[n][k][0]+dp[n][k][1]`
6. **Running time**: $O(n\cdot k)$