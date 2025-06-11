[300. Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)
Given an integer array `nums`, return _the length of the longest **strictly increasing**_ _**subsequence**_.


Given ```a[]```
```f[i]```  The length of the longest increasing subsequence with the last element being ```a[i]```
$$f[i]=\begin{cases} 
1,&\forall 1\le j \le i, a_j < a_i\\
\max\limits_{1\le j \le i, a_j < a_i}​(f[j])+1,​&otherwise.​
\end{cases}
$$

Answer: $$\max\limits_{1\le i\le n}(f[i])$$
``` cpp fold:Implementation
int lengthOfLIS(vector<int> &nums) {
    vector<int> f(nums.size());
    int n = nums.size();
    for (int i = 0; i < n; i++) {
      f[i] = 1;
      int maxv = 0;
      for (int j = 0; j < i; j++) {
        if (nums[i] > nums[j]) {
          maxv = max(maxv, f[j]);
        }
      }
      f[i] = maxv + 1;
    }
    return *max_element(f.begin(), f.end());
  }
```