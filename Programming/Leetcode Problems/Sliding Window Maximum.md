[239. Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/)
You are given an array of integers `nums`, there is a sliding window of size `k` which is moving from the very left of the array to the very right. You can only see the `k` numbers in the window. Each time the sliding window moves right by one position.

Return _the max sliding window_.

**Example 1:**

**Input:** nums = \[1,3,-1,-3,5,3,6,7], k = 3
**Output:** \[3,3,5,5,6,7]

使用deque双向队列和双指针轻松解决，deque按照递减维护目前所有可能的最大值。对于超出区间的最大值可以通过左指针检测。当检测到左指针元素和deque最大值相同，删除最大值。

> [!tip]
> 注意deque维护的可能最大值必须要包含重复，否则左指针不能正确删除区间外的值

```cpp fold:implementation
int l = 0, r = 0;
    while (r < n) {
      while (!dq.empty() && dq.back() < nums[r])
        dq.pop_back();
      dq.push_back(nums[r]);
      if (r - l + 1 == k) {
        ans.push_back(dq.front());
        if (nums[l] == dq.front())
          dq.pop_front();
        l++;
      }
      r++;
    }
```
