# Exercice 1

$2* z^5 - 2 * z$ en abstrait est $\forall ~~ \mathbb{N}$ divisible par $5$ :
$\bar{z} \in [0,4]$
$z$ est divisible par $5$ si et seulement si $\bar{z} = 0$ 


| $\bar{-}$ | $\bar{0}$ | $\bar{1}$ | $\bar{2}$ | $\bar{3}$ | $\bar{4}$ |
| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| $\bar{0}$ | $\bar{0}$ | $\bar{1}$ | $\bar{2}$ | $\bar{3}$ | $\bar{4}$ |
| $\bar{1}$ | $\bar{1}$ | $\bar{0}$ | $\bar{1}$ | $\bar{2}$ | $\bar{3}$ |
| $\bar{2}$ | $\bar{2}$ | $\bar{1}$ | $\bar{0}$ | $\bar{1}$ | $\bar{2}$ |
| $\bar{3}$ | $\bar{3}$ | $\bar{2}$ | $\bar{1}$ | $\bar{0}$ | $\bar{1}$ |
| $\bar{4}$ | $\bar{4}$ | $\bar{3}$ | $\bar{2}$ | $\bar{1}$ | $\bar{0}$ |

| $\bar{*}$ | $\bar{0}$ | $\bar{1}$ | $\bar{2}$ | $\bar{3}$ | $\bar{4}$ |
| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| $\bar{0}$ | $\bar{0}$ | $\bar{0}$ | $\bar{0}$ | $\bar{0}$ | $\bar{0}$ |
| $\bar{1}$ | $\bar{0}$ | $\bar{1}$ | $\bar{2}$ | $\bar{3}$ | $\bar{4}$ |
| $\bar{2}$ | $\bar{0}$ | $\bar{2}$ | $\bar{4}$ | $\bar{2}$ | $\bar{0}$ |
| $\bar{3}$ | $\bar{0}$ | $\bar{3}$ | $\bar{1}$ | $\bar{4}$ | $\bar{2}$ |
| $\bar{4}$ | $\bar{0}$ | $\bar{4}$ | $\bar{3}$ | $\bar{2}$ | $\bar{1}$ |

$e=2 \times z \times z \times z \times z \times z - 2 \times z$


Pour $\bar{z}=\bar{0}$; $e=\bar{0} \bar{-}\bar{0}= \bar{0}$
Pour $\bar{z}=\bar{1}$; $e=\bar{2} \times \bar{1} \bar{-} \bar{2} \times \bar{1} = \bar{2} \bar{-} \bar{2}= \bar{0}$
Pour $\bar{z}=\bar{2}$; $e=\bar{2} \times \bar{2} \bar{-} \bar{2} \times \bar{2} = \bar{4} \bar{-} \bar{4}= \bar{0}$ 
Pour $\bar{z}=\bar{3}$; $e=\bar{2} \times \bar{3} \bar{-} \bar{2} \times \bar{3} = \bar{1} \bar{-} \bar{1}= \bar{0}$
Pour $\bar{z}=\bar{4}$; $e=\bar{2} \times \bar{4} \bar{-} \bar{2} \times \bar{4} = \bar{3} \bar{-} \bar{3}= \bar{0}$ 

# Exercice 2

1. Soit l'expression $x-y$ dans l'environnement $\sigma_1 = [x \mapsto 42, y \mapsto 0]$ 
   $\mathcal{A}=[\![x-y]\!]\sigma = \mathcal{A}[\![x]\!]\sigma-\mathcal{A}[\![y]\!]\sigma = \sigma(x) - \sigma(y)=42-0$
   
2. Soit l'expression $x+y$ dans l'environnement $\sigma_2 = [x \mapsto 42, y \mapsto 0]$  
   $\mathcal{A}=[\![x+y]\!]\sigma = \mathcal{A}[\![x]\!]\sigma-\mathcal{A}[\![y]\!]\sigma = \sigma(x) - \sigma(y)=42+0$
   
3. Soit l'expression $x-y$ dans l'environnement $\sigma_3 = [x \mapsto 42, y \mapsto 42]$  
   $\mathcal{A}=[\![x-y]\!]\sigma = \mathcal{A}[\![x]\!]\sigma-\mathcal{A}[\![y]\!]\sigma = \sigma(x) - \sigma(y)=42-42=0$

# Exercice 3

1. Soit l'expression $1<n$ dans l'environnement $\sigma_1 = [n \mapsto 3, m \mapsto 1]$ 
   
2. Soit l'expression $1<n$ dans l'environnement $\sigma_2 = [n \mapsto 2, m \mapsto 3]$ 
   
3. Soit l'expression $1<n$ dans l'environnement $\sigma_3 = [n \mapsto 1, m \mapsto 6]$

# Exercice 4

1. Soit le programme ``x := x - y; y := x + y; x := y - x`` et l'état $\sigma=[x \mapsto 42, y \mapsto 0]$
   $<x=x-y; y:=x+y;x:=y-x, \sigma>~ \to ~<y:=x+y;x:=y-x, \sigma_{1}>$ avec $$\begin{rcases}\sigma_1 = [x \mapsto \mathcal{A}[\![x-y]\!]\sigma, ?] \\ \mathcal{A}[\![x-y]\!]\sigma=42\end{rcases} \implies \sigma_{1}=[x \mapsto 42; y \mapsto 0]$$
$\text{assign} \to <x:=y-x, \sigma_{2}>$
$\sigma_{2}=\sigma_{1}[y \mapsto \mathcal{A}[\![x+y]\!], \sigma_{1}]=[y \mapsto 42; x \mapsto 42]$
$\text{assign} \to$
$<\epsilon, \sigma_{3}>$ avec $\sigma_3???????$

2. Soit le programme ``m := 1; while 1 < n do m := m ∗ n; n := n − 1; end;`` et l'état $\sigma=[n \mapsto 3]$
   $<m=1; \text{ while } 1 < n \text{ do } m = m \times n; n=n-1; \text{ end}, \sigma> ~ \to ~~~~~~\text{     (assign)}$
   $<\text{while } 1 < n \text{ do } m = m \times n; n = n - 1; \text{end}, \sigma_{1} > \to ~~~~ \text{(while)}\sigma_{1}=[n \mapsto 3, m \mapsto 1]$
   $\sigma_{1}=\sigma[m \mapsto \mathcal{A}[\![1]\!]\sigma]=\sigma[m \mapsto 1]$
