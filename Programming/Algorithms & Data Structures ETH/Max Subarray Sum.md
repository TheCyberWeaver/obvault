[53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

gegeben: $a_{1},a_{2},\dots ,a_{n}\in \mathbb{Z}$
gesucht: $S_{i,j}=a_{i}+\dots+a_{j},\quad i,j\in\{1\dots n\}, i<j$
$S=0$ falls alle $a_{k}<0$

anders formuliert

## The Naive Approach
for $i=1\dots n$
	for $j=i\dots n$
		$S_{i,j}=\sum_{k=1}^{j}a_{k}$

Anzahl Addition: $A(n)\leq \sum_{i=1}^{n} \frac{(n-i+1)^{2}}{2}=\frac{1}{2}(n^{2}+(n-1)^{2}+\dots+1^{2})=\frac{n(n+1)\left( n+\frac{1}{2} \right)}{6}\leq O(n^{3})$
## Reduce Duplicate Work
**Using Prefix sum**
$A(n)=\sum_{i=1}^{n}(n-i)=\frac{n(n-1)}{2}=O(n^{2})$

## Divide and Conquer

![[divide and conquer.excalidraw|576]]
$S=max(Fall_{1},Fall_{2},Fall_{3})$

$n=1$ : $S=a_{1}$ falls $a_{1}>0$
sonst $S=0$

$A(n)=a\cdot n+2A\left( \frac{n}{2} \right)=2\left( 2A\left( \frac{n}{2} \right)+a\frac{n}{2} \right)+an=2^{2}T\left( \frac{n}{4} \right)+2n=2^{\log n}A\left( \frac{n}{n}\right)+a\cdot n\cdot\log n$
$=c\cdot n+a\cdot n\log n$
$=O(n\log n)$
### Another approach
![[Master Theorem]]
## Dynamic Programming

```cpp
class Solution {
public:
  int maxSubArray(vector<int> &nums) {
    int n = nums.size();
    int currentsum = 0;
    int maxs = INT_MIN;
    int maxsum = INT_MIN;
    for (int i = 0; i < n; i++) {
      currentsum += nums[i];
      maxs = max(maxs, currentsum);
      if (currentsum < 0) {
        maxsum = max(maxsum, maxs);
        currentsum = 0;
        maxs = INT_MIN;
      }
    }
    maxsum = max(maxsum, maxs);
    return maxsum;
  }
};
```