[算法学习笔记(6)：最短路问题 - 知乎](https://zhuanlan.zhihu.com/p/96621396)
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
    auto cmp = [](const Edge &a, const Edge &b) { return a.second > b.second; };
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