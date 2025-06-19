## Definition
   For an $m\times n$ matrix $A$ representing a linear map  
   $$  
     A : \mathbb{R}^n \to \mathbb{R}^m,\quad x \mapsto Ax,  
   $$  
   the **kernel** (or **null space**) is  
   $$  
     \ker(A) = \{\,x\in\mathbb{R}^n \mid A x = 0\}.  
   $$

## Properties  
   - $\ker(A)$ is a subspace of $\mathbb{R}^n$.  
   - The **nullity** is $\dim\bigl(\ker(A)\bigr)$.  
   - **Rank–Nullity Theorem**:  $$  
       \dim\bigl(\ker(A)\bigr) + rank(A) = n.  
     $$

## Relation to Homomorphism  
   In abstract algebra, the [[Section 13 Homomorphisms#13.13 Definition $Ker( phi)$|kernel of a homomorphism]] $\varphi$ is $\{x\mid \varphi(x)=0\}$. A matrix $A$ is a linear map, so its kernel matches this definition:  
   $$  
     \ker(A) = \{\,x \mid A(x)=0\}.  
   $$

## Geometric Interpretation  
   The kernel describes the directions that are “flattened” to $0$ by the linear map. A larger nullity means more information is collapsed.
