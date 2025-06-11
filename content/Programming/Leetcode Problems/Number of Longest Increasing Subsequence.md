[673. Number of Longest Increasing Subsequence](https://leetcode.com/problems/number-of-longest-increasing-subsequence/)

Given an integer array `nums`, return _the number of longest increasing subsequences._

**Notice** that the sequence has to be **strictly** increasing.


Given ```a[]```
Based on the code of the [[Longest Increasing Subsequence]] problem

 ```c[i]```  The number of the longest increasing subsequence with the last element being ```a[i]```
 
  $c[i]=\sum_{j=0}^{i}c[j]$  if ```f[j]``` has the current longest increasing subsequence

   Answer: 
   $$Answer=\sum_{i=0}^{n}c[i], where\ f[i]=\max\limits_{0\le j<n} f[j]$$

``` cpp fold:"Implementation"
for (int i = 0; i < n; i++) {
  f[i] = 1;
  c[i] = 1;
  int maxv = 0;
  for (int j = 0; j <= i; j++) {
	if (nums[i] > nums[j]) {
	  if (f[j] > maxv) {
		c[i] = c[j];
		maxv = f[j];
	  } else if (f[j] == maxv) {
		c[i] += c[j];
	  }
	}
  }
  f[i] = maxv + 1;
}
```
