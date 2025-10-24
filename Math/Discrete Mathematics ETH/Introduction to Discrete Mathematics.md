---
email: dm25-team@lists.inf.ethz.ch
---
#eth 
# Aussagen Implikation
Aussagen:
S="101 ist eine Primzahl"
T="Es gibt unendlich viele Primzahlzwillinge"
Implikation
$$
T\Longrightarrow S
$$

> [!Warning]
> Diese Aussage ist nicht prüfbar


## The Punctured Chessboard

$P(k)$=Ein $k*k$ Schachbrett auf dem ein beliebiges Feld blockiert ist, kann vollständig mit L-förmigen Bausteinen überdeckt werden.

**Theorem:**
$$ 
k^{2}-1\not\equiv_{3}0\Longrightarrow P(k)=0 
$$
bessere Formulierung: $3\mid k\Longrightarrow P(k)=0$

$P(1)=1$
$P(2)=1$
$P(3)=0$ (nach Theorem)
$P(4)=1$ (divide the board into 4 $2*2$ board)
- Fülle den Quadranten mit blockiertem Feld mit L-Stück
- Setze L in Mitte
- Fülle andere Quadranten (nutze P(k)=1)
$$P(k)=1\Longrightarrow P(2k)=1$$
# Beispiel für falschen Beweis
**Theorem:** 
Wenn in einer Menge p von n Planeten 1 Planet bewohnt ist, so sind es alle Planeten
$n=1$ : gilt
$n\to n+1$ : Seien n Planeten $p_{1},\dots,p_{n}$ gegeben, wobei oBdA $p_{1}$ bewohnt sei. Dann sind nach Voraus $p_{1},\dots,p_{n}$ und $p_{1},p_{3},\dots,p_{n+1}$ bewohnt
