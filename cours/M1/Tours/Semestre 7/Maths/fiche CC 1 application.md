# Fiche Formules Appliquées - Optimisation & Convexité

## 1. FONCTIONS QUADRATIQUES : Identification & Écriture Matricielle

### Application : Vérifier si $h_1(x,y) = x^2 + y^2 + 1$ est quadratique

**Méthode :** Mettre sous forme $\frac{1}{2}x^T Ax + b^T x + c$

$$h_1(x,y) = \frac{1}{2}\begin{pmatrix}x & y\end{pmatrix}\begin{pmatrix}2 & 0\\0 & 2\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix} + 1$$

$$\Rightarrow A = \begin{pmatrix}2 & 0\\0 & 2\end{pmatrix}, \quad b = \begin{pmatrix}0\\0\end{pmatrix}, \quad c = 1 \quad \checkmark \text{ QUADRATIQUE}$$

### Application : Vérifier si $h_2(x,y) = x^2 - 2xy + 5y^2 + y$ est quadratique

$$h_2(x,y) = \frac{1}{2}\begin{pmatrix}x & y\end{pmatrix}\begin{pmatrix}2 & -2\\-2 & 10\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix} + \begin{pmatrix}0 & 1\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix}$$

$$\Rightarrow A = \begin{pmatrix}2 & -2\\-2 & 10\end{pmatrix}, \quad b = \begin{pmatrix}0\\1\end{pmatrix}, \quad c = 0 \quad \checkmark \text{ QUADRATIQUE}$$

### Application : $f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}$

$$f(x,y) = \frac{1}{2}\begin{pmatrix}x & y\end{pmatrix}\begin{pmatrix}3 & 2\\2 & 2\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix} + \begin{pmatrix}-1 & -2\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix} + \frac{5}{2}$$

$$A = \begin{pmatrix}3 & 2\\2 & 2\end{pmatrix} \quad b = \begin{pmatrix}-1\\-2\end{pmatrix} \quad c = \frac{5}{2}$$

---

## 2. CONVEXITÉ : Test par Valeurs Propres

### Application : $g(x,y) = x^2 + y^2 + xy$ est-elle convexe ?

**Étape 1 :** Calculer la Hessienne

$$H_g = \begin{pmatrix}2 & 1\\1 & 2\end{pmatrix}$$

**Étape 2 :** Polynôme caractéristique

$$\det(H - \lambda I) = (2-\lambda)^2 - 1 = (1-\lambda)(3-\lambda)$$

$$\lambda_1 = 1 > 0 \quad \lambda_2 = 3 > 0$$

**Conclusion :** Toutes $\lambda > 0 \Rightarrow$ **STRICTEMENT CONVEXE** $\checkmark$

### Application : $f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}$

**Matrice A :**

$$A = \begin{pmatrix}3 & 2\\2 & 2\end{pmatrix}$$

**Valeurs propres :**

$$\det(A - \lambda I) = \lambda^2 - 5\lambda + 2 = 0$$

$$\lambda_{1,2} = \frac{5 \pm \sqrt{17}}{2}$$

$$\lambda_1 = \frac{5 + \sqrt{17}}{2} \approx 4.56 > 0$$

$$\lambda_2 = \frac{5 - \sqrt{17}}{2} \approx 0.44 > 0$$

**Conclusion :** **STRICTEMENT CONVEXE** $\Rightarrow$ possède un minimum unique

---

## 3. MINIMUM GLOBAL : Résolution de $\nabla f = 0$

### Application : Trouver le minimum de $f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}$

**Étape 1 :** Calculer le gradient

$$\nabla f = \begin{pmatrix}3x + 2y - 1\\2x + 2y - 2\end{pmatrix}$$

**Étape 2 :** Résoudre $\nabla f = 0$

$$\begin{cases}3x + 2y = 1 & (L_1)\\2x + 2y = 2 & (L_2)\end{cases}$$

$L_2 \Rightarrow x + y = 1 \Rightarrow y = 1 - x$

$L_1 \Rightarrow 3x + 2(1-x) = 1$

$$\Rightarrow 3x + 2 - 2x = 1$$

$$\Rightarrow x = -1$$

$$\Rightarrow y = 1 - (-1) = 2$$

**Étape 3 :** Point critique

$$X^* = (-1, 2)$$

**Étape 4 :** Calculer $f(X^*)$

