
- 栈可以$O(n)$ 解决 一个列表里每个元素下一个更大/更下 这样的问题
``` cpp 
vector<int> nextsmaller(n, n);
stack<int> st;
for (int i = 0; i < n; i++) {
  while (!st.empty() && h[i] < h[st.top()]) {
	nextsmaller[st.top()] = i;
	st.pop();
  }
  st.push(i);
}
```

### Example 0:
Given an array of integers `heights` representing the histogram's bar height where the width of each bar is `1`, return _the area of the largest rectangle in the histogram_.
[[Largest Rectangle in Histogram]]