

##  20 Nuovi Esercizi sul Valore Assoluto

### A. Disequazioni con Prodotto/Fattorizzazione (Simili a $|x^2-25|(x^2-1)<0$)

1. $|x^2-4|(x^2-9) \geq 0$
    
2. $(x^2-16) |2x+1| < 0$
    
3. $|3x-5|(x^2+x-2) \leq 0$
    
4. $(x-2)|x^2-4x+3| > 0$
    
5. $|x^3-x| (x^2+4) < 0$
    

---

### B. Disequazioni con Frazioni (Simili a $\frac{-x^2+6x-5}{1+|3x-4|}$)

6. $\frac{x^2-4x+3}{|x-2|} \geq 0$
    
7. $\frac{x^2+x-6}{1+|x^2-1|} < 0$
    
8. $\frac{|2x+3|-1}{x^2+5x+6} > 0$
    
9. $\frac{|x-1|}{x^2-7x+10} \leq 0$
    
10. $\frac{x^2}{|x^2-3x+2|+1} < 0$
    

---

### C. Disequazioni Miste con Valore Assoluto (Simili a $1-x|1-x|>0$)

11. $x^2 + 2x - |x+1| > 0$
    
12. $|2x-1| - x^2 + 1 \leq 0$
    
13. $3x + |x^2-2x| < 0$
    
14. $x|x| + 3x - 4 \geq 0$
    
15. $x|x+2| < 8$
    

---

### D. Dominio di Radici con Valore Assoluto (Simili a $\sqrt{|\log x| - 1}$ e $\sqrt{2+x+x|x|}$)

Determinare il **Dominio** delle seguenti funzioni (cioè, quando il radicando è $\geq 0$):

16. $\sqrt{1 - |\log_2 x|}$
    
17. $\sqrt{|\ln(x-1)| - 2}$
    
18. $\sqrt{x^2 - |5x+6|}$
    
19. $\sqrt{|x^2-4| - 3x}$
    
20. $\sqrt{x^3 + x^2|x| - 2}$
    

---

## 💡 Consiglio per la Risoluzione

Per risolvere la maggior parte di questi esercizi, il metodo fondamentale è **studiare il segno degli argomenti del valore assoluto** e risolvere la disequazione risultante nei diversi intervalli. Ad esempio, per risolvere un'espressione che contiene $|f(x)|$, dovrai dividere lo studio in due casi:

1. **Caso 1:** $f(x) \geq 0 \quad \rightarrow \quad |f(x)| = f(x)$
    
2. **Caso 2:** $f(x) < 0 \quad \rightarrow \quad |f(x)| = -f(x)$
    
# Risoluzione 

##  Soluzioni degli Esercizi Assegnati

### 1. Disequazione Prodotto: $|x^2-25|(x^2-1)<0$

Questa è una disequazione prodotto. Affinché il prodotto di due fattori sia **negativo** ($<0$), i due fattori devono avere segni opposti.

- Il primo fattore, $|x^2-25|$, è un **valore assoluto**, quindi è sempre $\geq 0$.
    
- L'unico modo in cui il prodotto possa essere negativo è se:
    
    1. $|x^2-25| > 0$
        
    2. $x^2-1 < 0$
        

A) Analizziamo il secondo fattore:

$$x^2-1 < 0 \Rightarrow (x-1)(x+1) < 0$$

Questa disequazione è soddisfatta per valori interni alle radici:

$$-1 < x < 1$$

B) Analizziamo il primo fattore:

$$|x^2-25| > 0$$

Un valore assoluto è maggiore di zero quando il suo argomento non è zero:

$$x^2-25 \neq 0 \Rightarrow x \neq 5 \text{ e } x \neq -5$$

C) Conclusione:

La soluzione finale è l'intersezione tra le due condizioni. Poiché l'intervallo $(-1, 1)$ non include i valori $x=5$ o $x=-5$, la soluzione è semplicemente la condizione A.

$$\mathbf{S: -1 < x < 1}$$

---

### 2. Disequazione Fratta: $\frac{-x^2+6x-5}{1+|3x-4|} > 0$

**Nota:** Ho assunto che l'esercizio fosse una disequazione che richiede di essere posta maggiore di $0$ (o minore di $0$) per essere risolta, come tipico in un elenco di esercizi. Ho scelto **$> 0$**.

A) Studio del Denominatore:

Il denominatore è $1+|3x-4|$.

- Il valore assoluto $|3x-4|$ è sempre $\geq 0$.
    
- Quindi, $1+|3x-4|$ è sempre $\geq 1$.
    
    Il denominatore è sempre positivo per ogni $x \in \mathbb{R}$.
    

B) Studio del Numeratore:

Affinché la frazione sia positiva, anche il numeratore deve essere positivo:

$$-x^2+6x-5 > 0$$

Moltiplico per $-1$ e inverto il segno della disequazione:

$$x^2-6x+5 < 0$$

Calcolo le radici dell'equazione $x^2-6x+5=0$ usando $x = \frac{6 \pm \sqrt{36-20}}{2} = \frac{6 \pm 4}{2}$.

Le radici sono $x_1=1$ e $x_2=5$.

Poiché la parabola volge verso l'alto e vogliamo i valori $<0$, prendiamo i valori interni alle radici.

$$1 < x < 5$$

C) Conclusione:

Poiché il denominatore è sempre positivo, la soluzione della frazione dipende solo dal numeratore.

$$\mathbf{S: 1 < x < 5}$$

---

### 3. Disequazione Mista: $1-x|1-x|>0$

Riscriviamo come: $x|1-x| < 1$.

Dobbiamo studiare il segno dell'argomento del valore assoluto, cioè $1-x$.

