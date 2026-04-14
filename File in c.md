### 1. Sintesi Teorica: Cos'è un File in C

- **Definizione:** Un file è un'astrazione del sistema operativo per memorizzare informazioni in modo permanente sulla memoria di massa1. In C, un file è visto come una sequenza di byte o record, accessibile tramite un puntatore a una struttura `FILE` (definita in `stdio.h`)2222.
    
- **Tipologie di File:**
    
    1. **File Binari:** Una sequenza pura di byte. Non c'è interpretazione dei dati (un intero viene salvato come i suoi bit interni). La fine del file è determinata dall'esito delle operazioni di lettura, non esiste un carattere speciale di fine333333333.
        
    2. **File di Testo:** Sequenza di caratteri organizzata in righe (terminate da `\n`). I dati numerici vengono convertiti in caratteri ASCII (es. l'intero 123 diventa i caratteri '1', '2', '3'). Terminano con un carattere speciale `EOF`444444444.
        
- **Canali Standard:** `stdin` (tastiera), `stdout` (video), `stderr` (errori a video) sono file di testo già aperti automaticamente dal programma 5.
    

---

### 2. Guida Pratica ai Comandi (Sintassi ed Esempi)

Qui trovi i comandi divisi per operazione. Ricorda sempre di includere `<stdio.h>` e `<stdlib.h>`.

#### A. Apertura e Chiusura (`fopen`, `fclose`)

Per lavorare su un file devi associare il nome fisico (es. "dati.txt") a un puntatore `FILE*` nel tuo programma.

- **Sintassi:** `FILE* fopen(char *nome_file, char *modalità);` 6
    
- **Modalità comuni:**
    
    - `"r"`: Lettura (file deve esistere).
        
    - `"w"`: Scrittura (crea file o sovrascrive se esiste).
        
    - `"a"`: Append (scrive in coda senza cancellare).
        
    - `"rb"`, `"wb"`: Lettura/Scrittura per **file binari** 7.
        
    - `"r+"`: Lettura e scrittura (modifica file esistente)8.

	- `"rewind(fp)"` : Riporta la bobina del file indietro
		

**Esempio di utilizzo:**

C

```C
FILE *fp;
// Apro in lettura un file binario. Controllo SEMPRE se fp è NULL (errore)
if ((fp = fopen("dati.dat", "rb")) == NULL) {
    perror("Errore apertura file"); // Stampa l'errore su stderr
    exit(1); // Termina il programma
}
// ... operazioni ...
fclose(fp); // Chiude il file e svuota i buffer [cite: 92, 96]
```

#### B. Input/Output su File Binari (`fread`, `fwrite`)

Queste funzioni leggono/scrivono blocchi di byte senza convertirli.

- **Scrittura (`fwrite`):** `int fwrite(void *indirizzo_memoria, int dim_elemento, int num_elementi, FILE *fp);` 9
    
- **Lettura (`fread`):** `int fread(void *indirizzo_memoria, int dim_elemento, int num_elementi, FILE *fp);` 10
    
    - _Nota:_ Restituiscono il numero di elementi letti/scritti (non i byte!). Se `fread` restituisce un numero minore di quello richiesto (o 0), il file è finito o c'è un errore11.
        

**Esempio (Salvare e rileggere un array):**

C

```C
int numeri[10] = {1, 2, 3, 4, 5};
// Scrittura
fwrite(numeri, sizeof(int), 5, fp); // Scrive 5 interi dal vettore al file

// Lettura
int buffer[10];
int n_letti = fread(buffer, sizeof(int), 10, fp); // Tenta di leggerne 10
// n_letti conterrà 5 se il file aveva solo 5 elementi
```

#### C. Input/Output su File di Testo

Simili alle funzioni da tastiera/video, ma con la `f` davanti e il puntatore al file come argomento.

**1. Carattere singolo (`fgetc`, `fputc`)**

- **Lettura:** `int c = fgetc(fp);` Legge un carattere. Restituisce `EOF` se il file è finito12.
    
- **Scrittura:** `fputc('A', fp);` Scrive il carattere 'A'13.
    

**Esempio (copiare un file carattere per carattere):**

C

```C
int c; // Nota: int, non char, per gestire EOF
while ((c = fgetc(fp_in)) != EOF) {
    fputc(c, fp_out);
}
```

**2. Stringhe (`fgets`, `fputs`)**

- **Lettura:** `fgets(char *str, int n, FILE *fp);` Legge al massimo `n-1` caratteri. Si ferma a fine riga (`\n`). **Importante:** Mantiene il `\n` nella stringa letta e aggiunge `\0` 14.
    
- **Scrittura:** `fputs(char *str, FILE *fp);` Scrive la stringa. Non aggiunge automaticamente il `\n` finale15.
    

3. Formattato (fscanf, fprintf)

Funzionano come scanf e printf.

- **Lettura:** `fscanf(fp, "%d %s", &intero, stringa);`16.
    
    - _Attenzione:_ `fscanf` con `%s` si ferma al primo spazio. Non va bene per leggere stringhe con spazi (es. "Mario Rossi")17.
        
    - _Trucco per dimensione fissa:_ `fscanf(fp, "%10c", buffer)` legge esattamente 10 caratteri (spazi inclusi), ma non mette il `\0` finale (devi metterlo tu)18181818.
        

**Esempio (Leggere dati strutturati):**

C

```C
#include <stdio.h>
#include <stdlib.h>

typedef struct {
    char cognome[30];
    char nome[30];
    int anno;
} Persona; // [cite: 416-424]

int main() {
    FILE *fp;
    Persona p; // Variabile di appoggio

    if ((fp = fopen("dati.txt", "r")) == NULL) {
        perror("Errore");
        exit(1);
    }

    printf("--- ELENCO LETTO ---\n");

    // fscanf restituisce EOF quando il file finisce [cite: 493]
    // Nota: NON servono spazi nella stringa di formato "%s%s%d"
    while(fscanf(fp, "%s %s %d", p.cognome, p.nome, &p.anno) != EOF) {
        printf("Letto: %s %s, nato nel %d\n", p.cognome, p.nome, p.anno);
    }

    fclose(fp);
    return 0;
}
```


#### D. Spostarsi nel File (`fseek`, `ftell`)

Utile per l'accesso casuale (non sequenziale), ad esempio per modificare un record a metà file.

- **`ftell(fp)`:** Restituisce la posizione attuale (long) della "testina" in byte dall'inizio19.
    
- **`fseek(fp, offset, origine)`:** Sposta la testina20.
    
    - `SEEK_SET`: Inizio file.
        
    - `SEEK_CUR`: Posizione corrente.
        
    - `SEEK_END`: Fine file 21.
        

**Esempio (Tornare indietro di un carattere per sovrascriverlo):**

C

```C
// Se ho letto una minuscola e voglio renderla maiuscola sul posto
long pos = ftell(fp);
fseek(fp, pos - 1, SEEK_SET); // Torno indietro di 1 byte
fputc(toupper(ch), fp);       // Sovrascrivo
fseek(fp, 0, SEEK_CUR);       // OBBLIGATORIO fare una fseek tra lettura e scrittura! [cite: 378]
```

### 3. Note Importanti per l'Esame

1. **Controllo Apertura:** Mai dare per scontato che `fopen` funzioni. Controlla sempre se restituisce `NULL`22.
    
2. **`sizeof` nei Binari:** Usa sempre `sizeof(int)` o `sizeof(struct persona)` invece di numeri fissi (es. 4), per garantire la portabilità23.
    
3. **Gestione Spazi (`fscanf` vs `fgets`):** Se devi leggere una riga che contiene spazi (es. "Via Roma 1"), usa `fgets`. Se i dati sono separati rigidamente da spazi (es. "Rossi Mario 1980"), usa `fscanf`24242424.
    
4. **Alternanza R/W:** Se apri un file in modalità `r+` (lettura+scrittura), devi obbligatoriamente chiamare `fseek` (anche di 0 byte) quando passi da un'operazione di lettura a una di scrittura e viceversa25.
    

Vuoi che ti mostri come applicare questi concetti all'**Esempio 4** del PDF (lettura array di `struct persona`) passo dopo passo?