
[[#Priorità]]
______
### TIPOLOGIA 1: La Funzione Ricorsiva "Bitwise"

Ti danno una funzione `f(int x)` corta e strana, piena di `&`, `|`, `>>`, e ti chiedono cosa succede a un array.

#### Il Codice "Nemico" (Esempio dall'Esame A)

C

```
int f(int x) {
    if (x == 0) return 0;          // CASO BASE: Se x è 0, fermati.
    return (x & 1) | f(x >> 1);    // PASSO RICORSIVO
}
```

#### Come analizzarla (Senza andare nel panico)

Non cercare di indovinare cosa fa. **Eseguila come un robot.**

Prendiamo `x = 5`.

In binario: `101`.

1. **Chiamata f(5) `101`:**
    
    - `x` è 0? No.
        
    - `(x & 1)`: L'ultimo bit è 1? **SÌ**. (Risultato parziale: **1**)
        
    - `f(x >> 1)`: Chiama `f(2)` (perché `101` shiftato diventa `10` cioè 2).
        
    - Operazione: `1 | f(2)`
        
2. **Chiamata f(2) `10`:**
    
    - `x` è 0? No.
        
    - `(x & 1)`: L'ultimo bit è 1? **NO** (è 0).
        
    - `f(x >> 1)`: Chiama `f(1)` (`10` diventa `1`).
        
    - Operazione: `0 | f(1)`
        
3. **Chiamata f(1) `1`:**
    
    - `x` è 0? No.
        
    - `(x & 1)`: L'ultimo bit è 1? **SÌ**.
        
    - `f(x >> 1)`: Chiama `f(0)`.
        
    - Operazione: `1 | f(0)`
        
4. **Chiamata f(0):**
    
    - `x` è 0? **SÌ**. Ritorna 0.
        

**Risalita (Il Ritorno):**

Ora metti insieme i pezzi dal basso verso l'alto usando l'operatore **OR (`|`)**:

- `f(1)` era `1 | 0` = **1**
    
- `f(2)` era `0 | 1` = **1**
    
- `f(5)` era `1 | 1` = **1**
    

**CONCLUSIONE LOGICA:**

Questa specifica funzione (`&` combinato con `|`) restituisce **1 se il numero è diverso da zero, 0 se è zero.**

_Se invece ci fosse stato un `+` al posto di `|`, avrebbe contato quanti bit a 1 ci sono (Population Count)._

---

### TIPOLOGIA 2: Puntatori, Stringhe e Aritmetica

Ti danno due array di stringhe e un ciclo strano con un operatore ternario `? :`.

#### Il Codice "Nemico"

C

```
// Questa funzione conta la lunghezza della stringa (è una strlen fatta a mano)
int f(const char *p) {
    int n = 0;
    while (p[n] != '\0') n++;
    return n;
}

// Nel main...
c[i] = (f(a[i]) > f(b[i])) ? (b[i] + 1) : (a[i] + 1);
```

#### I 3 Concetti Chiave da sapere

1. **L'Operatore Ternario (`? :`)**
    
    `Condizione ? VERO : FALSO`
    
    È un `if` scritto su una riga.
    
    - Esempio: `(5 > 3) ? 10 : 20` -> Fa 10.
        
    - Esempio: `(1 > 3) ? 10 : 20` -> Fa 20.
        
2. **Aritmetica dei Puntatori sulle Stringhe (TRAPPOLA CLASSICA!)**
    
    Se `a[i]` è la stringa `"mela"`.
    
    Cosa significa **`a[i] + 1`**?
    
    Non somma 1 alle lettere. Significa: **"Parti dal carattere successivo"**.
    
    - `"mela" + 0` = "mela"
        
    - `"mela" + 1` = "ela"
        
    - `"mela" + 2` = "la"
        
3. **La Logica del Quiz:**
    
    Il codice dice: _"Confronta la lunghezza delle due parole. Prendi quella che vince (o perde) e stampala togliendo la prima lettera."_
    

---

### 🛠️ ESERCITAZIONE PRATICA (Risolviamo l'Esame A)

Il testo chiede esplicitamente: **"riportare il valore delle variabili... in forma tabellare"**. Se scrivi solo il risultato finale perdi punti!

Esercizio 1 (Esame A)

Array `a = {5, 8, 3, 6}`.

**Analisi Tabellare (Quello che devi scrivere sul foglio):**

|**Iterazione i**|**Valore a[i]**|**Calcolo f(a[i])**|**Risultato b[i]**|**Stampa b[i]+i**|
|---|---|---|---|---|
|**0**|5|`101` != 0 -> ritorna 1|1|1 + 0 = **1**|
|**1**|8|`1000` != 0 -> ritorna 1|1|1 + 1 = **2**|
|**2**|3|`011` != 0 -> ritorna 1|1|1 + 2 = **3**|
|**3**|6|`110` != 0 -> ritorna 1|1|1 + 3 = **4**|

**Output finale:** `1 2 3 4`

---

Esercizio 2 (Esame A)

- `a`: "uno" (len 3), "otto" (len 4), "due" (len 3), "sei" (len 3), "tre" (len 3)
    
- `b`: "aaa" (len 3), "zz" (len 2), "bbbb" (len 4), "no" (len 2), "dddd" (len 4)
    
- **Logica:** `(len(a) > len(b)) ? (b + 1) : (a + 1)`
    
    (Se A è più lunga, stampa B tagliato. Altrimenti stampa A tagliato).
    

**Analisi Tabellare:**

| **i** | **Parola A (len)** | **Parola B (len)** | **Condizione A > B?** | **Chi vince?** | **Azione (+1)** | **c[i] finale** |
| ----- | ------------------ | ------------------ | --------------------- | -------------- | --------------- | --------------- |
| 0     | "uno" (3)          | "aaa" (3)          | 3 > 3? **Falso**      | Vince A        | "uno"+1         | **"no"**        |
| 1     | "otto" (4)         | "zz" (2)           | 4 > 2? **Vero**       | Vince B        | "zz"+1          | **"z"**         |
| 2     | "due" (3)          | "bbbb" (4)         | 3 > 4? **Falso**      | Vince A        | "due"+1         | **"ue"**        |
| 3     | "sei" (3)          | "no" (2)           | 3 > 2? **Vero**       | Vince B        | "no"+1          | **"o"**         |
| 4     | "tre" (3)          | "dddd" (4)         | 3 > 4? **Falso**      | Vince A        | "tre"+1         | **"re"**        |

**Output finale:** `no z ue o re`

---

### 🔥 COSA PUÒ CAMBIARE? (Varianti Possibili)

1. **Bitwise:**
    
    - Se invece di `|` c'è `+`: Conta i bit a 1.
        
        - `f(5)` (`101`) -> `1 + 0 + 1` = **2**.
            
    - Se invece di `|` c'è `^` (XOR): Fa la parità dei bit.
        
2. **Stringhe:**
    
    - Se c'è `p[i] - 1`: Cambia la lettera (codice ASCII).
        
    - Se il ciclo di stampa è `i--`: Stampa al contrario (dall'ultimo al primo).
        

**Vuoi provare a risolvere tu i quiz dell'Esame B (File 20260108Esame_FI_B.docx) usando questa tabella?** Dimmi cosa scriveresti per il primo quiz di quel file .


---
# Cheat SHEET
### 1. I "Bitwise" (Operatori sui Bit)

**Dove si usano:** Nel **Quiz 1** (quello con la funzione ricorsiva `f(x)`).

**Regola d'oro:** Lavorano sui numeri binari (`0` e `1`), colonna per colonna.

|**Simbolo**|**Nome**|**Cosa fa (In parole povere)**|**Esempio Pratico**|**Trucco per l'Esame**|
|---|---|---|---|---|
|**`&`**|**AND**|Vince solo se **TUTTI E DUE** sono 1.|`1 & 1` = **1**<br><br>  <br><br>`1 & 0` = **0**|È come una serratura doppia: servono entrambe le chiavi. Spesso usata `x & 1` per vedere se un numero è **dispari**.|
|**`|`**|**OR**|Vince se **ALMENO UNO** è 1.|`1 \| 0` = **1**<br><br>  <br><br>`0 \| 0` = **0**|
|**`^`**|**XOR**|Vince se sono **DIVERSI**.|`1 ^ 0` = **1**<br><br>  <br><br>`1 ^ 1` = **0**|**ATTENZIONE:** Non è la potenza! È l'esclusivo. Se sono uguali fa zero.|
|**`<<`**|**Left Shift**|Sposta i bit a sinistra.|`3 << 1`|**MOLTIPLICA per 2**. (`x << 1` raddoppia, `x << 2` x4).|
|**`>>`**|**Right Shift**|Sposta i bit a destra.|`8 >> 1`|**DIVIDE per 2**. (`x >> 1` dimezza, buttando via i resti).|
|**`~`**|**NOT**|Inverte tutto.|`~0` = `1`|Trasforma gli 0 in 1 e viceversa. Raro nei quiz, ma sappilo.|

---

### 2. Logica e Condizioni (Scelte)

**Dove si usano:** Nel **Quiz 2** (stringhe) e nei cicli `while` / `if`.

| **Simbolo** | **Nome**       | **Cosa fa**                               | **Esempio Pratico**   | **Trucco per l'Esame**                                                      |
| ----------- | -------------- | ----------------------------------------- | --------------------- | --------------------------------------------------------------------------- |
| **`? :`**   | **Ternario**   | È un `if...else` su una riga sola.        | `(A > B) ? X : Y`     | Leggilo così: "La condizione A>B è vera? Se SÌ usa **X**, se NO usa **Y**". |
| **`&&`**    | **AND Logico** | Vero se entrambe le condizioni sono vere. | `(x > 0) && (x < 10)` | Diversa da `&`! Questa guarda il concetto di "Vero/Falso", non i bit.       |
| **`         |                | `**                                       | **OR Logico**         | Vero se almeno una condizione è vera.                                       |
| **`!`**     | **NOT Logico** | Inverte il risultato (Vero -> Falso).     | `if (!vittoria)`      | Leggilo come "Se NON c'è vittoria".                                         |

---

### 3. Puntatori e Stringhe (Il "Quiz delle Parole")

**Dove si usano:** Nel **Quiz 2** (confronto stringhe e aritmetica puntatori).

|**Simbolo**|**Nome**|**Cosa fa**|**Esempio Pratico**|**Trucco per l'Esame (PERICOLOSO) ⚠️**|
|---|---|---|---|---|
|**`*p`**|**Dereferenza**|"Guarda COSA C'È dentro quella casella".|`char x = *p;`|Se `p` punta a una stringa, `*p` è **la prima lettera**.|
|**`&x`**|**Indirizzo**|"Dimmi DOVE SI TROVA quella variabile".|`int *p = &x;`|Ti dà il numero di casa, non chi ci abita.|
|**`p + 1`**|**Aritmetica**|Vai alla casella successiva.|`"ciao" + 1`|**NON somma 1 al valore!** Sposta il puntatore. Risultato: `"iao"`.|
|**`p[i]`**|**Indice**|Prendi l'elemento alla posizione i.|`p[0]`|È uguale a scrivere `*p`.|

---

### 🔥 Esempi "Trappola" da Ricordare

Ecco come il professore cercherà di fregarti nei quiz (basato sui file che hai caricato):

**1. La Trappola dello Shift**

- Vedi: `f(x >> 1)`
    
- Cosa pensi: "Oddio che calcolo complesso".
    
- Realtà: Sta solo chiamando la funzione col numero **dimezzato** (es. da 5 passa a 2, da 2 passa a 1).
    

**2. La Trappola della Stringa + 1**

- Vedi: `printf("%s", c[i] + 1);` (se c[i] è "mela")
    
- Cosa pensi: "Magari cambia la 'm' in 'n' (lettera successiva)?"
    
- Realtà: **Taglia la testa!** Stampa dalla seconda lettera in poi: `"ela"`.
    

**3. La Trappola della Priorità**

- Vedi: `*p++`
    
- Realtà: Prima usa il valore puntato, POI incrementa il puntatore per il prossimo giro.
    

# Priorità

### 1. LIVELLO DIVINO (Vincono su tutto)

Sono gli operatori che "incollano" le cose strettamente.

- **`()`** : Parentesi (Ovviamente).
    
- **`[]`** : Indici array (`a[i]`).
    
- **`->`** e **`.`** : Accesso alle struct.
    
- **`x++`** / **`x--`** : Post-incremento (ha priorità altissima!).
    

---

### 2. LIVELLO UNARIO (Legati al singolo numero)

Agiscono da destra a sinistra sul numero attaccato.

- **`++x`** / **`--x`** : Pre-incremento.
    
- **`!`** : NOT Logico (Es. `!vero`).
    
- **`~`** : NOT Bitwise (Inversione bit).
    
- **`*p`** : Dereferenziazione puntatore (Guarda il valore).
    
- **`&x`** : Indirizzo (Guarda dove sta).
    
- **`(int)`** : Casting.
    

---

### 3. LIVELLO MATEMATICO (Prima i calcoli!)

Qui c'è la trappola più grande dell'esame.

1. **`*`** , **`/`** , **`%`** (Moltiplicazione, Divisione, Resto).
    
2. **`+`** , **`-`** (Somma, Sottrazione).
    

---

### ⚠️ 4. LA TRAPPOLA DELLO SHIFT ⚠️

- **`<<`** , **`>>`**
    

**REGOLA D'ORO:** L'aritmetica (`+`, `-`) VINCE sullo Shift!

Se scrivi: `1 << 2 + 1`

Il computer fa prima `2 + 1` (fa 3).

Poi fa `1 << 3`.

**Risultato:** 8.

---

### 5. LIVELLO CONFRONTO (Relazioni)

1. **`<`** , **`<=`** , **`>`** , **`>=`** (Maggiore/Minore).
    
2. **`==`** , **`!=`** (Uguale/Diverso).
    

**Altra Trappola:** `x & 1 == 0`

L'uguale (`==`) vince sull'AND (`&`)!

Il computer fa prima `1 == 0` (Falso/0).

Poi fa `x & 0`. Risultato sempre 0.

_Ecco perché nei quiz si mettono le parentesi:_ `(x & 1) == 0`.

---

### 6. LIVELLO BITWISE (Uno alla volta)

L'ordine è alfabetico inverso (XOR sta in mezzo).

1. **`&`** (AND).
    
2. **`^`** (XOR).
    
3. **`|`** (OR).
    

Quindi `a & b | c` fa prima l'AND tra a e b, poi il risultato in OR con c.

---

### 7. LIVELLO LOGICO (Decisioni finali)

1. **`&&`** (AND Logico - "E").
    
2. **`||`** (OR Logico - "O").
    

---

### 8. LIVELLO ASSEGNAZIONE (In fondo alla catena)

Tutto ciò che finisce con **`=`**.

- `=`, `+=`, `-=`, ecc.
    
    Questi si fanno sempre per ultimi, quando tutto il resto a destra è stato calcolato.
    

---

### Riassunto "Salva-Esame" in 3 punti:

1. **`+` batte `<<`** (Somma prima, Shifta dopo).
    
2. **`==` batte `&`** (Confronta prima, fai AND dopo -> Usa le parentesi!).
    
3. **`&` batte `|`** (Come la moltiplicazione batte l'addizione).