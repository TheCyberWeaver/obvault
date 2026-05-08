> [!NOTE] Terminology
> A **stable set** is the same as an **independent set**: a set $S \subseteq V$ such that no edge has both endpoints in $S$.

## Randomized algorithm

Let $G=(V,E)$.

1. Keep each vertex independently with probability $p$.
2. Let $V_p$ be the set of kept vertices and start with $S_0 = V_p$.
3. For each edge $e=\{u,v\}$ with both $u,v \in S_0$, remove one of its endpoints from $S_0$.
4. Let $S$ be the remaining set.

Then $S$ is a stable set.
![[Pasted image 20260326113558.png|364]]

> [!NOTE]
> A simpler variant removes both endpoints of every surviving edge. That also produces a stable set, but it gives the weaker bound $|S| \ge X - 2Y$ instead of $|S| \ge X - Y$.

## Expectation analysis

Let $G=(V,E)$ with $|V|=n$ and $|E|=m$.

For each vertex $v \in V$, let $X_v$ be the [[Random Variable#Special case: indicator variable|indicator variable]] that $v$ is kept:
$$
X_v =
\begin{cases}
1, & v \in V_p, \\
0, & \text{otherwise.}
\end{cases}
$$
Then $\mathbb{E}[X_v] = p$, so for $X = \sum_{v \in V} X_v$ we get
$$
\mathbb{E}[X] = np.
$$

For each edge $e=\{u,v\} \in E$, let $Y_e$ be the indicator variable that both endpoints survive the first round. Then
$$
\mathbb{E}[Y_e] = p^2
$$
because the two vertex choices are independent. Hence for $Y = \sum_{e \in E} Y_e$ we get
$$
\mathbb{E}[Y] = mp^2.
$$

Each surviving edge forces at most one deletion, hence
$$
|S| \ge X - Y.
$$
Taking expectations gives (using [[Expected value#Linearity of expectation|linearity of expectation]])
$$
\mathbb{E}[|S|] \ge \mathbb{E}[X - Y] = \mathbb{E}[X] - \mathbb{E}[Y] = np - mp^2.
$$

## Optimal choice of $p$

To maximize the lower bound
$$
f(p) = np - mp^2,
$$
differentiate:
$$
f'(p) = n - 2mp.
$$

So the stationary point is
$$
p = \frac{n}{2m}.
$$

If this value lies in $[0,1]$, it is the optimal choice, and then
$$
\mathbb{E}[|S|] \ge n \cdot \frac{n}{2m} - m \left(\frac{n}{2m}\right)^2 = \frac{n^2}{4m}.
$$
