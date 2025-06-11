[Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram/description/ "https://leetcode.com/problems/largest-rectangle-in-histogram/description/")

Given an array of integers `heights` representing the histogram's bar height where the width of each bar is `1`, return _the area of the largest rectangle in the histogram_.

对于一个元素，完全包含其的最大面积由旁边的第一次出现的更小元素决定（）
> [!Tip]
> 
> 记得要同时找到一个元素两边的更小元素，而不是一边

```cpp fold:Implementation
int largestRectangleArea(vector<int> &h) {
    int n = h.size();
    vector<int> nextsmaller(n, n);
    vector<int> presmaller(n, -1);
    stack<int> st;
    for (int i = 0; i < n; i++) {
      while (!st.empty() && h[i] < h[st.top()]) {
        nextsmaller[st.top()] = i;
        st.pop();
      }
      st.push(i);
    }
    st = {};
    for (int i = n - 1; i >= 0; i--) {
      while (!st.empty() && h[i] < h[st.top()]) {
        presmaller[st.top()] = i;
        st.pop();
      }
      st.push(i);
    }
    // dbg(presmaller);
    // dbg(nextsmaller);
    int maxa = 0;
    for (int i = 0; i < n; i++) {
      maxa = max(maxa, h[i] * (nextsmaller[i] - presmaller[i] - 1));
    }
    return maxa;
  }
```
