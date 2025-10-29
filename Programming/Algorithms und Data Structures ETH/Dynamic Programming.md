#eth  
### Longest common substring
[1143. Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/)
```python
def longest_common_subsequence(A, B):
    n, m = len(A), len(B)
    L = [[0] * (m + 1) for _ in range(n + 1)]
 
    for i in range(1, n + 1):
        for j in range(1, m + 1):
            if A[i - 1] == B[j - 1]:
                L[i][j] = 1 + L[i - 1][j - 1]
            else:
                L[i][j] = max(L[i][j - 1], L[i - 1][j])
 
    return L[n][m]
```

### Edit Distance
[72. Edit Distance](https://leetcode.com/problems/edit-distance/)
