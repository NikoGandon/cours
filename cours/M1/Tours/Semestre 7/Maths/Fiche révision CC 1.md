# **Fonctions quadratiques**

## **Forme générale**

$$
f(x) = \frac{1}{2} x^T A x + b^T x + c
$$

- $A$ : matrice symétrique ($n \times n$)
- $b$ : vecteur ($n \times 1$)
- $c$ : constante

### Exemple

$$
f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}
$$

**Écriture matricielle :**

$$
f(x,y) = \frac{1}{2} \begin{pmatrix} x & y \end{pmatrix}
\begin{pmatrix} 3 & 2 \\ 2 & 2 \end{pmatrix}
\begin{pmatrix} x \\ y \end{pmatrix}
+ \begin{pmatrix} -1 & -2 \end{pmatrix}
\begin{pmatrix} x \\ y \end{pmatrix} + \frac{5}{2}
$$

## **Gradient**

$$
\nabla f(x) = Ax + b
$$

**Exemple :** Si $f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}$

$$
\nabla f = \begin{pmatrix} 3x + 2y - 1 \\ 2x + 2y - 2 \end{pmatrix}
$$

## **Hessienne (constante pour les quadratiques)**

$$
H_f = A
$$

## **Convexité**

- **A définie positive** (toutes valeurs propres $> 0$) $\Rightarrow$ **$f$ strictement convexe**

- **A semi-définie positive** (toutes valeurs propres $\geq 0$) $\Rightarrow$ **$f$ convexe**

### **Test rapide pour matrices 2×2**

Pour $A = \begin{pmatrix} a & b \\ b & d \end{pmatrix}$ :

- **Définie positive** $\Longleftrightarrow$ $a > 0$ ET $\det(A) = ad - b^2 > 0$

- **Semi-définie positive** $\Longleftrightarrow$ $a \geq 0$ ET $\det(A) \geq 0$

## **Minimum global**

Pour une fonction quadratique strictement convexe :

$$
\nabla f(x^*) = 0 \quad \Leftrightarrow \quad Ax^* + b = 0 \quad \Leftrightarrow \quad x^* = -A^{-1}b
$$

### **Exemple complet**

$$
f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}
$$

**1. Vérifier convexité :**

$$
A = \begin{pmatrix} 3 & 2 \\ 2 & 2 \end{pmatrix}, \quad \det(A-\lambda I) = \lambda^2 - 5\lambda + 2
$$

$$
\lambda_{1,2} = \frac{5 \pm \sqrt{17}}{2} \quad \text{(toutes deux > 0)} \quad \checkmark
$$

**2. Trouver le minimum :**

$$
\nabla f = 0 \Leftrightarrow \begin{cases} 3x + 2y - 1 = 0 \\ 2x + 2y - 2 = 0 \end{cases}
\Leftrightarrow x = -1, \, y = 2
$$

**3. Calculer f(x*) :**

$$
f(-1, 2) = \frac{3}{2} + 4 - 4 + 1 - 4 + \frac{5}{2} = 1
$$

---

# **Convexité en plusieurs variables**

## **Test via la Hessienne**

### **Matrice Hessienne**

$$
H_f = \begin{pmatrix}
f_{xx} & f_{xy} \\
f_{xy} & f_{yy}
\end{pmatrix}
$$

### **Critères de convexité**

- **H définie positive** (det(H) > 0 ET $f_{xx} > 0$) $\Rightarrow$ **strictement convexe**

- **H semi-définie positive** (det(H) $\geq$ 0 ET $f_{xx} \geq 0$) $\Rightarrow$ **convexe**

### **Exemple : $g(x,y) = x^2 + y^2 + xy$**

$$
H_g = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}
$$

$$
\det(H - \lambda I) = (2-\lambda)^2 - 1 = (1-\lambda)(3-\lambda)
$$

Valeurs propres : $\lambda_1 = 1 > 0$, $\lambda_2 = 3 > 0$ $\Rightarrow$ **strictement convexe**

