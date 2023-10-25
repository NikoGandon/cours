# Exercice 1
1) 

|     | Effectif | Cumul |
| --- | -------- | ----- |
| $[38;29[$   | 3        | 3            |
| $[39,39.5[$ | 5        | 8            |
| $[39.5,40[$ | 10       | 18           |
| $[40,40.5[$ | 13       | 31           |
| $[40.5,41[$ | 20       | 51           |
| $[41,41.5[$ | 18       | 69           |
| $[41.5,42[$ | 15       | 84           |
| $[42,42.5[$ | 11       | 95           |
| $[42.5,43[$ | 4        | 99           |
| $[43,44[$   | 1        | 100          |

2) La variable étudié est une variable continue
3) .
4) .
5) $\overline{X}=\frac{1}{100}\times(3\times38.5+5\times39.25+\dots+1\times43.5)$
   La médiane est 41 ?
   $Q_{1}=31$
   $Q_{2}=84$
6) .

```mermaid

```

# Exercice 2
1) 
   
   
```dataviewjs
const labels = ['0-10', '10-20', '20-30', '30-50', '50-100'];
const data = [30,60,150,50,10];

const chartData = {  
    type: 'bar',

    data: {
        labels: labels,
        datasets: [{
            label: 'Numbers',
            data: data,
            backgroundColor: '#FFB1C1',
        }]
    }
}

window.renderChart(chartData, this.container);
```

2) La classe modale est la classe $]20;30]$
3) 
      
| Montant           | $]0;10]$ | $]10;20]$ | $]20;30]$ | $]30;50]$ | $]50;100]$ |
| ----------------- | -------- | --------- | --------- | --------- | ---------- |
| Nb de client      | 30       | 60        | 150       | 50        | 10         |
| Cumul croissant   | 30       | 90        | 240       | 290       | 300        |
| Cumul decroissant | 300      | 270       | 210       | 60        | 10         |

```desmos-graph
left=0;right=110;
bottom = 0;top = 320;
---
(10,30)
(20,90)
(30,240)
(50,290)
(100,300)

(10,300)
(20,270)
(30,210)
(50,60)
(100,10)
```

Médiane : $M \binom{x}{y}$, $A \binom{26}{90}$, $B \binom{30}{240}$
$\Leftrightarrow 60\times 10 = 150(x_{m}-20)$
$\Leftrightarrow \frac{600}{150}=x_{m}-20$
$\Leftrightarrow x_{m}=24$
$Q_{1}=$
$Q_{3}=$
4) 


# Exercice 3
```desmos-graph

left = 58;right = 74;
bottom = 65;top = 105;
---
(60,70)
(62,75)
(62,70)
(64,75)
(64,80)
(66,80)
(68,80)
(70,85)
(72,90)
(74,100)

```

$\overline{X} = 66,2$
$\overline{Y} = 80,5$

$Var(X)={ \frac{(\sum^n_{i=1}| X_{i}-\overline{X} |^2 )}{n} }\approx 19.18$
$Var(Y)={ \frac{(\sum^n_{i=1}| Y_{i}-\overline{Y} |^2 )}{n} }\approx \dots$

$\sigma_{X}=\sqrt{ \frac{(\sum^n_{i=1}| X_{i}-µ |^2 )}{n} }$
$\sigma_{Y}=\sqrt{ \frac{(\sum^n_{i=1}| Y_{i}-µ |^2 )}{n} }$


# Exercice 6

```desmos-graph
left = -100;right = 1100;
bottom = 0;top = 10;
---
(94,1)
(221,2)
(446,3)
(1050,4)
```
2) 
   
| $x_i$   | 1     | 2      | 3      | 4   |
| ------- | ----- | ------ | ------ | --- |
| $z_{i}$ | $9.7$ | $14.9$ | $21.1$ | $32.4$ |

4) 
   $\overline{X}=\frac{(94\times 1)+(221\times 2) + (446 \times 3) + (1050 \times 4)}{4}=\frac{3037}{2}\approx 1518.5$
   