# Exercice 1

On a un type ``Bool`` ainsi que des opérateurs ``si-alors-sinon``, soit l'opérateur $eg : Ens \times Elt \to Bool$ où $Ens$ est l'ensemble et $Elt$ les éléments de l'ensemble
On écrira les axiomes pour définir les symboles suivants :
*Constructeur* :
	$vide :\to Ens$
	$ajout :\to Ens \times Elt \to Ens$
*Opération* :
	$app :\to Elt \times Ens \to Bool$
	$supp :\to Elt \times Ens \to Ens$
	$inter :\to Ens \times Ens \to Ens$
	$diff :\to Ens \times Ens \to Ens$
Où app signifie appartient, supp signifie supprime, inter est l’intersection et diff la différence. La suppression d’un élément inexistant laisse l’ensemble inchangé.

__Ensemble vide__ : $\text{vide}:\to \text{Ens}$
__Ajout d'un élément dans un ensemble__ : 
	$\text{ajout}:\to \text{Ens} \times \text{Elt} \to \text{Ens}$
	$\text{ajout}(\text{ajout}(m,e),e) = \text{ajout}(m,e)$
	$\text{ajout}(\text{ajout}(m,e_{1}),e_{2})=\text{ajout}(\text{ajout}(m,e_{2}),e_{1})$

__Appartient__ : implicite dans les axiomes de constructeurs
__Supprime__ :
	$\text{supp}(e, \text{vide}) = \text{vide}$
	$\text{supp}(e, \text{ajout}(m, e')) = \text{si } eg(e,e') \text{ alors } m \text{ sinon } \text{ajout}(\text{supp}(e,m),e')$
__Intersection__ :
	$\text{inter}(\text{vide}, m) = \text{vide}$
	$\text{inter}(\text{ajout}(m, e), m') = \text{si } \text{app}(e,m') \text{ alors } \text{ajout}(\text{inter}(m,m'),e) \text{ sinon } \text{inter}(m,m')$
__Différence__ : 
	$\text{diff}(\text{vide}, m) = \text{vide}$
	$\text{diff}(m,\text{vide}) = m$
	$\text{diff}(\text{ajout}(m,e),m') = \text{si } \text{app}(e,m') \text{ alors } \text{diff}(m,m') \text{ sinon } \text{ajout}(\text{diff}(m,m'))$


# Exercice 2

Soit $E$ la théorie équationnelle suivante :
(1) $a*b=b$
(2) $(x*y)*z=x*(y*z)$
(3) $a*(x*b)=x*b$

On doit montrer que $a*(b*(c*b))=\ _{E} b*(c*b)$ :
$x,y,z$ : variables
$a,b,c \in \mathcal{F}$
$\forall x, (x) =x$
$\forall c \in \mathcal{F} \text{ d'arrité } 0, (c)=c$

$\ ^{(1)}=_{E}b*(c*b)$, $G \in \text{Id}$
$a*(b*(c*b))\ ^{(2)}=_{E}(a*b)*(c*b)$ avec $\sigma=[x \mapsto a, y \mapsto b, z \mapsto c * b]$
$a*(b*(c*b)) \ ^{(2)}=_{E}(a*b)*(c*b)$
$a*(b*(c*b)) ^{(2)}=_{E}a*((b*c)*b)$, $\sigma=[x \mapsto b, y \mapsto c, z \mapsto b]$
$a*((b*c)*b) \ ^{(3)}=_{E}(b*c)*b$, $\sigma=[x \mapsto b*c]$
$\ ^{(2)}=_{E}b*(c*b)$, $\sigma=[x \mapsto b, y \mapsto c, z \mapsto b]$

# Exercice 3

Soit l'axiomatisation d'un groupe abélien suivant :
$$E = \begin{cases}
 x*e=x ~~~~~~~~~~~~~~~~~~~~~~~~~(1)\\
x*i(x)=e ~~~~~~~~~~~~~~~~~~~~~(2)\\
(x*y)*z=x*(y*z)~~(3)
\end{cases}$$
Pour prouver l'égalité $e*x=_{E}x$
$e*x\ ^{1}=_{E}e*(x*e)\ ^{(2)}=_{E}(x*(i(x)*(i(x)))) \ ^{(3)}=_{E}e*((x*i(x))*i(i(x))))$
$\ ^{(2)}=_{E} e*(e*i(i(x))) \ ^{(3)}=_{E} (e*e)*i(i(x))\ ^{(1)}=_{E}e*i(i(x)) \ ^{(3)}=_{E}(x*i(x))*i(i(x))$
$\ ^{(2)}=_{E}x*(i(x)*i(i(x))) \ ^{(2)}=_{E}x*e \ ^{(1)}=_{E}x$

# Exercice 4

Soit le système de réécriture suivant :
$$R=\{0+x \to x, f(x+y)\to f(y)$$
1. $R$ est terminant par l'ordre $>_{\text{lpo}}$

2. $R$ est confluant
