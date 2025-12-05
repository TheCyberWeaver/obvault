#eth  #exercise 
# Exercise 8.4
##### 1)
**Reflexive**:
$\forall{a\in G}\; (a\cdot e=a)$ and $e\in H$ (because $H$ is a subgroup of $G$, it must contains $e$)
hence $\forall{a\in G} \;	\exists{h\in H}\; (a\cdot h=a)$, (take $h=e$)
so $\forall{a\in G}\; (a\sim a)$
$\implies \sim$ is reflexive

**Symmetric**:
For any $a,b\in G$ that satisfies $a\sim b$
$\exists{h\in H}\; (a\cdot h=b)$ (definition of $\sim$)
$\implies a\cdot h\cdot \hat{h}=b\cdot \hat{h}$ (the inverse of $h$ exists, because $H$ is a group and $h\in H$)
$\implies a\cdot e=b\cdot \hat{h}$
$\implies b\cdot \hat{h}=a$
hence $\exists{h\in H}\; (b\cdot h=a)$, (take $h=\hat{h}$) ($\hat{h}\in H$, because $H$ is a group)
Therefore, according to the definition of $\sim$, $b\sim a$
$\implies\forall{a,b\in G}\; (a\sim b\to b\sim a)$
$\implies \sim$ is symmetric

**Transitive**
For any $a,b,c\in G$ that satisfies $a\sim b$ and $b \sim c$
$\exists{h_{1}\in H}\; (a\cdot h_{1}=b)$ and $\exists{h_{2}\in H}\; (b\cdot h_{2}=c)$ (definition of $\sim$)
Let $h_{3}=h_{1}\cdot h_{2}$ and $h_{3}\in H$ (Since group $H$ is closed and $h_{1}\in H \wedge h_{2}\in H$, $h_{3}$ must also be in $H$)
$\implies c=b\cdot h_{2}=a\cdot h_{1}\cdot h_{2}=a\cdot h_{3}$
$\implies \exists{h\in H}\; (a\cdot h=c)$ (take $h=h_{3}$)
$\implies\forall{a,b,c\in G}\; (a\sim b\wedge b\sim c\to a\sim c)$
$\implies \sim$ is transitive

**Summary**
Since $\sim$ is reflexive, symmetric and transitive, it is an equivalence relation.

##### 2)
We prove $\pi(a\cdot b)=\pi(a'\cdot b')$ by showing that $a\cdot b\sim a'\cdot b'$ (If $a\cdot b\sim a'\cdot b'$, then they must be in the same equivalence class)

Since $a\sim a'$ and $b\sim b'$, there exist $h_{1}$ and $h_{2}$ such that $a\cdot h_{1}=a'$ and $b\cdot h_{2}=b'$
Therefore, $a'\cdot b'=a\cdot h_{1}\cdot b\cdot h_{2}$
$\implies a\cdot b\cdot h_{1}\cdot h_{2}=a'\cdot b'$ (since $G$ is an abelian group)
Let $h_{3}=h_{1}\cdot h_{2}$ and $h_{3}\in H$ (Since group $H$ is closed and $h_{1}\in H \wedge h_{2}\in H$, $h_{3}$ must also be in $H$)
$\implies \exists{h\in H}\; ((a\cdot b)\cdot h=a'\cdot b')$ (take $h=h_{3}$)
$\implies a\cdot b\sim a'\cdot b'$ 
$\implies\pi(a\cdot b)=\pi(a'\cdot b')$

##### 3)
**Associativity**
Let $[a]_{\sim},[b]_{\sim},[c]_{\sim}\in G/H$
$([a]_{\sim}\star[b]_{\sim})\star[c]_{\sim}\overset{ def }{ = }(\pi(a)\star \pi(b))\star \pi(c)=\pi(a\cdot b)\star \pi(c)=\pi((a\cdot b)\cdot c)$
$=\pi(a\cdot (b\cdot c))=\pi(a)\star \pi(b\cdot c)=\pi(a)\star(\pi(b)\star \pi(c))=[a]_{\sim}\star([b]_{\sim}\star[c]_{\sim})$

**Neutral Element**
The neutral element $e'$ in $\langle G/H; \star \rangle$ is $[e]_{\sim}$ (or denoted as $\pi(e)$)
Let $\pi(a)\in G/H$ 
$\pi(a)\star \pi(e)\overset{ def }{ = }\pi(a\cdot e)=\pi(a)$
$\pi(e)\star \pi(a)\overset{ def }{ = }\pi(e\cdot a)=\pi(a)$
This means $\pi(a)\star \pi(e)=\pi(e)\star \pi(a)=\pi(a)$, which proves that $e'$ is the neutral element in $\langle G/H; \star \rangle$

