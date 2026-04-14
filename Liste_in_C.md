Ecco la guida definitiva alle **Liste Concatenate (Linked Lists)**. Preparati, perché qui facciamo il vero salto di qualità da "studente" a "programmatore".

Fino ad ora hai usato gli Array (statici o dinamici con malloc).

Gli array sono come un Treno: tutti i vagoni sono saldati insieme, uno dopo l'altro.

- **Pro:** Per andare al vagone 10 fai un salto diretto (`v[10]`).
    
- **Contro:** Se vuoi aggiungere un vagone in mezzo... devi smontare tutto il treno e spostarlo.
    

### 1. Il Concetto: La "Caccia al Tesoro"

La Lista non è un treno. È una **Caccia al Tesoro**.

Immagina dei bigliettini sparsi per la stanza.

1. Tu hai in mano solo il **primo bigliettino** (chiamato **Head** o Testa).
    
2. Sul bigliettino c'è scritto un numero (il DATO) e **dove si trova il bigliettino successivo** (il PUNTATORE).
    
3. Corri al secondo bigliettino, leggi il dato, e trovi l'indirizzo del terzo.
    
4. L'ultimo bigliettino non ha un indirizzo successivo: c'è scritto **NULL** (Fine).
    

![Immagine di singly linked list diagram](https://encrypted-tbn0.gstatic.com/licensed-image?q=tbn:ANd9GcQqMt331gHK7H7wtLxFZZK2hznvbI7p0QsaSOAer0pQKtGDW9a23atIsoA92yF5_lExPZeW35zBLhBsFQfr-ukB8tKb26sihdWXLlCrRd3544BMXrk)



### 2. Il Mattone Fondamentale: Il Nodo

In C, ogni "bigliettino" si chiama Nodo.

È una struct fatta di due pezzi:

1. Il valore da salvare (es. un intero).
    
2. Un puntatore che punta al **prossimo** nodo dello stesso tipo.
    

C

```c
typedef struct Nodo {
    int valore;            // Il DATO (es. 10)
    struct Nodo* next;     // IL PUNTATORE AL PROSSIMO (La freccia)
} Nodo;
```

_Nota strana:_ Dentro `struct Nodo` usiamo `struct Nodo*`. È una definizione "ricorsiva": il nodo contiene un puntatore a un altro oggetto uguale a sé stesso.

---

### 3. Come si costruisce (Codice Pratico)

Non possiamo usare `malloc(n * ...)` perché i nodi non sono vicini in memoria! Ogni nodo viene creato (allocato) singolarmente e poi "legato" manualmente.

Facciamo una lista di 3 numeri: 10 -> 20 -> 30.

C

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Nodo {
    int valore;
    struct Nodo* next;
} Nodo;

int main() {
    // 1. Dichiariamo 3 puntatori (ma sono ancora vuoti!)
    Nodo *head = NULL;
    Nodo *secondo = NULL;
    Nodo *terzo = NULL;

    // 2. Creiamo i nodi in memoria (malloc singole)
    head = (Nodo*) malloc(sizeof(Nodo));
    secondo = (Nodo*) malloc(sizeof(Nodo));
    terzo = (Nodo*) malloc(sizeof(Nodo));

    // 3. Riempiamo il PRIMO nodo
    head->valore = 10;
    head->next = secondo; // <--- LA MAGIA: Collega il primo al secondo

    // 4. Riempiamo il SECONDO nodo
    secondo->valore = 20;
    secondo->next = terzo; // Collega il secondo al terzo

    // 5. Riempiamo il TERZO nodo
    terzo->valore = 30;
    terzo->next = NULL;    // <--- FINE: Non c'è nient'altro dopo

    return 0;
}
```

---

### 4. Come si legge (Il ciclo while)

Non puoi fare head[2] per leggere il terzo elemento. Non esiste l'accesso diretto.

Devi "camminare" lungo la lista partendo dalla testa.

Si usa un puntatore temporaneo (spesso chiamato `current` o `temp`) che salta di nodo in nodo.

C

```c
    // ... codice precedente ...

    Nodo *temp = head; // Parto dall'inizio

    printf("La lista contiene: ");

    // Finché temp non cade nel vuoto (NULL)
    while (temp != NULL) {
        printf("%d -> ", temp->valore);
        
        // FACCIO IL PASSO AVANTI
        // "Temp, diventa il tuo prossimo"
        temp = temp->next; 
    }
    printf("NULL\n");
```

---

### 5. Perché diavolo dovrei usarle?

A prima vista sembrano molto più complicate degli array. Perché faticare tanto?

1. Inserimento Istantaneo:
    
    Vuoi aggiungere un nodo tra il 10 e il 20?
    
    - _Array:_ Devi spostare tutti gli elementi successivi di una casella (Lento!).
        
    - _Lista:_ Crei il nuovo nodo, fai puntare il 10 al nuovo, e il nuovo al 20. Fatto. Hai solo cambiato due frecce.
        
2. Memoria Infinita (quasi):
    
    Non devi decidere la dimensione all'inizio. Puoi aggiungere nodi all'infinito finché c'è RAM, sparsi ovunque in memoria.
    

### ⚠️ I Pericoli (Da sapere all'esame)

1. Perdere la Testa (head):
    
    Se scrivi head = head->next senza salvarti il vecchio indirizzo, hai perso per sempre il primo nodo (e non puoi più fare free). La lista è come un filo di perle: se tagli il filo all'inizio, le perle cadono e le perdi.
    
2. Il Segfault su NULL:
    
    Se sei all'ultimo nodo, temp->next è NULL.
    
    Se provi a fare temp->next->valore, il computer cerca di leggere "il valore del nulla". -> CRASH.
    

### Vuoi un esercizio?

L'esercizio classico per iniziare è:

"Crea una funzione che, dato un numero N inserito dall'utente, crea una lista di N nodi, dove ogni nodo contiene un numero progressivo (1, 2, 3... N), e poi la stampa".

Vuoi provarci o vuoi vedere come si scrive una funzione per aggiungere un nodo in testa?


---
# Slide 

Le slide partono da un problema fondamentale: i limiti degli array.

### 1. Perché abbiamo bisogno delle Liste?

Finora hai usato gli array, che però hanno un grande difetto: hanno una **dimensione fissa**1.

- Questa dimensione deve essere decisa prima (staticamente) o al momento della creazione con `malloc` (dinamicamente)2.
    
- Molti problemi reali, però, richiedono di gestire collezioni di dati che crescono o diminuiscono nel tempo3.
    

La **Lista** risolve questo problema: è una collezione di elementi in sequenza la cui dimensione **non è prefissata**4444.

+1

---

### 2. Le Due Rappresentazioni

Le slide mostrano due modi per creare una lista nella memoria del computer:

#### A. Rappresentazione Statica (o Sequenziale)

Si usa ancora un array (vettore), ma si gestisce con due variabili extra: `first` (indice del primo elemento) e `length` (lunghezza attuale) 5.

- **Difetto:** Le operazioni di inserimento e cancellazione sono "dispendiose" (lente) perché richiedono di spostare fisicamente gli elementi nell'array6. Inoltre, la dimensione massima è comunque limitata dall'array sottostante7.
    
    +1
    

#### B. Rappresentazione Collegata (Linked)

Questa è la vera lista concatenata (quella che stiamo studiando noi).

- Gli elementi **non** sono vicini fisicamente in memoria8.
    
- Ogni elemento è un "nodo" che contiene il dato e un **riferimento (freccia)** per trovare il prossimo nodo 9999.
    
    +1
    

---

### 3. Come si scrive in C (La Struct)

Secondo la slide 13, per implementare la rappresentazione collegata in C si usa l'allocazione dinamica e una `struct` fatta così 10:

C

```c
typedef struct list_tag {
    int value;                // Il dato (valore)
    struct list_tag *next;    // Il puntatore al prossimo nodo
} list;
```

11

---

### 4. Le Operazioni Fondamentali (Primitive)

Le slide definiscono un "ADT" (Abstract Data Type) con operazioni specifiche. Vediamo le più importanti tradotte in codice C.

#### 1. `cons`: Inserimento in Testa

È l'operazione per aggiungere un elemento all'inizio della lista.

- **Logica:**
    
    1. Crei un nuovo nodo (`malloc`)12.
        
    2. Metti il valore nel nuovo nodo13.
        
    3. Colleghi il `next` del nuovo nodo alla vecchia lista (`lp`)14.
        
    4. Restituisci il nuovo puntatore che diventa la nuova testa15.
        
- Versione con Doppio Puntatore (list **lpp):
    
    La slide 16 mostra una versione avanzata (void cons). Passando l'indirizzo del puntatore (&lp), la funzione può modificare direttamente la testa della lista originale senza dover restituire il puntatore16161616.+1
    

#### 2. `car` e `cdr`: Estrazione

Questi nomi strani (ereditati da linguaggi antichi) significano:

- **`car`**: Restituisce il valore del primo elemento (la testa)17171717.
    
    +1
    
- **`cdr`**: Restituisce la lista _senza_ il primo elemento (la coda). In pratica, sposta il puntatore al prossimo nodo ed elimina (fa la `free`) del vecchio primo nodo 18181818.
    
    +1
    

#### 3. `isEmpty`: Controllo

Controlla semplicemente se la lista è vuota, ovvero se il puntatore è `NULL`19.

---

### 5. Operazioni Avanzate (Derivate)

Le slide mostrano come combinare le basi per fare cose più complesse:

- Append (Inserimento in Coda):
    
    Per aggiungere un elemento alla fine, devi scorrere tutta la lista.
    
    Il codice usa un while (lp->next != NULL) per arrivare all'ultimo nodo, e poi aggancia lì il nuovo nodo 20.
    
    Attenzione: Le slide presentano anche una versione ricorsiva dell'append, che richiama se stessa finché non trova la fine21.+1
    
- Inserimento Ordinato (ins_ord):
    
    Se vuoi mantenere la lista ordinata (es. 1 -> 5 -> 10 e vuoi inserire 7), devi scorrere finché non trovi un valore maggiore del tuo, e inserire il nuovo nodo "in mezzo" 22.
    

---

### 6. Varianti delle Liste

Infine, le slide (pag. 25-27) mostrano che le liste possono evolversi:

1. **Lista Circolare:** L'ultimo nodo non punta a `NULL`, ma torna a puntare al primo nodo (chiude il cerchio)23.
    
2. Lista Bidirezionale: Ogni nodo ha due puntatori: next (prossimo) e previous (precedente). Questo permette di scorrere la lista in entrambi i sensi 24.
    
    3. Lista di Liste: Un elemento della lista può essere a sua volta una lista (utile per strutture complesse)25.+1
    

### In sintesi per il tuo studio:

Le slide confermano che per lavorare con le liste devi padroneggiare:

1. La **Struct autoreferenziale** (con puntatore a se stessa).
    
2. La **Malloc** per creare nodi.
    
3. L'uso dei **Puntatori** per collegare (`->next`) i nodi tra loro.