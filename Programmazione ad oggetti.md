# [[CheaList]]

# Lezione 2 
incapsulamento: un accesso semplificato tramite un interfaccia 
permette di modificare la codifica interna dell oggetto senza pero cambiare l'esperienza di chi usa il programma 

C# è un linguaggio di programmazione 
.Net è un framework o un ecosistema 

## Problemi con C risolti con C#
- memory leaks 
- illegal pointer references 
- overlu complex multiple inheritance
- static linking //eseguibile che contiene tutte le librerie

## Soluzioni 
- Garbage collection //evita gli orfani  
- threw out pointers
- Singola eredita con interfacce
- Linking dinamico 

## Storia 
>il c# è stato creato dalla microsoft da anders hejlsberg nel 2000 ed è stato riconosciuto come standard dall'ISO nel 2003. 
Piu tardi la Microsoft ha rilasciato C# insieme a .NET e Visual Studio 

## Componenti di sviluppo per realizzare un applicazione
1) Editor di testo 
	- Visual studio code (+ Estensione C#)
2) Compilatore 
	- Roslyn (compilatore ufficiale di C#)
3) Runtime e Framework 
	- .Net SDK ( contene librerie e runtime di base )
4) Gestione dei pacchetti
	- NuGet (per librerie esterne e dipendenze )
5) Debugger e strumenti di analisi 
	- Debugger integrato su vs studio 
	- .NET CLI (dot net per debugging e testing)
6) Controllo versione (Opzionale)
	- Git 

## CLR - COMMON LANGUAGE RUTIME 
il framweork dotnet implementa una "filosofia nel compilare" , non prendiamo piu il codice sorgente e lo compiliamo , ma si agguiunge un passaggio intermedio , l'ambiente .NET prevede 40 linguaggi diversi. 
Viene generato il byte code , univoco per tutti i codici , ( un linguaggio medio alto ) , 

| SOURCE CODE-> | BYTECODE-> | NATIVE CODE |
| ------------- | ---------- | ----------- |
| C#            |            |             |
| vr.net        | Cil code   | Native code |
|               |            |             |
//il __bytecode__ è un nuovo passaggio che questo compilatore introduce , ugugla eper tutti i codici , perche il passaggio che lo trasforma da codice di alto livello a codice macchina modifica il bytecode

# Lezione 3 2/3/26