$$f(-1, 2) = \frac{3}{2} + 4 - 4 + 1 - 4 + \frac{5}{2}$$

$$= \left(\frac{3}{2} + \frac{5}{2}\right) + (4 - 4 + 1 - 4)$$

$$= 4 - 3 = 1$$

**Conclusion :** Minimum global = **1** en **(-1, 2)**

---

## 4. POINTS CRITIQUES : Classification par $\det(H)$

### Application : $f(x,y) = xe^y + ye^x$ - Nature du point $(-1, -1)$

**Étape 1 :** Calculer la Hessienne

$$H = \begin{pmatrix}ye^x & e^y + e^x\\e^y + e^x & xe^y\end{pmatrix}$$

**Étape 2 :** Évaluer en $(-1, -1)$

$$H(-1,-1) = \begin{pmatrix}-e^{-1} & 2e^{-1}\\2e^{-1} & -e^{-1}\end{pmatrix}$$

**Étape 3 :** Calculer $D$

$$D = (-e^{-1})^2 - (2e^{-1})^2$$

$$= e^{-2} - 4e^{-2}$$

$$= -3e^{-2} < 0$$

**Conclusion :** $D < 0 \Rightarrow$ **POINT SELLE** $\checkmark$

---

## 5. CONVEXITÉ PAR COMPOSITION : Méthode du Logarithme

### Application : $g(x,y) = \frac{e^{x+y}}{\sqrt{x+y}}$ sur $\{x+y > 0\}$

**Étape 1 :** Prendre le logarithme

$$\ln(g) = \ln(e^{x+y}) - \ln(\sqrt{x+y})$$

$$= x + y - \frac{1}{2}\ln(x+y)$$

**Étape 2 :** Analyser chaque terme

- $(x,y) \mapsto x + y$ : AFFINE $\Rightarrow$ convexe
- $t \mapsto -\frac{1}{2}\ln(t)$ : CONVEXE sur $(0,+\infty)$

**Étape 3 :** Somme de convexes

$$\ln(g) = \text{convexe} + \text{convexe} \Rightarrow \text{CONVEXE}$$

**Étape 4 :** Conclusion

$$\ln \text{ strictement croissant} + \ln(g) \text{ convexe} \Rightarrow g \text{ CONVEXE } \checkmark$$

---

## 6. PLAN TANGENT : Équation & Position

### Application : Plan tangent à $g(x,y) = \frac{e^{x+y}}{\sqrt{x+y}}$ en $(1,0)$

**Étape 1 :** Calculer $g(1,0)$

$$g(1,0) = \frac{e^{1+0}}{\sqrt{1+0}} = e$$

**Étape 2 :** Calculer les dérivées partielles

Avec $t = x + y$ :

$$\frac{\partial g}{\partial x} = \frac{(2t - 1)e^t}{2t^{3/2}}, \quad \frac{\partial g}{\partial y} = \frac{(2t - 1)e^t}{2t^{3/2}}$$

En $(1,0)$ avec $t = 1$ :

$$\frac{\partial g}{\partial x}(1,0) = \frac{(2 \cdot 1 - 1)e^1}{2 \cdot 1^{3/2}} = \frac{e}{2}$$

$$\frac{\partial g}{\partial y}(1,0) = \frac{e}{2}$$

**Étape 3 :** Équation du plan tangent

$$z = g(1,0) + \frac{\partial g}{\partial x}(x-1) + \frac{\partial g}{\partial y}(y-0)$$

$$z = e + \frac{e}{2}(x-1) + \frac{e}{2}y$$

$$z = \frac{e}{2}x + \frac{e}{2}y + \frac{e}{2}$$

**Étape 4 :** Position relative

$$g \text{ convexe} \Rightarrow \text{Surface AU-DESSUS du plan tangent } \checkmark$$

---

## 7. COERCIVITÉ : Minoration par $\|x\|^2$

### Application : $g(x,y) = x^2 + y^2 + xy$ est-elle coercive ?

**Méthode 1 - Complétion du carré :**

$$g(x,y) = \left(\frac{x + y}{\sqrt{2}}\right)^2 + \frac{x^2}{2} + \frac{y^2}{2}$$

Tous les termes $\geq 0$, donc :

$$g(x,y) \geq \frac{x^2}{2} + \frac{y^2}{2} = \frac{1}{2}(x^2 + y^2) = \frac{1}{2}\|(x,y)\|^2$$