## **Plan tangent**

$$
z = f(x_0, y_0) + f_x(x_0, y_0)(x - x_0) + f_y(x_0, y_0)(y - y_0)
$$

### **Position relative**

- **f convexe** $\Rightarrow$ surface **au-dessus** du plan tangent

- **f concave** $\Rightarrow$ surface **en dessous** du plan tangent

### **Exemple : $g(x,y) = \frac{e^{x+y}}{\sqrt{x+y}}$ au point (1,0)**

$$
g(1,0) = e, \quad g_x(1,0) = g_y(1,0) = \frac{e}{2}
$$

$$
z = e + \frac{e}{2}(x-1) + \frac{e}{2}y = \frac{e}{2}x + \frac{e}{2}y + \frac{e}{2}
$$

Comme g est convexe, la surface est **au-dessus** du plan tangent.

## **Règles de composition**

### **Composition avec fonction affine**

- Si $h(u)$ convexe et $u = g(x)$ affine $\Rightarrow$ $h(g(x))$ convexe

### **Composition via logarithme**

- Si $g > 0$ et $\ln(g)$ convexe $\Rightarrow$ $g$ convexe

- Car $\ln$ strictement croissant

### **Exemple : $g(x,y) = \frac{e^{x+y}}{\sqrt{x+y}}$**

$$
\ln(g) = x + y - \frac{1}{2}\ln(x+y)
$$

- $(x,y) \mapsto x+y$ est affine (donc convexe)

- $t \mapsto -\frac{1}{2}\ln(t)$ est convexe sur $(0,+\infty)$

- Somme de fonctions convexes $\Rightarrow$ $\ln(g)$ convexe $\Rightarrow$ **g convexe** 

---

# **Points critiques & nature**

## **Méthode générale**

### **Étape 1 : Trouver les points critiques**

$$
\nabla f = 0 \Leftrightarrow \begin{cases}
\frac{\partial f}{\partial x} = 0 \\
\frac{\partial f}{\partial y} = 0
\end{cases}
$$

### **Étape 2 : Calculer la Hessienne au point critique**

$$
H = \begin{pmatrix} f_{xx} & f_{xy} \\ f_{xy} & f_{yy} \end{pmatrix}
$$

### **Étape 3 : Déterminer la nature**

$$
D = \det(H) = f_{xx} f_{yy} - (f_{xy})^2
$$

| Condition               | Nature                 |
| ----------------------- | ---------------------- |
| $D > 0$ et $f_{xx} > 0$ | **Minimum local**      |
| $D > 0$ et $f_{xx} < 0$ | **Maximum local**      |
| $D < 0$                 | **Point selle**        |
| $D = 0$                 | **Test non conclusif** |

## **Exemple complet : $f(x,y) = xe^y + ye^x$**

### **1. Points critiques**

$$
\nabla f = \begin{pmatrix} e^y + ye^x \\ xe^y + e^x \end{pmatrix} = 0
$$

En multipliant la 1ère par $x$ et la 2ème par $y$ :

$$
\begin{cases}
xe^y + xye^x = 0 \\
xye^y + ye^x = 0
\end{cases}
\Rightarrow xe^y = ye^x \Rightarrow \boxed{xy = 1}
$$

En injectant dans la 1ère équation :

$$
e^y = -ye^x \Rightarrow y = \frac{1}{x} \Rightarrow e^{1/x} = -\frac{1}{x}e^x
$$

$$
\Rightarrow \boxed{xe^{1/x} + e^x = 0}
$$

### **2. Résolution de $\varphi(x) = xe^{1/x} + e^x = 0$**

**Test de x = -1 :**

$$
\varphi(-1) = (-1)e^{-1} + e^{-1} = 0 \quad \checkmark
$$

**Monotonie de $\varphi$ pour x < 0 :**

$$
\varphi'(x) = e^{1/x}\left(1 - \frac{1}{x^2}\right) + e^x
$$