**Inverse**
Let $a\in G$ and $\pi(a)\in G/H$ 
We show that the inverse  $\widehat{\pi(a)}=\pi(\hat{a})$ ($\hat{a}$ exists because $G$ is a group, which means $\pi(\hat{a})$ exists)
$\pi(a)\star \pi(\hat{a})=\pi(a\cdot \hat{a})=\pi(e)=e'$
*Well-definedness*:
To prove the inverse operation is well defined, we show:
For $a,b\in G$ and $\pi(a),\pi(b)\in G/H$, $\pi(a)=\pi(b) \to\widehat{\pi(a)}=\widehat{\pi(b)}$
$\pi(a)=\pi(b)\implies a\sim b\implies \exists{h\in H}\; (a\cdot h=b)\implies\hat{a}\cdot \hat{h}=\hat{b}$
$\implies \hat{a}\sim \hat{b}\implies \pi(\hat{a})=\pi(\hat{b})\implies\widehat{\pi(a)}=\widehat{\pi(b)}$
Therefore the inverse operation is well defined.
##### 4)
Yes, $\pi$ is a homomorphism

# 8.7 Kernel of an homomorphism
![[Pasted image 20251112124514.png]]
We first show that $ker(\phi)=\{ e_{G} \}\implies \phi$ is injective:
$\phi(e_{G})=e_{H}$
Let $a,b\in G$ and satisfy $\phi(a)=\phi(b)$
$\implies \phi(a)\odot\widetilde{\phi(b)}=e_{H}$
$\implies \phi(a)\odot\phi(\hat{b})=e_{H}=\phi(e_{G})$ (because $\widetilde{\phi(b)}=\phi(\hat{b})$, see side proof)
$\implies \phi(a+\hat{b})=e_{H}=\phi(e_{G})$ (property of homomorphism)
Since $e_{G}$ is the only element in $G$ that satisfy $g\in G \wedge\phi(g)=e_{H}$, we must have $a+\hat{b}=e_{G}$
$\implies a+\hat{b}+b=e_{G}+b$
$\implies a+e_{G}=b$
$\implies a=b$
$\implies \forall{a,b\in G}\; (\phi(a)=\phi(b)\to a=b)$
$\implies \phi$ is injective
*side proof*:
$\phi(b)\odot\phi(\hat{b})=\phi(b+\hat{b})=\phi(e_{G})=e_{H}$
$\phi(\hat{b})\odot\phi(b)=\phi(\hat{b}+b)=\phi(e_{G})=e_{H}$
$\implies \phi(\hat{b})$ is an inverse of $\phi(b)$ 
$\implies\widetilde{\phi(b)}=\phi(\hat{b})$


We then show that $\phi$ is injective $\implies ker(\phi)=\{ e_{G} \}$:
$\phi$ is injective
$\implies$ for all $a,b\in G$ $\phi(a)=\phi(b)\to a=b$
Let's assume some $g\in ker(\phi)$ satisfies $g\in G,\phi(g)=e_{H}$
Let $x \in G$
$e_{H}\odot \phi(x)=\phi(g)\odot\phi(x)=\phi(g+x)=\phi(x)$ (property of homomorphism)
$\implies g+x=x$ ($\phi$ is injective)
$\phi(x)\odot e_{H}=\phi(x)\odot\phi(g)=\phi(x+g)=\phi(x)$ (property of homomorphism)
$\implies x+g=x$ ($\phi$ is injective)
Therefore $x+g=g+x=x$
$g$ is a neutral element in $G$ 
$\implies g=e_{G}\implies ker(\phi)=\{ e_{G} \}$

**Conclusion**
Since we proved the statement in both directions, the statement holds.

# 8.8 Conjugacy
![[Pasted image 20251112124532.png]]

We prove $T$ is a subgroup of $G$ by showing $\forall{a,b\in T}\; (a\star b\in H)$ and $\forall{a\in T}\; (\hat{a}\in T)$
We first show $\forall{a,b\in T}\; (a\star b\in T)$
Take $a,b\in T$ and $h\in H$
$\implies a\star h\star \hat{a}\in H\wedge b\star h\star \hat{b}\in H$

$\implies (a\star b)\star h\star \widehat{(a\star b)}\in H$

We then show that $\forall{a\in T}\; (\hat{a}\in T)$
Take $a\in T$ and $h\in H$
$\implies a\star h\star \hat{a}\in H$

