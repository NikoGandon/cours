# Exercice 1

1. Les expressions qui s'évaluent à une valeur dans un environnement vide sont $x,$. Dans les autres cas on se heurterait.
2. Pour montrer que $(e,\sigma)\to v \text{ alors } v \in \mathbb{N} \cup \{ \text{true}, \text{false} \}$, 
   Hypothèse : 
   $$\sigma(x_{1}\mapsto v_{1} ~~~~~ x_{n} \mapsto v_{n})$$
   Induction sur la dérivation $(e,\sigma)\to v$
   $$\frac{e,\sigma\to v_{1} ~~~~~~ e',\sigma\to v_{2}}{(e+e',\sigma)\to v_{1}+v_{2}}$$
   $$(x,\sigma)\to v_{2} \text{ verifié}$$
   $$(x,\sigma)\to \sigma(x) \text{ vérifié}\text{ (hypothèse)}$$
3. 

# Exercice 2

Évaluons les expressions suivantes : 
1. $1+1$
   $$\frac{}{}$$
2. $\text{not}((1+1)<(1+2))$