Pour $x < 0$ : $e^{1/x} > 0$, $1 - \frac{1}{x^2} < 0$ mais la somme reste > 0

$$
\Rightarrow \varphi \text{ strictement croissante} \Rightarrow \text{unique solution}
$$

**Conclusion :** Point critique unique : $\boxed{(-1, -1)}$

### **3. Nature du point critique**

$$
H = \begin{pmatrix} ye^x & e^y + e^x \\ e^y + e^x & xe^y \end{pmatrix}
$$

En $(-1, -1)$ :

$$
H = \begin{pmatrix} -e^{-1} & 2e^{-1} \\ 2e^{-1} & -e^{-1} \end{pmatrix}
$$

$$
D = (-e^{-1})^2 - (2e^{-1})^2 = e^{-2} - 4e^{-2} = -3e^{-2} < 0
$$

**Conclusion :** $(-1, -1)$ est un **point selle**

---

# **Convexité (1 variable) & Jensen**

## **Test de convexité en 1D**

$$
f''(x) > 0 \quad \Rightarrow \quad \text{f strictement convexe}
$$

$$
f''(x) < 0 \quad \Rightarrow \quad \text{f concave}
$$

$$
f''(x) = 0 \quad \Rightarrow \quad \text{point d'inflexion potentiel}
$$

## **Inégalité de Jensen**

### **Pour fonction convexe**

Si $f$ convexe et $\lambda_i \geq 0$ avec $\sum_{i=1}^n \lambda_i = 1$ :

$$
f\left(\sum_{i=1}^n \lambda_i x_i\right) \leq \sum_{i=1}^n \lambda_i f(x_i)
$$

### **Pour fonction concave**

Si $f$ concave :

$$
f\left(\sum_{i=1}^n \lambda_i x_i\right) \geq \sum_{i=1}^n \lambda_i f(x_i)
$$

### **Cas particulier (moyenne arithmétique)**

Avec $\lambda_i = \frac{1}{n}$ :

$$
f\left(\frac{1}{n}\sum_{i=1}^n x_i\right) \leq \frac{1}{n}\sum_{i=1}^n f(x_i) \quad \text{(si f convexe)}
$$

## **Exemple complet : $f(x) = \frac{1}{1+e^x}$**

### **1. Domaine**

$$
D_f = \mathbb{R} \quad \text{(car } 1+e^x > 0 \text{ toujours)}
$$

### **2. Convexité/Concavité**

$$
f'(x) = \frac{-e^x}{(1+e^x)^2}
$$

$$
f''(x) = \frac{-e^x(1+e^x)^2 + e^x \cdot 2(1+e^x)e^x}{(1+e^x)^4} = \frac{e^x(e^x - 1)}{(1+e^x)^3}
$$

**Signe de f''(x) :**

$$
\begin{cases}
e^x - 1 > 0 \Leftrightarrow x > 0 & \Rightarrow f \text{ convexe sur } ]0, +\infty[ \\
e^x - 1 < 0 \Leftrightarrow x < 0 & \Rightarrow f \text{ concave sur } ]-\infty, 0[
\end{cases}
$$

### **3. Application de Jensen**

**Objectif :** Montrer que pour $x_1, \ldots, x_n \geq 1$ :

$$
\frac{n}{1 + \sqrt[n]{x_1 \cdots x_n}} \leq \sum_{k=1}^n \frac{1}{1+x_k}
$$

**Démonstration :**

Posons $y_i = \ln(x_i) \geq 0$ (car $x_i \geq 1$).

Sur $\mathbb{R}_+$, f est **convexe**. Appliquons Jensen avec $\lambda_i = \frac{1}{n}$ :

$$
f\left(\frac{1}{n}\sum_{k=1}^n y_k\right) \leq \frac{1}{n}\sum_{k=1}^n f(y_k)
$$

**Membre gauche :**

$$
f\left(\frac{1}{n}\sum \ln(x_k)\right) = f\left(\ln\sqrt[n]{x_1 \cdots x_n}\right) = \frac{1}{1 + \sqrt[n]{x_1 \cdots x_n}}
$$

**Membre droit :**

$$
\frac{1}{n}\sum f(\ln(x_k)) = \frac{1}{n}\sum \frac{1}{1+e^{\ln(x_k)}} = \frac{1}{n}\sum \frac{1}{1+x_k}
$$

En multipliant par $n$ :

$$
\boxed{\frac{n}{1 + \sqrt[n]{x_1 \cdots x_n}} \leq \sum_{k=1}^n \frac{1}{1+x_k}}
$$

---

# **Coercivité**

## **Définition**

Une fonction $f : \mathbb{R}^n \to \mathbb{R}$ est **coercive** si :

$$
\|x\| \to +\infty \quad \Rightarrow \quad f(x) \to +\infty
$$

## **Méthode de vérification**

Trouver une minoration du type :

$$
f(x) \geq c\|x\|^2 \quad \text{avec } c > 0
$$

## **Exemple : $g(x,y) = x^2 + y^2 + xy$**

### **Méthode 1 : Minoration directe**

$$
g(x,y) = \left(\frac{x+y}{\sqrt{2}}\right)^2 + \frac{x^2}{2} + \frac{y^2}{2}
$$

Comme tous les termes sont positifs :

$$
g(x,y) \geq \frac{x^2}{2} + \frac{y^2}{2} = \frac{1}{2}(x^2 + y^2) = \frac{1}{2}\|(x,y)\|^2
$$

Donc quand $\|(x,y)\| \to +\infty$, on a $g(x,y) \to +\infty$ $\Rightarrow$ **g coercive**

### **Méthode 2 : Via les valeurs propres**

Si $g(x) = \frac{1}{2}x^T A x$ avec A définie positive :

$$
\lambda_{\min}(A) \|x\|^2 \leq x^T A x \leq \lambda_{\max}(A) \|x\|^2
$$

Ici $\lambda_{\min} = 1 > 0$ donc g est coercive.

## **Conséquence fondamentale**

$$
\boxed{\text{Coercive + Strictement convexe} \Rightarrow \text{Minimum global UNIQUE}}
$$

### **Justification**

- **Coercivité** $\Rightarrow$ minimum global existe (f tend vers $+\infty$ aux bords)

- **Stricte convexité** $\Rightarrow$ unicité du minimum

---

# **Méthodes du gradient**

## **Principe général**

Pour minimiser $f : \mathbb{R}^n \to \mathbb{R}$ :

$$
X^{(k+1)} = X^{(k)} - \alpha_k \nabla f(X^{(k)})
$$

où $\alpha_k > 0$ est le **pas de descente**.

---

## **Gradient à Pas Fixe (GPF)**

### **Formule**

$$
X^{(k+1)} = X^{(k)} - \alpha \nabla f(X^{(k)})
$$

avec $\alpha > 0$ constant.

### **Condition de convergence (fonctions quadratiques)**

$$
0 < \alpha < \frac{2}{\lambda_{\max}(A)}
$$

où $A$ est la matrice Hessienne.

### **Exemple**

$$
f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}
$$

