Ecco un esercizio perfetto per consolidare la logica del "camminare" lungo la lista (traversamento).

### 🎯 Missione: "Il Cercatore di Numeri"

Scrivi un programma che faccia queste tre cose:

1. **Caricamento:** Chiedi all'utente di inserire numeri interi (termina con `-1`) e salvali in una lista concatenata (usando l'inserimento in testa che abbiamo appena visto).
    
2. **La Domanda:** Una volta finito l'inserimento, chiedi all'utente: _"Quale numero vuoi cercare?"_.
    
3. **La Ricerca:** Scorri tutta la lista, conta quante volte appare quel numero e stampa il risultato.
    

---

### 💡 Suggerimenti

- Hai bisogno di un contatore intero (es. `int conta = 0;`).
    
- Ti serve un secondo ciclo `while` dopo quello di inserimento.
    
- Nel secondo while, usa un puntatore temporaneo (`temp`) che parte dalla `head`.
    
- **Logica del ciclo di ricerca:**
    
    - Se `temp->valore` è uguale al numero cercato -> aumenta il contatore.
        
    - Fai sempre il passo avanti: `temp = temp->next`.
        

**Provaci!** È molto simile alla stampa, ma con un `if` dentro.

---

### ✅ Soluzione Commentata

Prova a scriverlo da solo prima. Se ti blocchi, ecco come si fa:

C

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Nodo {
    int numero;
    struct Nodo* next;
} Nodo;

int main() {
    Nodo* head = NULL;
    Nodo* nuovo_nodo;
    int input;

    // --- FASE 1: CARICAMENTO (uguale a prima) ---
    printf("Inserisci numeri (-1 per finire):\n");
    while (1) {
        scanf("%d", &input);
        if (input == -1) break;

        nuovo_nodo = (Nodo*) malloc(sizeof(Nodo));
        if (nuovo_nodo == NULL) exit(1);

        nuovo_nodo->numero = input;
        nuovo_nodo->next = head;
        head = nuovo_nodo;
    }

    // --- FASE 2: RICHIESTA DEL TARGET ---
    int target;
    printf("\nQuale numero vuoi contare? ");
    scanf("%d", &target);

    // --- FASE 3: RICERCA E CONTEGGIO ---
    int conta = 0;
    Nodo* temp = head; // Parto dall'inizio senza toccare head!

    while (temp != NULL) {
        // Controllo se il vagone attuale contiene il numero cercato
        if (temp->numero == target) {
            conta++;
        }
        
        // Passo avanti, IMPORTANTE! Altrimenti ciclo infinito
        temp = temp->next;
    }

    printf("\nIl numero %d compare %d volte nella lista.\n", target, conta);

    // --- FASE 4: PULIZIA (Free) ---
    while(head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

Cosa devi notare:

Nel ciclo di ricerca non allochiamo memoria (malloc). Stiamo solo leggendo quello che c'è già. È come se il controllore passasse per il treno contando quante persone hanno il cappello. Non fa salire nessuno, guarda e basta.