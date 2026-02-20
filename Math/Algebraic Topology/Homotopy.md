## Formal Definition


## Example: Blender :D
In Blender, one can create a smooth spine curve $C$ and use Geometry Nodes to generate a 3D tubular shape around it. One can then use a parameter $t\in[0,1]$ to control the tube’s radius so it changes continuously over time to make an animation ($t$ change continuously). 
- Consider the solid tube $V_{t}=\{ x:dist(x,C)\leq r(t) \}$
	- Each map from $V_{t}$ to $C$ is a deformation retraction by nearest-point projection.
- Consider the surface of the tube $S_{t}=\{ x \in \mathbb{R}^{3}:dist(x,C)=r(t) \}$
	- The changing $t$ produces a homotopy  