**Conclusion :**

$$g(x,y) \geq \frac{1}{2}\|(x,y)\|^2 \to +\infty \text{ quand } \|(x,y)\| \to +\infty$$

$$\Rightarrow g \text{ est COERCIVE } \checkmark$$

**Théorème appliqué :**

$$\text{Coercive} + \text{Strictement convexe} \Rightarrow \text{MINIMUM UNIQUE}$$

$$g \text{ possède un unique minimum global}$$

---

## 8. INÉGALITÉ DE JENSEN : Applications

### Application : $f(x) = \frac{1}{1+e^x}$ - Convexité et Jensen

**Étape 1 :** Étude de convexité

$$f'(x) = \frac{-e^x}{(1+e^x)^2}$$

$$f''(x) = \frac{e^x(e^x - 1)}{(1+e^x)^3}$$

Signe de $f''$ :

- $x > 0$ : $e^x - 1 > 0 \Rightarrow f'' > 0 \Rightarrow$ CONVEXE sur $]0,+\infty[$
- $x < 0$ : $e^x - 1 < 0 \Rightarrow f'' < 0 \Rightarrow$ CONCAVE sur $]-\infty,0[$

**Étape 2 :** Application de Jensen pour $x_1,\ldots,x_n \geq 1$

**Objectif :** Montrer que

$$\frac{n}{1 + \sqrt[n]{x_1 \cdots x_n}} \leq \sum_{k=1}^{n} \frac{1}{1+x_k}$$

**Preuve :**

Poser $y_i = \ln(x_i) \geq 0$ (car $x_i \geq 1$)

Sur $\mathbb{R}_+$, $f$ est convexe. Jensen avec $\lambda_i = \frac{1}{n}$ :

$$f\left(\frac{1}{n}\sum y_k\right) \leq \frac{1}{n}\sum f(y_k)$$

**Membre gauche :**

$$f\left(\frac{1}{n}\sum\ln(x_k)\right) = f\left(\ln\left(\sqrt[n]{x_1 \cdots x_n}\right)\right) = \frac{1}{1 + \sqrt[n]{x_1 \cdots x_n}}$$

**Membre droit :**

$$\frac{1}{n}\sum f(\ln(x_k)) = \frac{1}{n}\sum \frac{1}{1+x_k}$$

Multiplier par $n$ $\Rightarrow$ Résultat $\checkmark$

---

## 9. GRADIENT À PAS FIXE (GPF)

### Application : $f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}$

**Paramètres :** $X^{(0)} = (0,0)$, $\alpha = \frac{1}{2}$

**Étape 1 :** Calculer $\nabla f(0,0)$

$$\nabla f(0,0) = \begin{pmatrix}3 \cdot 0 + 2 \cdot 0 - 1\\2 \cdot 0 + 2 \cdot 0 - 2\end{pmatrix} = \begin{pmatrix}-1\\-2\end{pmatrix}$$

**Étape 2 :** Formule GPF

$$X^{(1)} = X^{(0)} - \alpha\nabla f(X^{(0)})$$

$$= \begin{pmatrix}0\\0\end{pmatrix} - \frac{1}{2}\begin{pmatrix}-1\\-2\end{pmatrix}$$

$$= \begin{pmatrix}0\\0\end{pmatrix} + \begin{pmatrix}0.5\\1\end{pmatrix}$$

$$= \begin{pmatrix}0.5\\1\end{pmatrix}$$

**Étape 3 :** Calculer $f(X^{(1)})$

$$f(0.5, 1) = \frac{3}{2} \cdot (0.5)^2 + 1^2 + 2 \cdot (0.5) \cdot 1 - 0.5 - 2 \cdot 1 + \frac{5}{2}$$

$$= 0.375 + 1 + 1 - 0.5 - 2 + 2.5$$

$$= 2.375$$

**Résultat :** $X^{(1)} = (0.5, 1)$, $f(X^{(1)}) = 2.375$

---

## 10. GRADIENT À PAS OPTIMAL (GPO)

### Application : Même fonction $f$, même point de départ

**Étape 1 :** Direction de descente

$$w^{(0)} = -\nabla f(0,0) = \begin{pmatrix}1\\2\end{pmatrix}$$

**Étape 2 :** Paramétrage

$$X(\alpha) = X^{(0)} + \alpha w^{(0)} = \begin{pmatrix}0\\0\end{pmatrix} + \alpha\begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}\alpha\\2\alpha\end{pmatrix}$$

