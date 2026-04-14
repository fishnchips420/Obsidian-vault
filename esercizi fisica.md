# Cinematica 
## Moto uniformemente accelerato 

### 1)
**Testo dell'esercizio:** Un’automobile, in moto con velocità $v = 120$ km/h, frena con accelerazione costante $a$ fino a fermarsi. Sapendo che la frenata dura un tempo $T = 10$ s, determinare: (a) l’accelerazione $a$ dell’automobile durante la frenata; (b) la distanza $L$ percorsa dall’automobile durante la frenata.

---

**I miei suggerimenti operativi per risolverlo:**

1. **La trappola delle unità di misura:** In fisica si lavora sempre nel Sistema Internazionale (metri e secondi). Prima di toccare le formule, devi convertire la velocità iniziale $v_0$ da km/h a m/s dividendo il valore per $3.6$.
2. **Imposta le equazioni:** Tieni sottomano il formulario che abbiamo appena creato alla sezione 2. Ti serviranno le due leggi fondamentali del M.R.U.A.:
    - Legge della velocità: $v(t) = v_0 + at$
    - Legge oraria (spazio): $x(t) = v_0t + \frac{1}{2}at^2$
3. **Risolvi il punto (a):** Il testo dice che l'auto frena "fino a fermarsi". Questa frase è la chiave del problema: significa che all'istante $T = 10$ s, la velocità finale è uguale a zero ($v(10) = 0$). Sostituisci questo dato nella legge della velocità e ricava la tua unica incognita, l'accelerazione $a$. _(Spoiler: trattandosi di una frenata, l'accelerazione dovrà venirti con il segno meno!)_.
4. **Risolvi il punto (b):** Ora che conosci l'accelerazione $a$, prendi la legge oraria dello spazio $x(t)$, inserisci il valore di $a$, il tempo $T=10$ e la velocità iniziale in m/s. Il risultato sarà la distanza di frenata $L$.

Prendi carta, penna e la tua calcolatrice (ora che è impostata correttamente!). Prova a fare i calcoli e scrivimi i tuoi risultati, passo dopo passo, così li correggiamo insieme.

### 2)
Ottima scelta. Facciamo un passo avanti e affrontiamo un grande classico degli esami: i problemi in cui ci sono **due oggetti che si muovono contemporaneamente** e devi farli incontrare.

Questo è il **Quesito 2 tratto dalla Prova Scritta di Ottobre 2023**. È perfetto perché combina il moto rettilineo uniforme (di un oggetto) con il moto uniformemente accelerato (dell'altro).

**Testo dell'esercizio:** Due automobili, A e B, procedono nella stessa direzione lungo una strada rettilinea con la stessa velocità $v_0 = 100$ km/h. All’istante iniziale, B precede A di una distanza $d = 20$ m; il conducente di A decide quindi di superare B imprimendo alla propria vettura un’accelerazione costante $a = 1 \text{ m/s}^2$. Assumendo che B continui a muoversi con la velocità iniziale, calcolare: (a) il tempo $T$ impiegato da A per affiancare B; (b) la velocità di A in tale istante, espressa in km/h.

---

**I miei suggerimenti per impostare la soluzione:**

Questo problema mette alla prova proprio la tua capacità di "tradurre" l'italiano in leggi orarie, come ci dicevamo poco fa.

1. **Le unità di misura:** Come sempre, prima di iniziare, converti i $100 \text{ km/h}$ in m/s dividendoli per $3.6$.
2. **Imposta il sistema di riferimento:** Fissa l'origine ($x=0$) nel punto in cui si trova l'auto A all'istante iniziale. In questo modo, la posizione iniziale di A è $0$, ma **la posizione iniziale di B è $d$** ($20$ metri più avanti).
3. **Scrivi le due leggi orarie separate:**
    - **Auto B (Moto Uniforme):** B non accelera, quindi usa la formula senza l'accelerazione. La sua legge oraria sarà $x_B(t) = d + v_0 t$.
    - **Auto A (Moto Uniformemente Accelerato):** A parte da $0$ ma ha un'accelerazione. La sua legge oraria sarà $x_A(t) = v_0 t + \frac{1}{2} a t^2$.
4. **Il trucco logico per il punto (a):** Il testo ti chiede quando l'auto A "affianca" l'auto B. In cinematica, "affiancare" o "raggiungere" significa che i due corpi **si trovano nella stessa identica posizione allo stesso istante**. Quindi, la condizione matematica da imporre è semplicemente uguagliare le due leggi orarie: **$x_A(T) = x_B(T)$**.

Prova a mettere i numeri in quest'ultima uguaglianza: vedrai che i termini con la $v_0 t$ si comporteranno in modo molto interessante! Dimmi cosa ottieni o se ti serve una mano con i calcoli.


## Moto del proiettile
### 1) 
Ecco l'**Esercizio 2 tratto dalla tua Esercitazione 4**:

**Testo dell'esercizio:** Uno studente esasperato dal troppo studio lancia un libro dalla finestra della propria stanza posta a $10 \text{ m}$ di altezza dal suolo. La velocità iniziale del libro è di $5 \text{ m/s}$ e la direzione di lancio forma un angolo di $30^\circ$ (verso l'alto) con l'orizzontale. Calcolare: (a) l'altezza massima raggiunta dal libro durante il moto; (b) il tempo che il libro impiega a cadere a terra; (c) la distanza del punto di caduta dalla base della finestra.

