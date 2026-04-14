Questa è una domanda eccellente. Confondere lo spostamento tra _caratteri_ e lo spostamento tra _stringhe_ è il dubbio più diffuso e legittimo tra chi studia l'aritmetica dei puntatori in C.

Per chiarire questo concetto in modo accademico, dobbiamo partire dalla **Regola Aurea dell'Aritmetica dei Puntatori**:

> _Quando incrementi un puntatore (`p + 1`), il computer non si sposta in avanti di 1 byte, ma si sposta in avanti di un numero di byte pari alla **dimensione del tipo di dato a cui punta**._

Vediamo la differenza tra i due scenari applicati al tuo esercizio.

---

### Scenario 1: Muoversi sulle LETTERE di una parola (`char *`)

Immagina di avere un singolo puntatore a carattere:

C

```
char *str = "annA";
```

In memoria, la stringa `"annA"` è un blocco contiguo di caratteri terminato da `\0`.

Il puntatore `str` è di tipo `char *`. Questo significa che **punta a un singolo carattere** (che in C occupa esattamente **1 byte**).

Se tu scrivi `str + 1`, il compilatore ragiona così:

1. `str` punta a un `char`.
    
2. Un `char` pesa 1 byte.
    
3. Mi sposto in avanti di $1 \times 1 = 1$ byte.
    

**Risultato:** Ti sei spostato dalla lettera `'a'` alla lettera `'n'`. Stai viaggiando _all'interno_ della stessa parola.

---

### Scenario 2: Muoversi sulle PAROLE (`char **`)

Nel tuo quiz, la situazione iniziale era profondamente diversa. Avevamo un array di stringhe:

C

```
char *s[] = {"annA", "lUca", "MARIo"};
char **p = s;
```

]

Cosa significa `char **p`? Significa che `p` è un "puntatore a un puntatore a char".

In altre parole, `p` **non punta a una lettera, ma punta a un'altra scatola che contiene un indirizzo di memoria**.

Le variabili contenute nell'array `s` non sono lettere, ma sono _i puntatori_ alle tre stringhe.

Un puntatore (su un sistema a 64-bit) pesa **8 byte**, a prescindere da cosa indichi.

Se tu scrivi `p + 1`, il compilatore ragiona così:

1. `p` punta a un `char *` (un puntatore).
    
2. Un `char *` pesa 8 byte.
    
3. Mi sposto in avanti di $1 \times 8 = 8$ byte.
    

**Risultato:** Non ti sei spostato alla lettera 'n' di "annA", ma hai saltato l'intero primo puntatore e sei "atterrato" sul secondo puntatore dell'array, ovvero quello che punta alla parola `"lUca"`. Stai viaggiando _tra le parole_.

---

### La Sintesi: Come viaggiare in entrambe le direzioni

Per muoverti sia tra le parole che tra le lettere usando il doppio puntatore `p`, devi usare l'operatore di dereferenziazione (`*`) per "scendere di livello".

1. **`p`** : Punta al puntatore della prima parola.
    
2. **`p + 1`** : Salta al puntatore della seconda parola (`"lUca"`). _(Viaggio tra parole)_
    
3. **`*(p + 1)`** : Prende l'effettivo puntatore alla parola `"lUca"`. Ora sei a livello di singola parola (sei sceso a un `char *`).
    
4. **`*(p + 1) + 2`** : Prende la parola `"lUca"` e si sposta in avanti di 2 byte (2 caratteri). Atterra sulla lettera `'c'`. _(Viaggio tra lettere)_
    
5. **`*(*(p + 1) + 2)`** : Estrae fisicamente il carattere `'c'`.
    

**Perché nel tuo esercizio `f(p + i)` passava alle parole successive?**

Perché la funzione `f` richiedeva come argomento un `char **` (un doppio puntatore). Chiamando `p + i` (senza asterischi davanti), stavi sommando `i` a un doppio puntatore, chiedendo quindi al compilatore di fare "salti giganti" da una parola all'altra dell'array `s`, e non passetti da un byte tra le lettere di `"annA"`.

È più chiaro ora come la sintassi (quanti asterischi ha il puntatore) detti letteralmente la "lunghezza del passo" che il C compie in memoria?