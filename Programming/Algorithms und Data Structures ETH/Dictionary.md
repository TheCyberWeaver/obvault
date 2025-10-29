#eth 
A dictionary is a collection of unique keys with the following operations:
- `search(x, D)`: Returns `true` if integer `x` exists in dictionary `D`, otherwise `false`.
- `insert(x, D)`: Adds key `x` to `D` only if it doesn’t already exist.
- `delete(x, D)`: Removes key `x` from `D`.

# Binary Trees

- All keys in the left subtree are smaller than the root node’s key.
- All keys in the right subtree are larger than the root node’s key.

| Function | Average     | Worst case |
| -------- | ----------- | ---------- |
| Search   | $O(\log n)$ | $O(n)$     |
| Insert   | $O(\log n)$ | $O(n)$     |
| Delete   | $O(\log n)$ | $O(n)$     |

### Problem: The Linearised Binary Search Tree
 If we insert values in ascending order, the resulting structure becomes more like a linked list than a balanced tree.

# 2-3-Tree
2-3 children per node
- Every internal node is a 2-node or a 3-node.
	- 2-Node is just like a normal node in binary trees.
	- 3-Node: ![[3-node.excalidraw|338]]
- All leaves are at the same level.
- All data is kept in sorted order.
- Leave nodes are the keys

| Function | Average     | Worst case  |
| -------- | ----------- | ----------- |
| Search   | $O(\log n)$ | $O(\log n)$ |
| Insert   | $O(\log n)$ | $O(\log n)$ |
| Delete   | $O(\log n)$ | $O(\log n)$ |
Insertion:
![[Pasted image 20251021114414.png|492]]
deletion:
- search(x)
- delete B and a separator from the parent node
	case1:The neighbor has 3 children ![[2-3-tree-deletion-case1.excalidraw|328]]
	case2: The neighbor has 2 children 	![[2-3-tree-deletion-case2.excalidraw|328]]
We can perform other operations on this data structure (e.g. find maximum)
# Hash table

