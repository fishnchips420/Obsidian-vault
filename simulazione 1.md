## Domanda 2 , equazioni esponenziali 
![[Domanda 2.png]]Certamente, cominciamo dalla domanda 2. È un'ottima domanda per ripassare i fondamenti delle funzioni esponenziali.

L'argomento qui è il **grafico della funzione esponenziale** $y = a^x$.

L'aspetto più importante di questi grafici dipende interamente dal valore della **base $a$**. La regola fondamentale da ricordare è due:

1. **Caso 1: $a > 1$ (Crescita Esponenziale)**
    
    - La funzione è **sempre crescente**.
        
    - Più la base $a$ è grande, più la funzione cresce "velocemente" (cioè il grafico è più ripido per $x > 0$).
        
    - Nel tuo grafico, $f_3$, $f_4$ e $f_5$ sono tutti esempi di crescita esponenziale.
        
    - Poiché $f_5$ è la più ripida, seguita da $f_4$ e poi da $f_3$, possiamo dire che le loro basi sono in quest'ordine: $1 < \text{base}(f_3) < \text{base}(f_4) < \text{base}(f_5)$.
        
2. **Caso 2: $0 < a < 1$ (Decadimento Esponenziale)**
    
    - La funzione è **sempre decrescente**.
        
    - Più la base $a$ è piccola (cioè più si avvicina a 0), più la funzione decresce "velocemente" (il grafico è più ripido).
        
    - Nel tuo grafico, $f_1$ e $f_2$ sono esempi di decadimento esponenziale.
        
    - Poiché $f_1$ è più ripida di $f_2$, significa che la sua base è _più piccola_ di quella di $f_2$. Possiamo dire: $0 < \text{base}(f_1) < \text{base}(f_2) < 1$.
        

Tutti questi grafici (se non traslati) hanno una caratteristica in comune: passano tutti per il punto **$(0, 1)$**, perché qualsiasi numero (diverso da zero) elevato alla potenza di 0 fa 1.

---

### Analisi dell'Esercizio (Domanda 2)

Ora applichiamo queste regole al tuo esercizio.

1. **La funzione da trovare:** $y = (\frac{1}{3})^x$.
    
2. **Analisi della base:** La base è $a = \frac{1}{3}$.
    
3. **Identificazione del caso:** Poiché $0 < \frac{1}{3} < 1$, siamo nel **Caso 2: Decadimento Esponenziale**.
    
4. **Conclusione preliminare:** Il grafico che cerchiamo _deve_ essere uno di quelli decrescenti, quindi **o $f_1$ o $f_2$**.
    

Questo significa che l'opzione $f_4$ (che vedo selezionata nello screenshot) non è corretta. $f_4$ è una funzione _crescente_, quindi la sua base deve essere $a > 1$ (ad esempio $y = 3^x$ o $y = 4^x$).

#### Come distinguere $f_1$ e $f_2$?

Dobbiamo capire quale delle due è $y = (\frac{1}{3})^x$. Possiamo usare un punto specifico del grafico.

- Guarda le linee tratteggiate: indicano dei punti precisi. Sembra che la curva $f_3$ passi per il punto **$(1, 2)$** e la curva $f_2$ passi per il punto **$(-1, 2)$**.
    
- Verifichiamo questa ipotesi:
    
    - **Per $f_2$**: Se $y = a_2^x$ passa per $(-1, 2)$, allora $2 = a_2^{-1}$.
        
    - $a_2^{-1}$ significa $\frac{1}{a_2}$.
        
    - Quindi $2 = \frac{1}{a_2}$, che risolto dà $a_2 = \frac{1}{2}$.
        
    - Questo ha senso: $f_2$ è decrescente e la sua base $a_2 = \frac{1}{2}$ è compresa tra 0 e 1. Quindi, **$f_2$ è il grafico di $y = (\frac{1}{2})^x$**.
        
- Ora confrontiamo la nostra base $a = \frac{1}{3}$ con la base di $f_2$, cioè $a_2 = \frac{1}{2}$.
    
    - $\frac{1}{3} \approx 0.33...$
        
    - $\frac{1}{2} = 0.5$
        
    - Quindi, $\frac{1}{3} < \frac{1}{2}$.
        
- La nostra base ($\frac{1}{3}$) è _più piccola_ di quella di $f_2$ ($\frac{1}{2}$).
    
- Come abbiamo detto nella regola del Caso 2, una base più piccola significa un grafico **più ripido**.
    
- Tra $f_1$ e $f_2$, il grafico più ripido è $f_1$.
    

**Conclusione:** Il grafico della funzione $y = (\frac{1}{3})^x$ è **$f_1$**.

---

### Espansione e Altri Casi (Cosa potrebbe capitarti)

1. **Simmetria (molto comune!):**
    
    - Hai notato che $f_2(x) = (\frac{1}{2})^x$ e $f_3(x) = 2^x$? (Abbiamo dedotto $f_3$ dal punto $(1, 2)$).
        
    - Una funzione con base $a$ (es. $2^x$) e una con base $\frac{1}{a}$ (es. $(\frac{1}{2})^x$) sono **l'una la riflessione speculare dell'altra rispetto all'asse $y$**.
        
    - Nello stesso modo, siccome $f_1$ è $y = (\frac{1}{3})^x$, è molto probabile che $f_4$ (la sua simmetrica) sia $y = 3^x$.
        
2. **Traslazioni Verticali ($y = a^x + k$):**
    
    - **Esempio:** $y = 2^x + 3$.
        
    - Prendi il grafico di $y = 2^x$ (il nostro $f_3$) e lo **sposti 3 unità verso l'alto**.
        
    - Il punto $(0, 1)$ diventa $(0, 1+3) = (0, 4)$.
        
    - L'asintoto orizzontale, che di solito è l'asse $x$ ($y=0$), diventa $y=3$.
        
3. **Traslazioni Orizzontali ($y = a^{(x-h)}$):**
    
    - **Esempio:** $y = 2^{(x-1)}$.
        
    - Prendi il grafico di $y = 2^x$ (il nostro $f_3$) e lo **sposti 1 unità verso destra**. (Attenzione: $x-1$ significa destra, $x+1$ significa sinistra).
        
    - Il punto $(0, 1)$ diventa $(0+1, 1) = (1, 1)$.
        
4. **Riflessione sull'asse x ($y = -a^x$):**
    
    - **Esempio:** $y = -2^x$.
        
    - Prendi il grafico di $y = 2^x$ (il nostro $f_3$) e lo **ribalti "sottosopra" rispetto all'asse $x$**.
        
    - Il punto $(0, 1)$ diventa $(0, -1)$. La funzione sarà sempre negativa.
        

### Riepilogo per il Test

Per riconoscere un grafico esponenziale $y = a^x$:

1. **Guarda la Base $a$**:
    
    - $a > 1$? **Crescente** (come $f_3, f_4, f_5$).
        
    - $0 < a < 1$? **Decrescente** (come $f_1, f_2$).
        
2. **Controlla il punto $(0, 1)$**: Ci passa? Se no, è stata traslata.
    
3. **Confronta la ripidità**:
    
    - Se $a > 1$, base più grande = più ripida.
        
    - Se $0 < a < 1$, base più piccola = più ripida.
        
4. **Testa un punto**: Se sei in dubbio, prova $x=1$ (dovrebbe darti $y=a$) o $x=-1$ (dovrebbe darti $y = \frac{1}{a}$). Questo di solito risolve ogni dubbio.

## Domanda 3 

![[Domanda 4.png]]