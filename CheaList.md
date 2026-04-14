Ottima idea! Avere un "cheat sheet" (un foglio di riepilogo) sottomano è il modo migliore per memorizzare i comandi quando si impara un nuovo linguaggio.

Ecco una raccolta pratica e diretta delle sintassi più utilizzate in C#, strutturata proprio per aiutarti con i tuoi primi programmi.

### 1. Variabili e Tipi di Dato Principali

Servono per memorizzare le informazioni. Devi sempre specificare _che tipo_ di dato stai salvando.

C#

```cs
int eta = 25;                  // Numeri interi (senza virgola)
double temperatura = 36.5;     // Numeri con la virgola (usa il punto, non la virgola!)
string nome = "Mario";         // Testo (sempre tra doppie virgolette)
char iniziale = 'M';           // Singolo carattere (sempre tra singole virgolette)
bool isOnline = true;          // Valore logico: vero (true) o falso (false)
```

### 2. Input e Output (Interagire con l'utente)

I comandi fondamentali per parlare con chi usa il programma nel terminale.

C#

```cs
// Stampare testo e andare a capo
Console.WriteLine("Ciao Mondo!"); 

// Stampare testo senza andare a capo
Console.Write("Inserisci il tuo nome: "); 

// Leggere quello che l'utente scrive (restituisce sempre una stringa)
string inputUtente = Console.ReadLine(); 

// Convertire una stringa di testo in un numero
int numero = Convert.ToInt32("10");     // Per i numeri interi
double numeroDec = Convert.ToDouble("10.5"); // Per i numeri con la virgola
```

### 3. Condizioni (Prendere decisioni)

Permettono al programma di fare cose diverse in base alla situazione.

**L'istruzione If / Else:**

C#

```cs
int punti = 85;

if (punti >= 90) 
{
    Console.WriteLine("Ottimo lavoro!");
} 
else if (punti >= 60) 
{
    Console.WriteLine("Test superato.");
} 
else 
{
    Console.WriteLine("Devi ritentare.");
}
```

**L'istruzione Switch:** (Ideale quando hai tante opzioni esatte, come nella tua calcolatrice)

C#

```cs
string comando = "start";

switch (comando) 
{
    case "start":
        Console.WriteLine("Avvio in corso...");
        break; // Il break è obbligatorio per fermare lo switch
    case "stop":
        Console.WriteLine("Arresto...");
        break;
    default: // Se non corrisponde a nessun caso precedente
        Console.WriteLine("Comando sconosciuto.");
        break;
}
```

### 4. Cicli (Ripetere le azioni)

Servono per non dover riscrivere mille volte lo stesso codice.

**Ciclo For** (Quando sai esattamente quante volte vuoi ripetere un'azione):

C#

```cs
// Parte da 0; si ripete finché i è minore di 5; a ogni giro aggiunge 1 (i++)
for (int i = 0; i < 5; i++) 
{
    Console.WriteLine($"Giro numero: {i}");
}
```

**Ciclo While** (Quando vuoi ripetere un'azione _finché_ una condizione è vera):

C#

```cs
int contatore = 0;
while (contatore < 3) 
{
    Console.WriteLine("Sto caricando...");
    contatore++;
}
```

### 5. Array e Liste (Collezioni di dati)

Per salvare tanti dati simili dentro un'unica variabile.

**Array** (Hanno una dimensione fissa che non puoi cambiare):

C#

```cs
string[] colori = { "Rosso", "Verde", "Blu" };
Console.WriteLine(colori[0]); // Stampa "Rosso" (si conta sempre partendo da 0!)
```

**Liste** (Molto più flessibili, puoi aggiungere o togliere elementi quando vuoi):

C#

```cs
List<string> spesa = new List<string>();
spesa.Add("Pane");
spesa.Add("Latte");
spesa.Remove("Pane"); // Rimuove un elemento
```

### 6. Metodi (Le Funzioni)

Piccoli blocchi di codice che fanno un'azione specifica e che puoi "chiamare" quando ti servono, per tenere il codice pulito.

C#

```cs
// Un metodo che esegue un'azione e non restituisce nulla (void)
static void Saluta(string nome) 
{
    Console.WriteLine($"Ciao, {nome}!");
}

// Un metodo che fa un calcolo e restituisce un numero (int)
static int Somma(int a, int b) 
{
    return a + b;
}

// Come usarli nel tuo codice principale:
Saluta("Luigi");
int risultato = Somma(5, 3);
```

---
