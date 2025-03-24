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
   $$\frac{\frac{}{1,\emptyset\to 1} ~~~~~~~~\frac{}{1,\emptyset\to 1}}{1+1,\emptyset \to 2}$$
2. $\text{not}((1+1)<(1+2))$
   $$\frac{\frac{\frac{1,\emptyset\to 1 ~~~~~~ 1,\emptyset \to 1}{1+1, \emptyset\to 2}~~~~~~\frac{1,\emptyset\to 1 ~~~~~~2,\emptyset\to 2}{1+2,\emptyset\to 3}}{(1+1)<(1+2), \emptyset \to \text{true}}}{\text{not}((1+1)<(1+2)), \emptyset\to \text{false}}$$

# Exercice 3

1. `x=1;y=2; if(x<y) then skip else skip`
   
   $$\frac{\frac{\frac{}{1,\emptyset\to 1}}{x=1,\emptyset\to(\text{skip}, x \to 1)}~~~~\frac{\frac{\frac{}{(2,x\to 2)}}{y=2,x=1,x\to1\to\text{skip},(x \to 1, y \to 2)}~~~~~~~~~~\frac{\frac{\frac{}{x,\{ x \mapsto 1, y \mapsto 2 \})\to\text{true}}~~~~~~\frac{}{(y,\{ x \mapsto 1, y \mapsto 2 \})\to 2}}{(x<y, \{ x \mapsto 1, y \mapsto 2 \})\to\text{true}}}{\text{(if (x<y) then skip else skip, }\{ x\to 1, y \to 2 \})\to(\text{skip}, \{ x\to1, y \to 2 \})}}{(y=2,~~~~,x \to 1)\to (\text{skip}, \{ x \mapsto 1, y \mapsto 2 \})}}{(x=1,y=2~~~~~~~~\text{if (x<y) then skip else skip)}, \emptyset)\to(\text{skip}, \{ x \mapsto 1, y \mapsto 2 \})}$$
2. `arg=5;x=1;whie(arg>0) do {x=x*arg;arg=arg-1}`
   