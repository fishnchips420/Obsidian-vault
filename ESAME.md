---buchi probabili---

- [ ] tipi di dato , es 32 bit , unsigned ecc.
- [ ] separazione dallo spazio , scrittura dello spazio nelle stringhe 
- [ ] implementare funzioni 
- [ ] `int g(int *q)` perche è all interno della parentesi un puntatore 
- [ ] il binario
	- [ ] &
	- [ ] | 
	- [ ] <<
	- [ ] >>
	- [ ] cosa stampano i vari %u , &d ... 


quiz 1: 
```c
int g(int *q) { //1 cosa vuol dire int *q di fianco a g ?  

int i, s = 0;

  

for (i = 0; i < 6; i++) {

int x = *(q + i); //2 cosa vuol dire *(q+i) con lasterisco , è un puntatore della somma ? 

  

if ((x & 1) == 0) { /* somma solo i numeri pari */ //3 quindi solo numeri pari vengono sommati a s

s = s + x;

}

}

  

return s; // 4 il fatto che ritorna s cosa succede , non ho mai capito dove va a finire il numero che viene ritornato , di solito si usa 0 , quindi presumo che se s è  negativo funge come -1 e il programma si interrompe??

}

  

int main() {

int m[2][3] = {

{4, 7, 2},

{9, 6, 8}

};

  

int k = g(&m[0][0]); //5 cosa vuol dire g(&m[0][0]) 

  

printf("%d %d\n", k, k >> 2); //6 ho bisogno infine che mi dici quali sono tutti gli operatori di questa categoria , << , >> , | , & , eccc, penso che siano or xor ecc.   

return 0;

}
```

# risposta quiz 1 

---
### **1. `int *q` di fianco a g?**

Vuol dire che la funzione `g` **aspetta in ingresso un indirizzo di memoria** (un puntatore) che punta a un numero intero.

- Non vuole il numero in sé (es. `4`), ma vuole sapere **dove** si trova il numero nella RAM.
    
- `q` diventa quindi la nostra "mappa" per accedere ai dati.
    

### **2. `*(q + i)`: è un puntatore della somma?**

No, questa è la cosiddetta **aritmetica dei puntatori**.

- `q` è l'indirizzo di partenza (il primo elemento dell'array).
    
- `i` è il "passo" (0, 1, 2, 3, 4, 5).
    
- `(q + i)` calcola l'indirizzo dell'elemento i-esimo (si sposta avanti di `i` caselle).
    
- L'asterisco esterno `*` (operatore di deferenziazione) dice: **"Vai a quell'indirizzo calcolato e prendi il VALORE che c'è dentro"**.
    
    - Se `i=0`, prende il primo numero.
        
    - Se `i=1`, prende il secondo numero, e così via.
        

### **3. `if ((x & 1) == 0)`: somma solo i numeri pari?**

**Esatto.**

- L'operatore `&` (AND bit a bit) confronta i bit del numero `x` con il numero `1` (che in binario è `...0001`).
    
- Se l'ultimo bit di un numero è `0`, il numero è **PARI**.
    
- Se l'ultimo bit è `1`, il numero è **DISPARI**.
    
- Quindi `(x & 1)` restituisce 0 se è pari. La condizione == 0 è vera, quindi somma solo i pari.
    

### **4. `return s`: dove va a finire il numero?**

Qui c'è un malinteso comune. Il `return` **non** serve a dire "errore" o "successo" (quello succede solo nel `main` con `return 0` o `exit`).

- `return s` significa: "Prendi il risultato del calcolo (`s`) e **spediscilo indietro** a chi ha chiamato la funzione".
    
- Dove finisce? Guarda nel `main`: c'è scritto `int k = g(...)`.
    
- Il valore di `s` viene **copiato dentro la variabile `k`**.
    
- Il programma non si interrompe; la funzione `g` finisce e l'esecuzione riprende nel `main` con `k` che ora vale quanto valeva `s`.
    

### **5. `g(&m[0][0])`**

Questo è il trucco per trattare una matrice (array 2D) come se fosse una lista unica.

- `m` è una matrice 2x3 (2 righe, 3 colonne).
    
- In memoria, però, il computer salva i numeri tutti di fila: `4, 7, 2, 9, 6, 8`.
    
- `&m[0][0]` prende l'**indirizzo del primissimo numero** (il 4).
    
- Passando questo indirizzo alla funzione `g` (che si aspetta un puntatore generico `*q`), la funzione può scorrere tutti e 6 i numeri come se fossero in fila indiana, ignorando che sono divisi su due righe.
    

### **6. Gli operatori bitwise (Bit a Bit)**

Ecco la lista completa che ti serve per l'esame. Questi operatori lavorano sui singoli bit (0 e 1) dei numeri.

| **Simbolo** | **Nome**        | **Funzionamento**                                                                          | **Esempio (con 5=0101 e 3=0011)** |
| ----------- | --------------- | ------------------------------------------------------------------------------------------ | --------------------------------- |
| **`&`**     | **AND**         | **1** solo se entrambi sono 1.                                                             | `5 & 3` → `0001` (1)              |
| **`         | `**             | **OR**                                                                                     | **1** se almeno uno dei due è 1.  |
| **`^`**     | **XOR**         | **1** se sono diversi (uno 0 e l'altro 1).                                                 | `5 ^ 3` → `0110` (6)              |
| **`~`**     | **NOT**         | Inverte i bit (0 diventa 1 e viceversa).                                                   | `~5` → `...1010`                  |
| **`<<`**    | **Left Shift**  | Sposta i bit a sinistra (equivale a **moltiplicare per 2** per ogni passo).                | `5 << 1` → `1010` (10)            |
| **`>>`**    | **Right Shift** | Sposta i bit a destra (equivale a **dividere per 2** per ogni passo, perdendo i decimali). | `20 >> 2` → 20 diviso 4 → 5       |

---

### **Soluzione del Quiz**

Per completezza, vediamo cosa stampa il programma:

1. **Array:** `{4, 7, 2, 9, 6, 8}`
    
2. **Ciclo:** Scorre 6 volte.
    
3. **Controllo Pari:**
    
    - 4 (Pari) -> `s = 4`
        
    - 7 (Dispari) -> ignora
        
    - 2 (Pari) -> `s = 4 + 2 = 6`
        
    - 9 (Dispari) -> ignora
        
    - 6 (Pari) -> `s = 6 + 6 = 12`
        
    - 8 (Pari) -> `s = 12 + 8 = 20`
        
4. **Return:** Restituisce 20. Quindi `k = 20`.
    
5. **Stampa:**
    
    - `k`: stampa **20**
        
    - `k >> 2`: sposta i bit di 2 a destra (che significa dividere 20 per $2^2$, cioè 4). $20 / 4 = 5$. Stampa **5**.
        

**Output finale:** `20 5`1.