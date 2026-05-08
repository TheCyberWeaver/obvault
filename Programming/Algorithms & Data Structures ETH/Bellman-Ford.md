Compute shortest distances from a source vertex $s$ to all vertices, allowing negative edge weights.

## When to Use
- Graph has negative edge weights.
- Need to detect whether a reachable negative cycle exists.

## Idea
- Initialize `dist(s)=0`, all others to $\infty$.
- Repeat edge relaxation for all edges exactly $|V|-1$ times.
- Do one extra pass:
  - If any distance still improves, a reachable negative cycle exists.

## Relaxation
For each directed edge $(u,v,w)$:
$$
dist(v)=\min(dist(v),\;dist(u)+w)
$$

## Complexity
- Time: $O(|V||E|)$
- Space: $O(|V|)$ (plus optional parent array)

## Output
- Distance array `dist`
- Optional predecessor array `parent` for path reconstruction
- Negative-cycle detection result