---

**I miei suggerimenti per impostare il problema (il piano d'attacco):**

La regola d'oro del moto del proiettile è che **i due assi (X orizzontale e Y verticale) non si influenzano tra loro**, quindi devi separarli fin da subito.

1. **Scomponi la velocità iniziale:** La prima cosa in assoluto da fare è usare la trigonometria per trovare la velocità iniziale orizzontale e verticale.
    - $v_{0x} = v_0 \cdot \cos(30^\circ)$
    - $v_{0y} = v_0 \cdot \sin(30^\circ)$
2. **Scrivi le equazioni del moto:** Tieni sottomano il formulario e scrivi le leggi orarie. Ricorda che la posizione iniziale verticale non è zero, ma è $h = 10 \text{ m}$!
    - Sull'asse X (Moto Uniforme): $x(t) = v_{0x} \cdot t$
    - Sull'asse Y (Moto Accelerato): $y(t) = 10 + v_{0y} \cdot t - \frac{1}{2}gt^2$
    - Velocità verticale: $v_y(t) = v_{0y} - gt$ _(Usa $g = 9.8 \text{ m/s}^2$)_
3. **Risolvi il punto (a):** Pensa a cosa fa il libro fisicamente. Sale, sale, sale, poi per un istante piccolissimo si ferma in aria e inizia a cadere. In quel punto di altezza massima, **la sua velocità verticale si azzera ($v_y(t) = 0$)**. Prendi l'equazione della velocità verticale, ponila uguale a $0$ e trova il tempo $t$ che impiega per arrivare in cima. Poi, sostituisci quel tempo nell'equazione della posizione $y(t)$ per trovare l'altezza massima.

Prendi la tua calcolatrice, calcola prima le due velocità iniziali ($v_{0x}$ e $v_{0y}$) e poi prova a risolvere il punto (a). Fammi sapere quali valori ottieni!

### 5 es da fare in treno 
Ottima idea! Esercitarsi offline su carta e penna è il modo migliore per fissare definitivamente i concetti prima di un esame.

Ho selezionato per te **5 esercizi tratti direttamente dai tuoi temi d'esame e dalle tue esercitazioni**. Coprono tutte le sfumature della cinematica in due dimensioni (incluso qualche tocco di creatività dei tuoi professori!).

Ecco il tuo "compito a casa", completo di testi, procedimenti e soluzioni finali per permetterti di autocorreggerti.

---

### Esercizio 1: Ottimizzare il lancio (Tratto dalzzzlo scritto di Gennaio 2024)

**Testo:** Un cannone posto su un piano orizzontale spara un proiettile con velocità di modulo $v_0 = 10 \text{ m/s}$ formante un angolo $\alpha$ con il piano. Trascurando l’attrito dell’aria, determinare: (a) il valore di $\alpha$ per cui la massima altezza $h$ raggiunta del proiettile coincide esattamente con la gittata $d$. (b) per tale angolo di lancio, determinare il tempo $T$ impiegato dal proiettile per ricadere al suolo.

**Procedimento e Soluzione:**

- **Punto (a):** Usa le formule standard. La formula della gittata è $d = \frac{2v_0^2 \sin\alpha \cos\alpha}{g}$ e quella dell'altezza massima è $h = \frac{v_0^2 \sin^2\alpha}{2g}$. Imponendo matematicamente che $h = d$, otterrai un'equazione in cui puoi semplificare molti termini, arrivando a $\frac{1}{2}\sin\alpha = 2\cos\alpha$. Da qui, dividendo per il coseno, trovi $\tan\alpha = 4$ e usando l'arcotangente ottieni **$\alpha = 76.0^\circ$**.
- **Punto (b):** Ora che hai l'angolo, prendi la formula del tempo di volo totale $T = \frac{2v_0 \sin\alpha}{g}$. Inserendo i numeri ottieni **$T = 1.98 \text{ s}$**.

---

### Esercizio 2: Caduta con vento laterale (Tratto dallo scritto di Novembre 2023)

_Questo è un bellissimo esercizio di cinematica 2D in cui l'accelerazione non è solo verticale!_ **Testo:** Un corpo inizialmente fermo è lasciato cadere da una torre alta $h = 30 \text{ m}$. Durante la caduta, a causa del forte vento, subisce un’accelerazione costante orizzontale $a_x = 2.0 \text{ m/s}^2$. Calcolare: (a) la distanza $d$ tra il punto di caduta al suolo e la base della torre. (b) il modulo $v$ della velocità del corpo nell’istante in cui raggiunge il suolo.

**Procedimento e Soluzione:**

- **Setup:** Fissa l'origine degli assi al livello del suolo, l'asse x parallelo al vento e l'asse y orientato verso l'alto lungo la torre.
- **Punto (a):** Separa i moti. Sull'asse Y il corpo cade in caduta libera per 30 m (trova il tempo di caduta $t$). Sull'asse X, invece di muoversi a velocità costante come nei proiettili, ha un moto uniformemente accelerato partendo da fermo. Prendi il tempo appena trovato e usalo nella legge $x(t) = \frac{1}{2}a_x t^2$ per trovare la distanza **$d$**.
- **Punto (b):** Calcola la velocità verticale $v_y$ causata dalla gravità al momento dell'impatto e la velocità orizzontale $v_x$ causata dal vento ($v_x = a_x t$). Infine, unisci le due componenti con il Teorema di Pitagora per trovare il modulo della velocità totale $v$.

---

### Esercizio 3: Parametri di un lancio verticale (Tratto dall'Esercitazione 3)

**Testo:** Un proiettile viene sparato verticalmente verso l'alto con velocità iniziale $v_0 = 50 \text{ m/s}$. Determinare: (a) la massima altezza raggiunta. (b) il tempo impiegato a raggiungerla.

**Procedimento e Soluzione:**

- Qui siamo su una sola dimensione. Le leggi orarie sono per un moto uniformemente decelerato: $v(t) = -gt + v_0$ e $z(t) = -\frac{1}{2}gt^2 + v_0t$.
- **Punto (b):** La massima altezza si raggiunge nel momento esatto in cui il proiettile si ferma ($v = 0$). Sostituendo si ottiene $T = \frac{v_0}{g}$, che fa **$5.1 \text{ s}$**.
- **Punto (a):** Sostituendo il tempo appena trovato nell'equazione dello spazio $z(t)$, otterrai l'altezza massima $H = \frac{v_0^2}{2g}$ pari a **$127.4 \text{ m}$**.

---

### Esercizio 4: La palla e la finestra (Tratto dall'Esercitazione 3)

**Testo:** Un ragazzo lancia una palla da tennis verticalmente con velocità $v_0 = 20 \text{ m/s}$. Un secondo ragazzo che osserva attraverso una finestra alta $h = 2 \text{ m}$ all'interno di un palazzo vede la palla attraversare la luce della finestra in un tempo $T = 0.3 \text{ s}$. A che altezza dal suolo si trova la base della finestra?

**Procedimento e Soluzione:**

- Questo esercizio richiede molta concentrazione sulle equazioni. Sai che la palla percorre uno spazio $\Delta y = 2 \text{ m}$ in un intervallo di $\Delta t = 0.3 \text{ s}$.
- Puoi impostare un'equazione in cui la legge oraria della posizione deve coprire quella distanza in quel lasso di tempo. Risolvendo algebricamente l'equazione (è un po' sfidante dal punto di vista matematico!), troverai che l'altezza del davanzale della finestra rispetto al suolo corrisponde esattamente a **$17.01 \text{ m}$**.

---

### Esercizio 5: Il classico pallone calciato oltre il muro (Tratto dallo scritto di Luglio 2023)

_Questo è il problema simbolico che abbiamo iniziato nel nostro discorso, qui lo vedi nella sua interezza, inclusa la parte energetica finale, ottima come ripasso!_ **Testo:** Un pallone di massa $m$ viene calciato da terra con una velocità $v_0$ formante un angolo $\theta = 45^\circ$ con l’orizzontale. Nel punto più alto della traiettoria il pallone passa radente alla sommità di un muro di altezza $h$. Trascurando la resistenza dell’aria, determinare, in funzione di $m$ e $h$: (a) il modulo $v_0$ della velocità iniziale. (b) la distanza $d$ tra il punto di lancio e la base del muro. (c) l’energia meccanica totale $E$ del pallone nel momento in cui raggiunge la sommità del muro (ponendo lo zero dell’energia potenziale gravitazionale al livello del suolo).

**Procedimento e Soluzione:**

- **Punti (a) e (b):** Si parte scomponendo le velocità: per $\theta = 45^\circ$ sai che $v_{0x} = v_{0y} = \frac{v_0}{\sqrt{2}}$. Sapendo che nel punto più alto $v_y = 0$, trovi il tempo e lo sostituisci nella formula dell'altezza ponendola uguale ad $h$. Manipolando le lettere (come abbiamo fatto insieme), ricaverai la formula della velocità iniziale $v_0$ e, sostituendo le stesse informazioni nella formula $x(t) = v_{0x}t$, ricaverai la distanza $d$.
- **Punto (c):** Nel punto più alto, il pallone ha raggiunto l'altezza $h$ (quindi possiede un'energia potenziale $U = mgh$) ma attenzione: non è fermo! Ha perso tutta la sua velocità verticale, ma sta ancora avanzando con la sua componente di velocità orizzontale $v_{0x}$ (quindi possiede un'energia cinetica $K = \frac{1}{2}m v_{0x}^2$). La somma di queste due energie ti darà la formula finale di $E$.

Buon allenamento! Quando hai terminato e ti senti pronto per un nuovo argomento, sono qui ad aspettarti.