Caso 1: $1-x \geq 0 \Rightarrow x \leq 1$

In questo intervallo, $|1-x| = 1-x$.

La disequazione diventa:

$$x(1-x) < 1$$

$$x - x^2 < 1$$

$$-x^2 + x - 1 < 0$$

$$x^2 - x + 1 > 0$$

Studiamo il discriminante $\Delta = b^2 - 4ac = (-1)^2 - 4(1)(1) = 1 - 4 = -3$.

Poiché $\Delta < 0$ e il coefficiente di $x^2$ è positivo ($1 > 0$), la parabola $y=x^2-x+1$ è sempre sopra l'asse $x$. Quindi, $x^2-x+1 > 0$ è sempre vera per ogni $x \in \mathbb{R}$.

Intersezione con la condizione del Caso 1 ($x \leq 1$):

$$\mathbf{S_1: x \leq 1}$$

Caso 2: $1-x < 0 \Rightarrow x > 1$

In questo intervallo, $|1-x| = -(1-x) = x-1$.

La disequazione diventa:

$$x(x-1) < 1$$

$$x^2 - x < 1$$

$$x^2 - x - 1 < 0$$

Calcolo le radici dell'equazione $x^2 - x - 1 = 0$:

$$x = \frac{1 \pm \sqrt{1 - 4(1)(-1)}}{2} = \frac{1 \pm \sqrt{5}}{2}$$

Le radici sono $x_3 = \frac{1 - \sqrt{5}}{2}$ e $x_4 = \frac{1 + \sqrt{5}}{2}$.

Vogliamo i valori interni:

$$\frac{1 - \sqrt{5}}{2} < x < \frac{1 + \sqrt{5}}{2}$$

Intersezione con la condizione del Caso 2 ($x > 1$).

Si noti che $\frac{1 - \sqrt{5}}{2} \approx -0.618$ e $\frac{1 + \sqrt{5}}{2} \approx 1.618$.

Intersecando l'intervallo $(-0.618, 1.618)$ con $x > 1$:

$$\mathbf{S_2: 1 < x < \frac{1 + \sqrt{5}}{2}}$$

C) Soluzione Finale:

La soluzione è l'unione di $S_1$ e $S_2$:

$$S = S_1 \cup S_2 = \left(x \leq 1\right) \cup \left(1 < x < \frac{1 + \sqrt{5}}{2}\right)$$

$$\mathbf{S: x < \frac{1 + \sqrt{5}}{2}}$$

---

### 4. Dominio di Funzione Radice: $\sqrt{|\log x| - 1}$

Il campo di esistenza (dominio) di una radice quadrata richiede che il radicando sia maggiore o uguale a zero:

$$|\log x| - 1 \geq 0$$

Inoltre, l'argomento del logaritmo deve essere positivo: $\mathbf{x > 0}$ (Condizione di Esistenza).

A) Disequazione con Valore Assoluto:

$$|\log x| \geq 1$$

Questa si sdoppia in due disequazioni:

1. $\log x \geq 1$
    
2. $\log x \leq -1$
    

**B) Risoluzione (assumendo $\log x = \log_{10} x$):**

1. $\log_{10} x \geq 1 \Rightarrow x \geq 10^1 \Rightarrow \mathbf{x \geq 10}$
    
2. $\log_{10} x \leq -1 \Rightarrow x \leq 10^{-1} \Rightarrow \mathbf{x \leq \frac{1}{10}}$
    

C) Conclusione:

Dobbiamo intersecare le soluzioni trovate con la condizione di esistenza $x > 0$.

- $x \geq 10$ è accettabile.
    
- $x \leq \frac{1}{10}$ intersecato con $x > 0$ diventa $0 < x \leq \frac{1}{10}$.
    

$$\mathbf{S: 0 < x \leq \frac{1}{10} \text{ o } x \geq 10}$$

---

### 5. Dominio di Funzione Radice: $\sqrt{2+x+x|x|}$

Dobbiamo imporre che il radicando sia maggiore o uguale a zero:

$$2+x+x|x| \geq 0$$

Dobbiamo studiare il segno dell'argomento del valore assoluto, cioè $x$.

Caso 1: $x \geq 0$

In questo intervallo, $|x| = x$.

La disequazione diventa:

$$2+x+x(x) \geq 0$$

$$x^2 + x + 2 \geq 0$$

Studiamo il discriminante $\Delta = 1^2 - 4(1)(2) = 1 - 8 = -7$.

Poiché $\Delta < 0$ e il coefficiente di $x^2$ è positivo ($1 > 0$), la disequazione è sempre vera per ogni $x \in \mathbb{R}$.

Intersezione con la condizione del Caso 1 ($x \geq 0$):

$$\mathbf{S_1: x \geq 0}$$

Caso 2: $x < 0$

In questo intervallo, $|x| = -x$.

La disequazione diventa:

$$2+x+x(-x) \geq 0$$

$$-x^2 + x + 2 \geq 0$$

Moltiplico per $-1$ e inverto il segno della disequazione:

$$x^2 - x - 2 \leq 0$$

Calcolo le radici di $x^2-x-2=0$: $(x-2)(x+1)=0$.

Le radici sono $x_1=-1$ e $x_2=2$.

Vogliamo i valori interni:

$$-1 \leq x \leq 2$$

Intersezione con la condizione del Caso 2 ($x < 0$):

$$\mathbf{S_2: -1 \leq x < 0}$$

C) Soluzione Finale:

La soluzione è l'unione di $S_1$ e $S_2$:

$$S = S_1 \cup S_2 = \left(-1 \leq x < 0\right) \cup \left(x \geq 0\right)$$

L'unione copre tutti i valori reali da $-1$ in poi.

$$\mathbf{S: x \geq -1}$$