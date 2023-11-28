---
~
---
# Exercice 1
1. Vrai
2. Faux
3. ?
4. ?
5. Faux
(Voir page 75)

# Exercice 2
(à partir de la page 80)
1. Expression régulière pour $R_{i:j}^{(0)}$
$$R_{i:j}^{(0)}$$
$$= R_{1:1}=\epsilon+1$$   
2. Expression régulière pour $R_{i:j}^{(1)}$
3. Expression régulière pour $R_{i:j}^{(2)}$
4. Expression régulière du langage de cet automate par construire $R_{1:3}^{(3)}$ 
5. Expression régulière du langage de cet automate par éliminer $q_{2}$

# Exercice 3
On convertit cet automate

|       | 0   | 1   |
| ----- | --- | --- |
| ->\*p | s   | p   |
| q     | p   | s   |
| r     | r   | q   |
| s     | q   | r   |

Par cette expression régulière :

```mermaid
flowchart LR
	p -- 0 --> s
	p -- 1 --> p
	s -- 0 --> q
	s -- 1 --> r
	q -- 0 --> p
	q -- 1 --> s
	r -- 0 --> r
	r -- 1 -->q
```

Sa forme REGEX est : 
# Exercice 4
On convertit ces expressions régulières en AFD :
1. 01*
```mermaid
flowchart LR
	s1
	s2
	s3
	s1 -- 0 --> s2
	s2 -- 1 --> s3
	s3 -- 0,1 --> s3
```   
   
2. (0+1)01
```mermaid
flowchart LR
	s1
	s2
	s3
	s4
	s5
	s1 -- 0 --> s3
	s2 -- 1 --> s3
	s3 -- 0 --> s4
	s4 -- 1 --> s5
```

3. 00(0+1)
```mermaid
flowchart LR
	s1
	s2
	s3
	s5
	s1 -- 0 --> s2
	s2 -- 0 --> s3
	s3 -- 0 --> s5
	s3 -- 1 --> s5
```

# Exercice 5

# Exercice 6
