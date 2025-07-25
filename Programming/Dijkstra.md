[算法学习笔记(6)：最短路问题 - 知乎](https://zhuanlan.zhihu.com/p/96621396)

算法过程：

将结点分成两个集合：已确定最短路长度的点集（记为$S$集合）的和未确定最短路长度的点集（记为$T$集合）。一开始所有的点都属于$T$集合。

初始化$dis(s)=0$，其他点的$dis$均为$+\infty$。

然后重复这些操作：

1. 从$T$集合中，选取一个最短路长度最小的结点，移到$S$集合中。
2. 对那些刚刚被加入$S$集合的结点的所有出边执行松弛操作。

直到$T$集合为空，算法结束。

**Time Complexity**: $O(n^2)$  
### Example 0:
[743. Network Delay Time](https://leetcode.com/problems/network-delay-time/)

You are given a network of `n` nodes, labeled from `1` to `n`. You are also given `times`, a list of travel times as directed edges `times[i] = (ui, vi, wi)`, where `ui` is the source node, `vi` is the target node, and `wi` is the time it takes for a signal to travel from source to target.

We will send a signal from a given node `k`. Return _the **minimum** time it takes for all the_ `n` _nodes to receive the signal_. If it is impossible for all the `n` nodes to receive the signal, return `-1`.

```cpp fold:Implementation
int networkDelayTime(vector<vector<int>> &times, int n, int k) {
    vector<vector<Edge>> g(n + 1);
    for (int i = 0; i < times.size(); i++) {
      int u = times[i][0], v = times[i][1], w = times[i][2];
      g[u].push_back({v, w});
    }
    vector<int> dist(n + 1, INT_MAX);
    vector<bool> visited(n + 1, false);
    auto cmp = [](const Edge &a, const Edge &b) { return a.second > b.second;};
    priority_queue<Edge, vector<Edge>, decltype(cmp)> pq(cmp);

    pq.push({k, 0});
    dist[k] = 0;
    while (!pq.empty()) {
      auto [u, du] = pq.top();
      pq.pop();
      if (visited[u])
        continue;
      visited[u] = true;
      for (auto &e : g[u]) {
        auto [v, w] = e;
        if (du + w < dist[v]) {
          dist[v] = du + w;
          pq.push({v, du + w});
        }
      }
    }
    int cnt = 0, maxd = INT_MIN;
    for (int i = 1; i <= n; i++) {
      if (dist[i] != INT_MAX) {
        cnt++;
        maxd = max(maxd, dist[i]);
      }
    }
    return cnt == n ? maxd : -1;
  }
```