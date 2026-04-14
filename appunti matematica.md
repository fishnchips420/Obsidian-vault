Un **limite matematico** descrive il comportamento di una funzione, una sequenza o una serie quando una variabile si avvicina a un determinato valore, solitamente infinito o un punto specifico. 

Ecco una guida chiara per determinare l'inversa di una funzione e verificare se è iniettiva, suriettiva o biunivoca:

---

### **1. Come calcolare l'inversa di una funzione?**

Per trovare la funzione inversa f−1(x)f^{-1}(x), segui questi passaggi:

1. **Scrivi l'equazione della funzione originale:**
    
    y=f(x)y = f(x)
2. **Scambia le variabili xx e yy:**
    
    x=f(y)x = f(y)
    
    Questo riflette il fatto che l'inversa "inverte" il ruolo di input e output.
    
3. **Risolvi l'equazione per yy:** Trova yy in termini di xx. La soluzione sarà la funzione inversa f−1(x)f^{-1}(x).
    
4. **Verifica l'inversa**:
    
    - Assicurati che f(f−1(x))=xf(f^{-1}(x)) = x e f−1(f(x))=xf^{-1}(f(x)) = x.

---

#### **Esempio:**

Troviamo l'inversa di f(x)=2x−1+1f(x) = \frac{2}{x-1} + 1.

1. Scrivi l'equazione:
    
    y=2x−1+1y = \frac{2}{x-1} + 1
2. Scambia xx e yy:
    
    x=2y−1+1x = \frac{2}{y-1} + 1
3. Risolvi per yy:
    
    x−1=2y−1⇒y−1=2x−1⇒y=2x−1+1x - 1 = \frac{2}{y-1} \quad \Rightarrow \quad y - 1 = \frac{2}{x-1} \quad \Rightarrow \quad y = \frac{2}{x-1} + 1

L'inversa è:

f−1(x)=2x−1+1f^{-1}(x) = \frac{2}{x-1} + 1

---

### **2. Come verificare se una funzione è iniettiva?**

Una funzione è **iniettiva** (o "uno-a-uno") se **a ogni valore di yy corrisponde al massimo un valore di xx**. In altre parole, due valori di input distinti non possono produrre lo stesso output.

#### **Test dell'iniettività:**

1. **Grafico:** La funzione è iniettiva se passa il _test della retta orizzontale_: ogni retta orizzontale interseca il grafico al massimo in un punto.
    
2. **Derivata:** Se la derivata di una funzione f′(x)f'(x) non cambia segno (sempre >0> 0 o <0< 0), la funzione è strettamente monotona e quindi iniettiva.
    
3. **Algebraicamente:** Supponi f(x1)=f(x2)f(x_1) = f(x_2) e verifica che ciò implichi x1=x2x_1 = x_2. Se ciò accade, la funzione è iniettiva.
    

#### **Esempio:**

Verifichiamo l'iniettività di f(x)=2x+3f(x) = 2x + 3:

f(x1)=f(x2)⇒2x1+3=2x2+3⇒x1=x2f(x_1) = f(x_2) \quad \Rightarrow \quad 2x_1 + 3 = 2x_2 + 3 \quad \Rightarrow \quad x_1 = x_2

La funzione è iniettiva.

---

### **3. Come verificare se una funzione è suriettiva?**

Una funzione è **suriettiva** (o "sopraiettiva") se **ogni valore di yy nell'insieme di arrivo ha almeno una corrispondenza nell'insieme di partenza**.

#### **Test della suriettività:**

1. **Definizione del codominio:** Il codominio è l'insieme dei valori che la funzione _può_ assumere.
2. **Verifica esplicita:** Risolvi y=f(x)y = f(x) per xx. Se puoi ottenere xx per ogni yy appartenente all'insieme di arrivo, allora la funzione è suriettiva.
3. **Grafico:** La funzione è suriettiva se il grafico copre tutto l'asse yy del codominio.

#### **Esempio:**

Verifichiamo se f(x)=x2f(x) = x^2 (con x∈Rx \in \mathbb{R}) è suriettiva su R\mathbb{R}:

- Risolvi y=x2y = x^2. Ottieni x=±yx = \pm\sqrt{y}, ma y\sqrt{y} esiste solo per y≥0y \geq 0.
- La funzione non è suriettiva su R\mathbb{R}, ma lo è su [0,∞)[0, \infty).

---

### **4. Quando una funzione è biunivoca (invertibile)?**

Una funzione è **biunivoca** se è **sia iniettiva che suriettiva**.

- Se è iniettiva, ogni valore yy ha al massimo un xx.
- Se è suriettiva, ogni valore yy ha almeno un xx.
- Se è biunivoca, ogni yy ha esattamente un xx, il che garantisce l'esistenza dell'inversa.

#### **Esempio:**

f(x)=2x+3f(x) = 2x + 3:

- È iniettiva perché la derivata è f′(x)=2>0f'(x) = 2 > 0 (strettamente crescente).
- È suriettiva perché, risolvendo y=2x+3y = 2x + 3, otteniamo x=y−32x = \frac{y-3}{2}, che esiste per ogni y∈Ry \in \mathbb{R}.
- Quindi, è biunivoca e ha un'inversa.

---

### **Riassunto dei test:**

| **Proprietà**     | **Criterio**                                                                                                                             |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Iniettività**   | 1. Derivata non cambia segno. 2. f(x1)=f(x2)f(x_1) = f(x_2) implica x1=x2x_1 = x_2. 3. Il grafico passa il test della retta orizzontale. |
| **Suriettività**  | 1. Risolvi y=f(x)y = f(x) per xx e verifica che esista per ogni yy nel codominio. 2. Il grafico copre tutto l'insieme di arrivo.         |
| **Invertibilità** | La funzione è invertibile se è sia iniettiva che suriettiva (biunivoca).                                                                 |
|                   |                                                                                                                                          |

17/12/24
[[funzioni razionali fratte.xopp]]sss
[[asintoti.jpg]] 


esercizi verifica 
-  