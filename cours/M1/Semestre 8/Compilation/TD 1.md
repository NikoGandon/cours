# Exercice 1
1. `(1+(2+3))` : Le type est `int` $$\frac{\frac{}{\emptyset\Gamma1\text{ int}}\text{Int}~~ \frac{\frac{}{\emptyset\Gamma2\text{: int}}\text{Int}~~\frac{}{\emptyset\Gamma3\text{: int}}\text{Int}}{\emptyset\Gamma(2+3)\text{: int}}\text{Int}}{\emptyset\Gamma1+(2+3)\text{: int}}\text{add}$$
2. `(x+y)` : Le type est `var`  $$\frac{\frac{}{x\text{ int},y \text{ int } \Gamma x:\text{ int}}\text{var}~~\frac{}{x\text{ int},y \text{ int } \Gamma y : \text{ int}}\text{var}}{x\text{ int},y \text{ int } \Gamma(x+y):\text{ int}}\text{add}$$
3. `fun x -> (x + 1)` : Le type est `int` ? $$\frac{\frac{\frac{}{x:\text{ int } \Gamma x\text{ int}}\text{var} ~~ \frac{}{x\text{ int } \Gamma 1:\text{int}}\text{int}}{x\text{ int } \Gamma ~~ x+1:\text{ int}}\text{add}}{\Gamma \text{func } x \to (x+1):\text{int}\to \text{int}}$$
4. `fun x -> if (x < 5) then (x + 1) else (x + 2)` : Le type est `int` ? $$\frac{\frac{\frac{\frac{}{x:\text{ int } \Gamma  x : \text{ int }}\text{var}~~ \frac{}{x\text{ int } \Gamma 5 : \text{int}}\text{int}}{x:\text{ int } \Gamma x < 5:\text{ bool}}~~~~\frac{}{x\text{ int } \Gamma x+1:\text{ int}}\text{add}~~~~\frac{}{x\text{ int } \Gamma x + 2 : \text{ int}}\text{add}}{x:\text{ int } \Gamma \text{ if } (x<5) \text{ then } (x+1) \text{ else } (x+2)}}{\Gamma \text{ func } x \to (\text{if } (x<5)\text{ then }(x+1)\text{ else } (x+2)):\text{int}\to \text{int}}$$
5. Le type est `real` ? $$\frac{\frac{}{}}{}$$
6. Le type est `(fun x -> x + x) (y + 2)` ? $$\frac{\frac{\frac{\frac{}{y:\text{ int },x:\text{ int }\Gamma x+x:\text{ int }}\text{var}~~~~\frac{}{y:\text{ int },x:\text{ int }\Gamma x:\text{ int }}\text{var}}{y: \text{ int },x:\text{ int }\Gamma x + x:\text{ int }}\text{add}}{y: \text{ int }\Gamma \text{ func } x\to x+x:\text{ int }\to \text{ int }}\text{func}~~~~\frac{\frac{}{y:\text{ int } \Gamma y:\text{ int }}\text{var} ~~~~\frac{}{y:\text{ int } \Gamma 2:\text{ int }}\text{Int}}{y:\text{ int } \Gamma y+2:\text{ int}}\text{add}}{\Gamma (\text{func } x \to x+ x)(y+2):\text{ int }}\text{call}$$
7. Le type est `real` ? $$\frac{\frac{}{}}{}$$

# Exercice 2

1. `while (x < 10) do print x; x:= (x + 1)`
2. `if (x < 5) then print x else print (x + 1)`