**Départ :** $X^{(0)} = (0, 0)$, **Pas :** $\alpha = \frac{1}{2}$

**Calcul :**

$$
\nabla f(0,0) = \begin{pmatrix} -1 \\ -2 \end{pmatrix}
$$

$$
X^{(1)} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} - \frac{1}{2}\begin{pmatrix} -1 \\ -2 \end{pmatrix} = \begin{pmatrix} 0.5 \\ 1 \end{pmatrix}
$$

$$
f(X^{(1)}) = f(0.5, 1) = 2.375
$$

---

## **Gradient à Pas Optimal (GPO)**

### **Principe**

À chaque itération, on minimise :

$$
\varphi(\alpha) = f(X^{(k)} - \alpha \nabla f(X^{(k)}))
$$

### **Formule pour fonctions quadratiques**

Si $f(x) = \frac{1}{2}x^T A x + b^T x + c$ :

$$
\alpha^* = \frac{\|\nabla f(X^{(k)})\|^2}{\nabla f(X^{(k)})^T A \nabla f(X^{(k)})}
$$

### **Exemple (suite)**

$$
\nabla f(0,0) = \begin{pmatrix} -1 \\ -2 \end{pmatrix}, \quad w^{(0)} = -\nabla f = \begin{pmatrix} 1 \\ 2 \end{pmatrix}
$$