**Étape 3 :** Former $\varphi(\alpha) = f(\alpha, 2\alpha)$

$$\varphi(\alpha) = \frac{3}{2}\alpha^2 + (2\alpha)^2 + 2\alpha \cdot (2\alpha) - \alpha - 2 \cdot (2\alpha) + \frac{5}{2}$$

$$= \frac{3}{2}\alpha^2 + 4\alpha^2 + 4\alpha^2 - \alpha - 4\alpha + \frac{5}{2}$$

$$= \frac{19}{2}\alpha^2 - 5\alpha + \frac{5}{2}$$

**Étape 4 :** Minimiser $\varphi$

$$\varphi'(\alpha) = 19\alpha - 5 = 0$$

$$\Rightarrow \alpha^* = \frac{5}{19}$$

**Étape 5 :** Calculer $X^{(1)}$

$$X^{(1)} = \begin{pmatrix}5/19\\10/19\end{pmatrix}$$

**Étape 6 :** Calculer $f(X^{(1)})$

$$f\left(\frac{5}{19}, \frac{10}{19}\right) = \frac{665}{361} \approx 1.8438$$

**Résultat :** $X^{(1)} = \left(\frac{5}{19}, \frac{10}{19}\right)$, $f(X^{(1)}) \approx 1.8438$

---

## 11. COMPARAISON GPF vs GPO

### Résultats sur $f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}$

**Minimum global :** $X^* = (-1, 2)$, $f(X^*) = 1$

**GPF** ($\alpha = \frac{1}{2}$) :
- $X^{(1)} = (0.5, 1)$
- $f(X^{(1)}) = 2.375$
- Écart au minimum : $1.375$

**GPO** :
- $X^{(1)} = \left(\frac{5}{19}, \frac{10}{19}\right) \approx (0.263, 0.526)$
- $f(X^{(1)}) \approx 1.8438$
- Écart au minimum : $0.8438$

**Conclusion :** GPO converge PLUS VITE (écart réduit de 38%) $\checkmark$

---

## 12. CHECKLIST MÉTHODE COMPLÈTE

### Exemple traité : $g(x,y) = x^2 + y^2 + xy$

**ÉTAPE 1 : Identification**
- Quadratique homogène
- Domaine : $\mathbb{R}^2$

**ÉTAPE 2 : Convexité**

$$H_g = \begin{pmatrix}2 & 1\\1 & 2\end{pmatrix} \Rightarrow \lambda_1=1, \lambda_2=3 \Rightarrow \text{STRICTEMENT CONVEXE } \checkmark$$

**ÉTAPE 3 : Coercivité**

$$g(x,y) \geq \frac{1}{2}\|(x,y)\|^2 \Rightarrow \text{COERCIVE } \checkmark$$

**ÉTAPE 4 : Minimum unique**

$$\text{Convexe} + \text{Coercive} \Rightarrow \exists! \text{ minimum global}$$

**ÉTAPE 5 : Trouver le minimum**

$$\nabla g = \begin{pmatrix}2x + y\\2y + x\end{pmatrix} = \begin{pmatrix}0\\0\end{pmatrix} \Rightarrow X^* = (0, 0)$$

**ÉTAPE 6 : Valeur**

$$g(0,0) = 0 \Rightarrow \text{Minimum} = 0 \checkmark$$

---

## FORMULES ESSENTIELLES (À CONNAÎTRE PAR COEUR)

$$\boxed{\nabla f = Ax + b} \quad \text{(gradient quadratique)}$$

$$\boxed{D = f_{xx} \cdot f_{yy} - (f_{xy})^2} \quad \text{(classification points critiques)}$$

$$\boxed{\text{Coercive} + \text{Strictement convexe} \Rightarrow \text{min unique}}$$

$$\boxed{\alpha^* = \frac{\|\nabla f\|^2}{\nabla f^T A \nabla f}} \quad \text{(pas optimal GPO)}$$

$$\boxed{f\left(\sum\lambda_i x_i\right) \leq \sum\lambda_i f(x_i)} \quad \text{(Jensen convexe)}$$

$$\boxed{\ln(g) \text{ convexe} + \ln \text{ croissant} \Rightarrow g \text{ convexe}}$$