### 1. Operatori LOGICI (Booleani)

Si usano nelle condizioni (es. if, while). Il loro risultato è sempre 1 (Vero) o 0 (Falso).

Ricorda: In C, 0 è falso, qualsiasi altro numero è vero.

| **Simbolo** | **Nome**       | **Descrizione**                         | **Esempio**           | **Risultato**                  |
| ----------- | -------------- | --------------------------------------- | --------------------- | ------------------------------ |
| **`         |                | `**                                     | **OR Logico**         | Vero se **almeno uno** è vero. |
| **`&&`**    | **AND Logico** | Vero solo se **tutti e due** sono veri. | `(5 > 0) && (5 < 10)` | **1** (Vero)                   |
| **`!`**     | **NOT Logico** | Inverte il valore (Vero diventa Falso). | `!(5 > 0)`            | **0** (Falso)                  |

> **Nota:** Non esiste un operatore logico specifico per lo XOR in C (tipo `^^`). Per i valori booleani, lo XOR logico si simula semplicemente con `!=` (diverso).

---

### 2. Operatori BITWISE (Bit a Bit)

Questi lavorano sulla rappresentazione binaria dei numeri. Prendono i bit dei due numeri e li confrontano posizione per posizione.

Prendiamo due numeri di esempio (su 4 bit):

- **A = 5** (in binario `0101`)
    
- **B = 6** (in binario `0110`)
    

|**Simbolo**|**Nome**|**Logica (Bit per Bit)**|**Esempio (A=5, B=6)**|**Calcolo**|**Risultato**|
|---|---|---|---|---|---|
|**`|`**|**OR**|**1** se almeno un bit è 1.|`5|6`|
|**`&`**|**AND**|**1** solo se entrambi i bit sono 1.|`5 & 6`|`0101` AND `0110`|`0100` (**4**)|
|**`^`**|**XOR**|**1** se i bit sono **diversi** (uno 1, l'altro 0).|`5 ^ 6`|`0101` XOR `0110`|`0011` (**3**)|
|**`~`**|**NOT**|Inverte tutti i bit (0→1, 1→0).|`~5`|NOT `0101`|`1010` (dipende dal segno)|
|**`<<`**|**Shift Sx**|Sposta i bit a sinistra (moltiplica per 2).|`5 << 1`|`0101` diventa `1010`|**10**|
|**`>>`**|**Shift Dx**|Sposta i bit a destra (divide per 2).|`6 >> 1`|`0110` diventa `0011`|**3**|

---

### La Trappola dell'Esame: `||` vs `|`

È l'errore più comune. Guarda la differenza:

**Caso A: Logico (`||`)**

C

```
int x = 2; // (Vero perché non è 0)
int y = 1; // (Vero perché non è 0)

// "È vero x OPPURE è vero y?" -> SÌ.
int ris = x || y; 
// ris vale 1 (Vero)
```

**Caso B: Bitwise (`|`)**

C

```
int x = 2; // Binario: 0010
int y = 1; // Binario: 0001

// "Fai l'OR dei bit di x e y"
int ris = x | y;
//   0010
// | 0001
// ------
//   0011 -> che vale 3
// ris vale 3
```

### Sintesi rapida per ricordarli

1. **Doppio simbolo (`||`, `&&`)**: Sono **LOGICI**. Servono per dire "SE succede questo OPPURE quello".
    
2. **Simbolo singolo (`|`, `&`, `^`)**: Sono **MATEMATICI/BINARI**. Servono per modificare i bit di un numero.
    
3. **XOR (`^`)**: Esiste solo come operatore bitwise (simbolo cappelletto). "O l'uno o l'altro, ma non tutti e due".
    