**Paramétrage :**

$$
X(\alpha) = (0,0) + \alpha(1, 2) = (\alpha, 2\alpha)
$$

**Substitution dans f :**

$$
\varphi(\alpha) = f(\alpha, 2\alpha) = \frac{3}{2}\alpha^2 + 4\alpha^2 + 4\alpha^2 - \alpha - 4\alpha + \frac{5}{2}
$$

$$
= \frac{19}{2}\alpha^2 - 5\alpha + \frac{5}{2}
$$

**Minimisation :**

$$
\varphi'(\alpha) = 19\alpha - 5 = 0 \quad \Rightarrow \quad \alpha^* = \frac{5}{19}
$$

**Itéré optimal :**

$$
X^{(1)} = \left(\frac{5}{19}, \frac{10}{19}\right)
$$

$$
f(X^{(1)}) = \frac{665}{361} \approx 1.8438
$$

---

## **Comparaison GPF vs GPO**

| Critère | GPF | GPO |
|---------|-----|-----|
| **Complexité** | Simple | Plus coûteux |
| **Convergence** | Linéaire | Plus rapide |
| **Exemple** | f(0.5, 1) = **2.375** | f(5/19, 10/19) $\approx$ **1.8438** |

**Conclusion :** GPO converge plus vite vers le minimum (f* = 1) 

---

# **Dérivées usuelles**

## **Fonctions 1D**

| Fonction | Dérivée |
|----------|---------|
| $x^n$ | $nx^{n-1}$ |
| $e^x$ | $e^x$ |
| $\ln(x)$ | $\frac{1}{x}$ |
| $\sqrt{x}$ | $\frac{1}{2\sqrt{x}}$ |
| $\frac{1}{x}$ | $-\frac{1}{x^2}$ |
| $e^{ax}$ | $ae^{ax}$ |

## **Fonctions 2D**

| Fonction | $\frac{\partial f}{\partial x}$ | $\frac{\partial f}{\partial y}$ |
|----------|---------|---------|
| $x^2 + y^2$ | $2x$ | $2y$ |
| $xy$ | $y$ | $x$ |
| $2xy$ | $2y$ | $2x$ |
| $e^{x+y}$ | $e^{x+y}$ | $e^{x+y}$ |
| $\ln(x+y)$ | $\frac{1}{x+y}$ | $\frac{1}{x+y}$ |
| $\frac{1}{\sqrt{x+y}}$ | $-\frac{1}{2(x+y)^{3/2}}$ | $-\frac{1}{2(x+y)^{3/2}}$ |
| $xe^y$ | $e^y$ | $xe^y$ |
| $ye^x$ | $ye^x$ | $e^x$ |

## **Hessienne**

$$
H_f = \begin{pmatrix}
\frac{\partial^2 f}{\partial x^2} & \frac{\partial^2 f}{\partial x \partial y} \\
\frac{\partial^2 f}{\partial y \partial x} & \frac{\partial^2 f}{\partial y^2}
\end{pmatrix}
$$

**Théorème de Schwarz :** Si f est $C^2$, alors $f_{xy} = f_{yx}$

---

# **Astuces de calcul**

## **Valeurs propres matrice 2×2**

Pour $A = \begin{pmatrix} a & b \\ b & d \end{pmatrix}$ :

