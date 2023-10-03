# AFN
## Fonction de transition étendue
```python
def Delta(q0, w):
	P = []
	Q = [q0]
	for a in w :
		for q in Q :
			P.extend(delta(q, a))
		if not len(P):
			return []
		Q = P
		P = []
	return Q
```

# AFD
## Fonction de transition étendue
```python
def Delta(q0, w):
	q = q0
	for a in w:
		p = delta(q, a)
		if not p:
			return None
		q = p
		return q
```
## Fonction de transition
```python
def delta (q, a ): 
	if q in table : 
		if a in table [q]: 
			return table [q][a] 
	return None
```