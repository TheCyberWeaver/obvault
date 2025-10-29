[算法学习笔记(1) : 并查集 - 知乎](https://zhuanlan.zhihu.com/p/93647900)

# Union by Size (alternate to Union by Rank)

```cpp
struct DSU {
  vector<int> parent;
  vector<int> sz;

  DSU(int n) {
    parent.resize(n + 1);
    sz.resize(n + 1);
    for (int i = 1; i <= n; i++) {
      parent[i] = i;
      sz[i] = 1;
    }
  }

  int find(int x) {
    if (parent[x] == x)
      return x;
    return parent[x] = find(parent[x]);
  }

  bool unite(int u, int v) {
    int ru = find(u);
    int rv = find(v);
    if (ru == rv)
      return false;

    if (sz[ru] < sz[rv]) {
      swap(ru, rv);
    }
    parent[rv] = ru;
    sz[ru] += sz[rv];
    return true;
  }
};
```

### Example 0:
[721. Accounts Merge](https://leetcode.com/problems/accounts-merge/)
