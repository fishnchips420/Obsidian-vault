Preparare il test OFA (Obblighi Formativi Aggiuntivi) richiede precisione: spesso le domande non sono difficili, ma sono formulate per scovare le lacune di base e gli errori di distrazione.

Ecco un ripasso strutturato per punti chiave e "trappole" comuni da evitare, organizzato per le macro-aree che hai indicato.

---

### 1. Logica e Insiemistica

Questi sono i "mattoni" del linguaggio matematico.

- **Logica delle Proposizioni:**
    
    - **Implicazione ($A \implies B$):** È falsa **solo** se $A$ è vera e $B$ è falsa. Ricorda che $A \implies B$ è equivalente a $\neg B \implies \neg A$ (contronominale), ma **non** a $\neg A \implies \neg B$.
        
    - **Legge di De Morgan:**
        
        - $\neg (A \land B) \iff (\neg A \lor \neg B)$
            
        - $\neg (A \lor B) \iff (\neg A \land \neg B)$
            
    - **Quantificatori:** La negazione di "Tutti..." ($\forall$) è "Esiste almeno uno che non..." ($\exists$), non "Nessuno".
        
- **Insiemistica:**
    
    - **Intersezione ($A \cap B$):** Elementi comuni.
        
    - **Unione ($A \cup B$):** Elementi in $A$ oppure in $B$ (o in entrambi).
        
    - **Differenza ($A \setminus B$):** Elementi che sono in $A$ ma **non** in $B$.
        
- **Insiemi Numerici:**
    
    - $\mathbb{N} \subset \mathbb{Z} \subset \mathbb{Q} \subset \mathbb{R}$.
        
    - Ricorda: $\sqrt{2}$ e $\pi$ sono in $\mathbb{R}$ ma non in $\mathbb{Q}$ (irrazionali). I numeri periodici sono in $\mathbb{Q}$.
        

---

### 2. Algebra: Polinomi, Equazioni e Disequazioni

Qui si gioca sulla velocità di calcolo e sullo studio dei segni.

- **Polinomi e Prodotti Notevoli:**
    
    - Differenza di quadrati: $a^2 - b^2 = (a-b)(a+b)$.
        
    - Quadrato di binomio: $(a \pm b)^2 = a^2 \pm 2ab + b^2$.
        
    - **Teorema di Ruffini:** Se un polinomio $P(x)$ si annulla per $x=a$ (cioè $P(a)=0$), allora è divisibile per $(x-a)$.
        
- Equazioni di 2° grado:
    
    $$x_{1,2} = \frac{-b \pm \sqrt{\Delta}}{2a}$$
    
    - Se $\Delta > 0$: due soluzioni reali distinte.
        
    - Se $\Delta = 0$: due soluzioni reali coincidenti.
        
    - Se $\Delta < 0$: nessuna soluzione reale.
        
- **Disequazioni Fratte ($\frac{N(x)}{D(x)} \ge 0$):**
    
    1. Poni $N(x) \ge 0$.
        
    2. Poni $D(x) > 0$ (**Mai** $\ge$ al denominatore, non puoi dividere per 0).
        
    3. Fai il grafico dei segni.
        
    
    > **Attenzione:** Nelle disequazioni non puoi mai eliminare il denominatore moltiplicando a destra e sinistra, perché non ne conosci il segno (se fosse negativo, il verso della disuguaglianza cambierebbe).
    

---

### 3. Geometria Analitica: Rette e Coniche

Devi saper associare un'equazione al suo grafico immediatamente.

- **Piano Cartesiano:**
    
    - Distanza tra due punti: $d = \sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$.
        
    - Punto medio: $M = (\frac{x_1+x_2}{2}, \frac{y_1+y_2}{2})$.
        
- **Rette:**
    
    - Forma esplicita: $y = mx + q$.
        
    - $m$: coefficiente angolare (pendenza). Se $m > 0$ cresce, $m < 0$ decresce.
        
    - $q$: intercetta sull'asse $y$.
        
    - **Parallelismo:** $m_1 = m_2$.
        
    - **Perpendicolarità:** $m_1 \cdot m_2 = -1$ (oppure $m_1 = -1/m_2$).
        
