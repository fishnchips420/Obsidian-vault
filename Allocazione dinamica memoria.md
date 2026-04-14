Ecco la guida completa alla **Memoria Dinamica** in C, strutturata esattamente come quella per i file: teoria essenziale, sintassi pratica, esempi "copia-incolla" e trappole comuni.

---

### 1. Sintesi Teorica: Stack vs Heap

Per capire la memoria dinamica, devi immaginare la memoria del computer divisa in due grandi zone:

1. **Lo Stack (Pila):** È la zona "automatica" e rigida.
    
    - Qui vivono le variabili normali (`int a`, `char buff[10]`).
        
    - **Pro:** Veloce e gestita da sola.
        
    - **Contro:** Devi sapere la dimensione _prima_ di compilare. Non puoi dire "crea un array grande quanto vuole l'utente" (o meglio, in C standard puro C90 non si può). Se la funzione finisce, le variabili muoiono.
        
2. **Lo Heap (Mucchio):** È la zona "manuale" e gigante.
    
    - Qui decidi tu, **durante l'esecuzione** (runtime), quanta memoria prendere.
        
    - **Pro:** Puoi creare array enormi o di dimensione variabile decisa dall'utente. La memoria resta lì finché non la cancelli tu.
        
    - **Contro:** Devi gestirla manualmente. Se ti dimentichi di liberarla, crei un _Memory Leak_ (perdi memoria).
        

**In breve:** La memoria dinamica serve quando **non sai a priori** quanti dati dovrai gestire.

---

### 2. Guida Pratica ai Comandi (`stdlib.h`)

Per usare queste funzioni devi includere `<stdlib.h>`.

#### A. `malloc` (Memory Allocation)

Chiede al sistema un blocco di byte grezzi.

- **Sintassi:** `void* malloc(size_t size);`
    
- **Concetto:** "Dammi X byte".
    
- **Uso Tipico:** Si usa insieme a `sizeof` per calcolare i byte corretti.
    

C

```c
int *v;
// Chiedo spazio per 10 interi
// (10 * 4 byte = 40 byte totali)
v = (int*) malloc(10 * sizeof(int));
```

_Nota:_ Il `(int*)` davanti si chiama _casting_. In C puro non è obbligatorio, ma è consigliato per chiarezza: "Tratta questi byte grezzi come puntatori a interi".

#### B. `calloc` (Contiguous Allocation)

Simile a malloc, ma fa due cose in più:

1. Prende due parametri (numero elementi, dimensione singolo elemento).
    
2. **Azzera tutta la memoria** (mette tutto a 0). `malloc` invece lascia "spazzatura" in memoria.
    

C

```c
// Spazio per 10 interi, tutti inizializzati a 0
v = (int*) calloc(10, sizeof(int));
```

#### C. `realloc` (Re-Allocation)

Serve a ridimensionare un blocco di memoria già esistente (allargarlo o restringerlo).

- **Scenario:** Hai fatto un array di 10 posti, ma l'utente vuole inserirne un 11°.
    
- **Sintassi:** `p_nuovo = realloc(p_vecchio, nuova_dimensione_totale);`
    

C

```c
// Allargo l'array v da 10 a 20 interi
v = (int*) realloc(v, 20 * sizeof(int));
```

#### D. `free` (Liberazione)

Fondamentale. Restituisce la memoria al sistema. Va usata quando hai finito di usare quella variabile.

- **Regola d'oro:** Per ogni `malloc` (o `calloc/realloc`) deve esserci una `free`.
    

C

```c
free(v); // Libero la memoria puntata da v
v = NULL; // Buona norma: metto a NULL per non usarlo per sbaglio dopo
```

---

### 3. Pattern Standard: L'Array Dinamico

Questo è l'esempio che userai nel 90% degli esercizi d'esame: chiedere all'utente quanti numeri vuole inserire e creare un array di quella misura esatta.

C

```c
#include <stdio.h>
#include <stdlib.h> // INDISPENSABILE

int main() {
    int *vettore; // Dichiaro un PUNTATORE, non un array fisso v[100]
    int n, i;

    // 1. Chiedo la dimensione
    printf("Quanti numeri vuoi inserire? ");
    scanf("%d", &n);

    // 2. Allocazione Dinamica (malloc)
    // Formula: N_ELEMENTI * sizeof(TIPO)
    vettore = (int*) malloc(n * sizeof(int));

    // 3. CONTROLLO FONDAMENTALE (Safety Check)
    // Se la RAM è piena, malloc restituisce NULL.
    if (vettore == NULL) {
        perror("Memoria esaurita o errore di allocazione");
        exit(1);
    }

    // 4. Uso il vettore come se fosse un array normale
    // Il C tratta i puntatori come array: vettore[i] funziona!
    for (i = 0; i < n; i++) {
        vettore[i] = i * 10; // Riempio con 0, 10, 20...
        printf("v[%d] = %d\n", i, vettore[i]);
    }

    // 5. Pulizia (free)
    free(vettore);
    
    return 0;
}
```

---

### 4. Struct e Memoria Dinamica

Spesso devi allocare dinamicamente un array di struct (es. un elenco di studenti di dimensione variabile).

C

```c
typedef struct {
    char nome[30];
    int voto;
} Studente;

int main() {
    Studente *classe; // Puntatore alla struct
    int numero_studenti = 5;

    // Alloco spazio per 5 strutture Studente
    classe = (Studente*) malloc(numero_studenti * sizeof(Studente));
    
    if (classe == NULL) exit(1);

    // Accesso ai campi (uguale agli array statici)
    // Non serve -> ma basta il punto . perché classe[i] è l'oggetto vero e proprio
    classe[0].voto = 28;
    
    free(classe);
}
```

---

### 5. Errori Comuni e "Crash"

Ecco la lista nera degli errori con la memoria dinamica:

1. Dimenticare la free (Memory Leak):
    
    Il programma funziona, ma consuma sempre più RAM finché il PC non si blocca.
    
2. **Usare la memoria dopo la `free` (Dangling Pointer):**
    
    C
    
    ```c
    free(v);
    v[0] = 5; // CRASH! O comportamento impazzito.
    ```
    
3. **Doppia `free`:**
    
    C
    
    ```c
    free(v);
    free(v); // CRASH! Il sistema va in panico perché cerchi di liberare il vuoto.
    ```
    
4. Segfault (Segmentation Fault):
    
    Accade se malloc fallisce (restituisce NULL) e tu provi a scriverci dentro senza controllare.
    
    - _Sbagliato:_ `v = malloc(...); v[0] = 5;`
        
    - _Giusto:_ `v = malloc(...); if (v!=NULL) v[0] = 5;`
        

### Esercizio Rapido per Te

Prova a modificare l'esercizio del "Magazzino" che abbiamo fatto prima:

Invece di struttura1 str1[DIM] (dove DIM era 50 fisso), chiedi all'utente all'inizio: "Quanti prodotti devi caricare?".

Poi usa malloc per creare l'array della dimensione esatta richiesta.

Dimmi se vuoi provare a scrivere questo codice!