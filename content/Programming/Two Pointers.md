
## 对于双指针的遍历方式
### 方法一
对于固定区间k，一种遍历方式是遍历右指针，然后让左指针跟上具体表现为：
```cpp
int l = 0, r = 0;
while (r < n) {
  ...//actions
  if (r - l + 1 == k) {
	...//actions
	l++;
  }
  r++;
}
```
这样优雅解决了遇到第一合法区间前预处理的问题，无需单独在循环前预处理。预处理的内容放在while循环和合法if判断之间。
#### Example 0: 
[438. Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/)
Given two strings `s` and `p`, return an array of all the start indices of `p`'s anagrams in `s`. 
```cpp
//findAnagrams(string s, string p)
for (int i = 0; i < m; i++) {
  freq[p[i]]++;
}
int l = 0, r = 0;
while (r < n) {
  freq[s[r]]--;
  if (r - l + 1 == m) {
	if (zero(freq))
	  ans.push_back(l);
	freq[s[l]]++;
	l++;
  }
  r++;
}
```

#### Example 1:
You are given an array of integers `nums`, there is a sliding window of size `k` which is moving from the very left of the array to the very right. You can only see the `k` numbers in the window. Each time the sliding window moves right by one position.

Return _the max sliding window_.

See File [[Sliding Window Maximum]]

### 方法二
让左右指针从两边边界开始逐渐向中间靠拢
### Example 0:
Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

See [[Three Sum#方法二 Two Pointers| Three Sum]]