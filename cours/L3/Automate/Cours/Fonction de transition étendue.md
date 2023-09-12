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
