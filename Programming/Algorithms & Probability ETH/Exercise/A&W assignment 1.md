# T1.1 Disjoint Paths
![[Pasted image 20260305141011.png|632]]
a)
using the edge version of Mengers's theorem
$\lambda _{a,c}=min\{ \lvert F \rvert:F\subseteq E \text{ and }G-F \text{ separates } a,c\}$
claim: In the graph $G-F$, either $a,b$ is disconnected or $b,c$ is disconnected
Suppose both $a,b$ and $b,c$ are connected, then it would mean there is a path from $a$ to $b$ and a path $b$ to $c$. Therefore, we can concatenate those two paths and makes $a,c$ connect. This contradicts the fact that $G-F$ separates $a,c$

Therefore, every $a-c$ cut (a set of edges that disconnects $a,c$) must also either be a $a-b$ cut or a $b-c$ cut.
This implies that every $\lvert F \rvert\geq min(\lambda _{a,b},\lambda _{b,c})$ . Thus $\lambda _{a,c}\geq min(\lambda _{a,b},\lambda _{b,c})$

b)
Consider a graph $G'$ by adding a new vertex $v$ to $G$ and connect $y$ to $v$ with $\alpha$ parallel edges, $z$ to $v$ with $\beta$ parallel edges

we first prove that $\lambda _{x,v}\geq\alpha+\beta$
By Menger's theorem we know $\lambda _{x,z}=min\{ \lvert F \rvert :F\subseteq E' \text{ and } G'-F \text{ separates }x,z \}$
- case 1: $F$ does not separates $y,z$
	- $y,z$ are on the side of $v$ (connected with $v$)
		- $\lvert F \rvert\geq\lambda _{x,y}+\lambda _{x,z}\geq\alpha+\beta$
	- $y,z$ are on the side of $x$ (connected with $x$)
		- $\lvert F \rvert=\alpha+\beta$
- case 2: $F$ separate $y,z$
	- wlog. we assume that $y$ is connected with $x$ and $z$ is connected with $v$.
	- all $\alpha$ edges $y-v$ must be in $F$
	- $|F| \ge \alpha + |F \cap E|,$ where $E$ are the original edges of $G$.
	- Also, $x$ and $z$ are separated in $G' - F$. The new vertex $v$ and the new edges do not help connect $x$ to $z$, so the separation must be achieved by deleting original edges that disconnect $x$ from $z$. Therefore,$|F| \ge \alpha + \beta.$

Since:
- exactly $\alpha$ of the paths end via an edge between $y,v$
- exactly $\beta$ of the paths end via an edge between $z,v$​.

Thus we obtain $\alpha$ edge-disjoint $x-y$ paths and $\beta$ edge-disjoint $x-z$ paths that are pairwise edge-disjoint.
This proves b)