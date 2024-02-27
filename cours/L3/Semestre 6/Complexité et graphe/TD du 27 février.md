# Exercice 2

## Algo 5

```
E(n) :
	x = 0
	for (i = 1, i <= n, i = i * 2)
		for (j = 1, j <= 1, j++)
			x++
```

$$log(n) * \sum^{\log(n)}_{k=1} {2k}$$
# Exercice 3

1. En une heure, nous traitons $N$ opérations un problème $\mathcal{O}(n)$, nous pouvons traiter $100x$ plus d'opération en 1 heure avec un ordinateur 100x plus puissant, pareil pour $1000000x$ 
2. .
	1. Pour $\mathcal{O}(2^n)$ :
		1. $10x$
		2. $1000x$
	2. Pour $\mathcal{O}(3^n)$ :
		1. $100^\left( \frac{1}{3} \right) \approx 4.64$
		2. $1000000^\left( \frac{1}{3} \right)=100$
	3. Pour $\mathcal{O}(5^n)$
		1. $100^\left( \frac{1}{5} \right) \approx 2.51$
		2. $1000000^\left( \frac{1}{5} \right) \approx 15.85$
3. .
	1. Pour $\mathcal{O}(n^2)$ :
		1. $10N$
		2. $1000N$
	2. Pour $\mathcal{O}(n^3)$ : 
		1. $5N$
		2. $100N$
	3. Pour $\mathcal{O}(n^5)$ :
		1. $3N$
		2. $16N$
# Exercice 4

1. ![[Exercice 5 td 27 fevrier.excalidraw]]
2. Nous rentrons le mot "abab", donc nous aurons ABAB (autant en majuscule)
3. Avec ``(a|b)*``, 
# Exercice 5

1. On peut le savoir en regardant à partir du 3ème bit de la droite et si le premier bit est à 0
2. 