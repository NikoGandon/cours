# Formulaire de Révision : Optimisation

## 1. Optimisation sans contraintes

Soit $f: \mathbb{R}^n \rightarrow \mathbb{R}$ une fonction à optimiser.

### Dérivées et Matrices
* **Gradient ($\nabla f$)** : Le vecteur des dérivées partielles premières.
    $$\nabla f(x) = \begin{pmatrix} \frac{\partial f}{\partial x_1} \\ \vdots \\ \frac{\partial f}{\partial x_n} \end{pmatrix}$$

 **Matrice Hessienne ($H_f$)** : La matrice des dérivées partielles secondes.
    $$H_f(x) = \begin{pmatrix} \frac{\partial^2 f}{\partial x_1^2} & \cdots & \frac{\partial^2 f}{\partial x_1 \partial x_n} \\ \vdots & \ddots & \vdots \\ \frac{\partial^2 f}{\partial x_n \partial x_1} & \cdots & \frac{\partial^2 f}{\partial x_n^2} \end{pmatrix}$$

### Conditions d'optimalité
* **Condition nécessaire (Point critique)** :
    $$\nabla f(x^*) = 0$$
    Un point critique est un candidat pour être un extremum (minimum, maximum ou point selle).

 **Convexité (Condition suffisante)**:
    * $f$ est **convexe** si $H_f(x)$ est positive (toutes valeurs propres $\geq 0$).
    * $f$ est **strictement convexe** si $H_f(x)$ est définie positive (toutes valeurs propres $> 0$).
     Si $f$ est convexe, tout minimum local est global.

### Algorithmes de descente
 **Algorithme du gradient à pas fixe ($\alpha$)**:
    $$x^{(k+1)} = x^{(k)} - \alpha \nabla f(x^{(k)})$$

---

## 2. Optimisation sous contraintes (Égalités)

On cherche à minimiser $f(x,y)$ sous la contrainte $g(x,y) = 0$.

### Méthode de Lagrange
 **Fonction Lagrangienne ($\mathcal{L}$)**:
    $$\mathcal{L}(x,y,\lambda) = f(x,y) + \lambda g(x,y)$$

 **Système à résoudre (Point critique)**:
    $$\begin{cases} \frac{\partial \mathcal{L}}{\partial x} = 0 \\ \frac{\partial \mathcal{L}}{\partial y} = 0 \\ \frac{\partial \mathcal{L}}{\partial \lambda} = 0 \quad (\text{équivaut à } g(x,y)=0) \end{cases}$$

### Conditions suffisantes (Nature des points)
 **Matrice Hessienne Bordée ($HB_{\mathcal{L}}$)**:
    $$HB_{\mathcal{L}}(x,y,\lambda) = \begin{pmatrix} \frac{\partial^2 \mathcal{L}}{\partial x^2} & \frac{\partial^2 \mathcal{L}}{\partial x \partial y} & \frac{\partial g}{\partial x} \\ \frac{\partial^2 \mathcal{L}}{\partial y \partial x} & \frac{\partial^2 \mathcal{L}}{\partial y^2} & \frac{\partial g}{\partial y} \\ \frac{\partial g}{\partial x} & \frac{\partial g}{\partial y} & 0 \end{pmatrix}$$

 **Test du déterminant ($\Delta$)**:
    Soit $\Delta = \det(HB_{\mathcal{L}}(x^*, y^*, \lambda^*))$.
    * Si $\Delta > 0 \Rightarrow$ **Maximum** local lié.
    * Si $\Delta < 0 \Rightarrow$ **Minimum** local lié.

---

## 3. Applications : Régression Linéaire

### Régression Linéaire Simple
Modèle : $y_i = \beta_1 x_i + \beta_0 + \epsilon_i$.

 **Pente ($\hat{\beta}_1$)** (MCO):
    $$\hat{\beta}_1 = \frac{\sum_{i=1}^{n}(x_i - \bar{x})(y_i - \bar{y})}{\sum_{i=1}^{n}(x_i - \bar{x})^2} = \frac{S_{xy}}{S_{xx}}$$

**Ordonnée à l'origine ($\hat{\beta}_0$)**:
    $$\hat{\beta}_0 = \bar{y} - \hat{\beta}_1 \bar{x}$$

**Coefficient de détermination ($R^2$)**:
    $$R^2 = \frac{SCE}{SCT} = 1 - \frac{SCR}{SCT}$$
    *Dans le cas simple, c'est le carré du coefficient de corrélation : $R^2 = r^2$.*

### Régression Linéaire Multiple (Matricielle)
Modèle : $Y = X\beta + \epsilon$.

**Estimateur des MCO ($\hat{\beta}$)**:
    $$\hat{\beta} = (tX X)^{-1} tX Y$$

---

## 4. Outils Algèbre Linéaire (Matrices)

### Déterminant 2x2
$$\det \begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc$$

### Déterminant 3x3
Soit $A = \begin{pmatrix} a & b & c \\ d & e & f \\ g & h & i \end{pmatrix}$.

$$\det(A) = a(ei - fh) - b(di - fg) + c(dh - eg)$$