$$
\det(A - \lambda I) = \lambda^2 - (a+d)\lambda + (ad-b^2) = 0
$$

$$
\lambda_{1,2} = \frac{(a+d) \pm \sqrt{(a+d)^2 - 4(ad-b^2)}}{2}
$$

**Simplification :**

$$
\Delta = (a+d)^2 - 4(ad-b^2) = (a-d)^2 + 4b^2
$$

## **Test rapide de convexité d'un domaine**

Un ensemble $D \subset \mathbb{R}^n$ est convexe si :

$$
\forall x, y \in D, \quad \forall t \in [0,1], \quad tx + (1-t)y \in D
$$

**Exemples :**

- $\{(x,y) : x+y > 0\}$ est convexe (demi-plan) 

- $\{(x,y) : x^2 + y^2 < 1\}$ est convexe (disque) 

- $\{(x,y) : xy > 1\}$ est **non** convexe 

## **Changement de variable utile**

Si $f(x,y)$ dépend de $u = x + y$ uniquement :

$$
\frac{\partial f}{\partial x} = \frac{\partial f}{\partial u} \cdot \frac{\partial u}{\partial x} = f'(u)
$$

$$
\frac{\partial f}{\partial y} = \frac{\partial f}{\partial u} \cdot \frac{\partial u}{\partial y} = f'(u)
$$

---

#  **Checklist pour les examens**

## **Pour une fonction donnée**

###  **Étape 1 : Identification**

- [ ] Quadratique ? (forme $\frac{1}{2}x^T A x + b^T x + c$)

- [ ] Domaine de définition ?

###  **Étape 2 : Propriétés**

- [ ] Calculer le gradient $\nabla f$

- [ ] Calculer la Hessienne $H_f$

- [ ] Tester la convexité (valeurs propres ou déterminant)

- [ ] Vérifier la coercivité (si demandé)

###  **Étape 3 : Optimisation**

- [ ] Résoudre $\nabla f = 0$ (points critiques)

- [ ] Classifier les points (min/max/selle via det(H))

- [ ] Calculer f au minimum

### **Étape 4 : Méthodes numériques** (si demandé)

- [ ] GPF : calculer $X^{(1)} = X^{(0)} - \alpha \nabla f(X^{(0)})$

- [ ] GPO : minimiser $\phi(\alpha)$ puis calculer $X^{(1)}$

- [ ] Comparer les valeurs f(X^{(1)})

---

# **Erreurs classiques à éviter**

## **Calcul**

- Oublier le facteur $\frac{1}{2}$ dans la forme quadratique

- Confondre $f_{xy}$ et $(f_{xy})^2$ dans le déterminant

- Ne pas vérifier que $f_{xy} = f_{yx}$ (Schwarz)

## **Raisonnement**

- Dire "H > 0 donc convexe" sans vérifier toutes les valeurs propres

- Conclure "point critique = minimum" sans tester la Hessienne

- Oublier de vérifier la coercivité avant d'affirmer l'existence d'un minimum

## **Méthodologie**

- Sauter l'étape "vérifier que c'est quadratique"

- Ne pas justifier les calculs intermédiaires

- Oublier de calculer f(x*) à la fin

---

# **Formules clés à retenir par cœur**

$$
\boxed{\nabla f = Ax + b} \quad \text{(quadratique)}
$$

$$
\boxed{D = f_{xx}f_{yy} - (f_{xy})^2} \quad \text{(déterminant Hessienne)}
$$

$$
\boxed{\text{coercive + strictement convexe} \Rightarrow \text{min unique}}
$$

$$
\boxed{\alpha^* = \frac{\|\nabla f\|^2}{\nabla f^T A \nabla f}} \quad \text{(GPO quadratique)}
$$

$$
\boxed{f\left(\sum \lambda_i x_i\right) \leq \sum \lambda_i f(x_i)} \quad \text{(Jensen convexe)}
$$