- **Coniche:**
    
    - **Circonferenza:** $(x-x_c)^2 + (y-y_c)^2 = r^2$. Centro $(x_c, y_c)$, raggio $r$.
        
    - **Parabola (asse verticale):** $y = ax^2 + bx + c$.
        
        - Vertice: $V = (-\frac{b}{2a}, -\frac{\Delta}{4a})$.
            
        - $a > 0$: concavità verso l'alto (U). $a < 0$: concavità verso il basso.
            
    - **Ellisse:** $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$.
        
    - **Iperbole:** $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$ (o viceversa).
        

---

### 4. Funzioni Elementari

Questa è spesso la parte più corposa del test.

#### Concetti Base

- **Dominio:** L'insieme delle $x$ per cui la funzione esiste.
    
    - Denominatori $\neq 0$.
        
    - Argomenti radici pari $\ge 0$.
        
    - Argomenti logaritmi $> 0$.
        
- **Iniettiva:** A $x$ diverse corrispondono $y$ diverse (test della retta orizzontale).
    

#### Funzioni Specifiche

- **Valore Assoluto ($|x|$):** Rende tutto positivo. Grafico a "V".
    
    - $|A(x)| < k \iff -k < A(x) < k$.
        
    - $|A(x)| > k \iff A(x) < -k \lor A(x) > k$.
        
- **Esponenziali ($a^x$) e Logaritmi ($\log_a x$):**
    
    - Sono una l'inversa dell'altra.
        
    - **Importante:** Se la base $a > 1$, la funzione cresce (conserva il verso nelle disequazioni). Se $0 < a < 1$, la funzione decresce (**inverte** il verso nelle disequazioni).
        
    - Proprietà logaritmi: $\log(a \cdot b) = \log a + \log b$; $\log(a^k) = k \log a$.
        
- **Trigonometria:**
    
    - Relazione fondamentale: $\sin^2 x + \cos^2 x = 1$.
        
    - Periodicità: $\sin$ e $\cos$ hanno periodo $2\pi$, $\tan$ ha periodo $\pi$.
        
    - Valori notevoli: Ricorda assolutamente i valori di seno e coseno a $0, \pi/6, \pi/4, \pi/3, \pi/2$.
        

![Immagine di exponential and logarithmic function graphs](https://encrypted-tbn1.gstatic.com/licensed-image?q=tbn:ANd9GcS-yi5cHPdZCJccrUlUt0pNVhNQbvSlxiHWWsqLG3zES-P-9av9HEsNw5s03Dda1TmMlmUJoLROCPlSsazs15-dVcCqMbZMrT5uVDLQSVzPWmPtqIk)

Shutterstock

---

### 5. Trasformazioni di Grafici

Se conosci il grafico di $y = f(x)$, puoi dedurre velocemente gli altri:

1. ==**Traslazioni:**==
    
    - ==$y = f(x) + k$: Traslazione verticale (su se $k>0$, giù se $k<0$).==
        
    - ==$y = f(x + k)$: Traslazione orizzontale (**sinistra** se $k>0$, **destra** se $k<0$). _Attenzione a questo segno opposto!_==
        
2. ==**Riflessioni:**==
    
    - ==$y = -f(x)$: Ribaltamento rispetto all'asse $x$ (ciò che è su va giù).==
        
    - ==$y = f(-x)$: Ribaltamento rispetto all'asse $y$ (destra diventa sinistra).==
        
    - ==$y = |f(x)|$: La parte di grafico sotto l'asse $x$ viene ribaltata sopra.==
        
3. ==**Riscalamenti:**==
    
    - ==$y = k \cdot f(x)$: Dilatazione verticale (se $k>1$).==
        
    - ==$y = f(k \cdot x)$: Contrazione orizzontale (se $k>1$, la funzione "accelera").==
        

---

### Come affrontare il test OFA

1. **Dominio prima di tutto:** In molte domande a risposta multipla, puoi scartare 2 o 3 risposte solo controllando il dominio (es. presenza di logaritmi di numeri negativi).
    
2. **Sostituzione:** Se ti chiedono "Qual è la soluzione dell'equazione...", a volte è più veloce provare a sostituire i valori delle risposte nell'equazione piuttosto che risolverla da zero.
    
3. **Disegno:** Fai sempre uno schizzo rapido del grafico quando si parla di intersezioni o disequazioni complesse.
    

**Vuoi che proviamo a fare una simulazione di 3 domande "tipo" su uno di questi argomenti (es. logaritmi o coniche) per vedere come te la cavi?**