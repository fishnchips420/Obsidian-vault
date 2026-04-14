Certamente! Alziamo un po' l'asticella.

Fino ad ora abbiamo fatto programmi "usa e getta": leggono, calcolano e finiscono.

Adesso facciamo un programma interattivo che deve ricordarsi le cose anche se lo chiudi e lo riapri.

### 🎯 Missione: "La Rubrica Telefonica"

Devi creare un programma che permetta all'utente di scegliere se **aggiungere** un nuovo amico alla rubrica o **leggere** tutti i contatti salvati.

**Specifiche tecniche:**

1. **La Struct:** Definisci una `struct Contatto` con:
    
    - `char nome[30]`
        
    - `char cognome[30]`
        
    - `char telefono[15]` (Usa una stringa per il numero, così puoi mettere simboli come `+` e non perdi gli zeri iniziali!).
        
2. **Il Menu:** Il programma deve mostrare un menu all'utente:
    
    Plaintext
    
    ```
    1. Aggiungi nuovo contatto
    2. Leggi tutta la rubrica
    3. Esci
    ```
    
3. **La Logica dei File (Punto Critico):**
    
    - Se l'utente sceglie **1**, devi aprire il file in modo da **NON cancellare** quelli vecchi. Nel PDF c'è una modalità apposta per "aggiungere in coda" 1.
        
    - Se l'utente sceglie **2**, devi leggere il file dall'inizio alla fine.
        

---

### 💡 Suggerimenti Strategici

1. **Modalità di apertura:**
    
    - Per leggere usi `"r"`.
        
    - Per scrivere cancellando tutto usi `"w"`.
        
    - Per scrivere **aggiungendo** alla fine (append) si usa **`"a"`**2. Questo è il segreto di questo esercizio!
        
2. Il Ciclo del Menu:
    
    Usa un ciclo do...while che continua a mostrare il menu finché l'utente non digita 0.
    
3. **Gestione File:**
    
    - Apri e chiudi il file **dentro** ogni singola scelta (`if` o `switch`). Non tenerlo aperto per tutto il programma, perché la modalità (lettura vs scrittura) cambia in base a cosa vuole fare l'utente.
        

**Provaci!** Questo esercizio simula un vero software gestionale. Se riesci a farlo, hai capito come gestire la persistenza dei dati.1