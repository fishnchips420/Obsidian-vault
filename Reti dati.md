### [[lezione 1 23.02.26 . Enti standardizzazione delle TLC]]

# Lezione 2 26/2/26

Compiti di unn sistema di comunicaizone 
- utilizzo dei sistemi di trasmissione
- interfacciamento
- ==generazione di segnali==
	- I segnali trasmettono o 1 o zero , tramite certe modalita in cui arriva l'elettricita 

- ==sincronizzazione==
	- se due dispositivi non sono sincronizzati non comunicheranno mai 
	- l'insieme delle regole che tra dispositivi agganciati che li permette di comunicare
	- modalita di scambio: la modalita per la quale un dispositivo puo acquisire le informazioni
-  ==modalita e rivelazione degli errori== : comprendere quali segnali sono danneggiati 
	- modalita di gestione degli errori : 
		- comunicazioni dati : file , streaming 
			- quando si trasemtte un file tramite il File Portocol Transfer , vengono trasferiti pacchetti ocnetenenti parti di questa applicaizone , conetenenti anche un codice di verifica con il quale si verifica che il pacchetto sia arrivato correttamente , se cosi non è , si richiedee il pacchetto finche non arriva giusto 
			- servizi in tempo reale : non si puo chiedere indietro i pacchetti che non sono arrivati , per esempio , durante lo streaming avviene una media dei frame giusti con quelli precedenti e quelli successiv , per provare a creare un immagine simile

- ==Controllo di flusso==
	- la negozizazione della velocitia di trasmissisone , ES: una chiamata su meet nella quale non tutti hanno la stessa banda 
	- ==congestione== : per esempio un router del wifi che ottiene troppi pacchetti in entrata , oltre che scartare i pacchetti danneggiati, scarta pure i surplus 
	- ==indirizzamento==
	- ==ripristino==
		- per esempio : un download si blocca , permette di ripartire da li 
	- ==formattazione dei messaggi==
		- i messaggi sonoo i Protocol Data Unit ( con formati particolare)
	- ==Sicurezza(cyber security)==
		- non intercettabilita dei messaggi , sicurezza che non vengano modificati dati in arrivo , ecc. 
	- ==Gestione della rete== 
		- banalizzare la gestione della rete : gestire l'erogazione e gli accessi della rete , per la ridistribuzione della banda di accesso in base al traffico in rete 

## Protocolli di rete 
### Concetti di protocolli, interfacce e primitive 
bill gates nella progettazone del personal computer ha suddiviso tutto in 7 problemi 

__protocolli__ : insieme di regole e formati che determina la comunicazione traduce livelli uguali

_esempio: posso mandare un email da gmail a outlook perche i protocolli sono scritti in modo di poter comuicare tra loro _

__primitive__: sono le entita che si scambiano tramite le interfacce 

| Livello       | Protocolli | Livello       |
| ------------- | ---------- | ------------- |
| Applicazione  | <------->  | Applicazione  |
| Presentazione | <------->  | Presentazione |
| Sessione      | <------->  | Sessione      |
| Network       | <------->  | Network       |
| DataLink      | <------->  | DataLink      |
| Trasporto     | <------->  | Trasporto     |
| Fisico        | <------->  | Fisico        |

__tramite il protocollo giusto si possono far comunicare anche livelli diversi__ 

Acune elaborazione vengono eseguite attraverso software , il telefono possiede l'antenna , e tutto il resto viene eseguito tramite software 

tutto sopra a il livello fisico viene eseguito attraverso software 

Iso si basa anche su incapsulamento e decapsulamento 

### Scambio delle informazione tra livelli : overhaud 

| Livello       |               |     |
| ------------- | ------------- | --- |
| Applicazione  | Dati grezzi   | 0   |
| Presentazione | Unita dati    | \|  |
| Sessione      | unita dati    | \|  |
| Network       | unita dati    | \|  |
| DataLink      | unita dati    | \|  |
| Trasporto     | unita dati    | \|  |
| Fisico        | flusso di bit | V   |
i dati grezzi generati dall applicazione 
e scorrono ogni volta giu aggiungendo dei bit overhead man mano che un protocollo ci mette mano

e come se ogni portocollo aggiungesse un qualche tipo di imballaggio al dato che man mano che scende viene garnito sempre piu 

# Lezione 17/03/25

# ARQ protocols 
- stop and wait 
	- vecchio protocollo per verificare la trama ricevuta 
		- inefficente sostitutito da sliding window
- sliding windows 
	- mentre si riceve un riscontro durante la destinaizone si mandano nodi succesivi in contemporanea ( non si stoppa !)
		- appena riceve un reject , allora la trama deve rimandare la trama del reject e tutte le successive  ( anche se sono gia state mandate ) 
	- se non vengono ricevuti tanti file , viene mandato il bit P/F ( Poll/Final) , che consiste in una sollecitazione e chiede un responso , il pool final = 1 , allora arriva il responso 
		- Il responso conferma quali sono arrivate , puo anche avvenire che ne sono arrivate dipiu di quelle a cui si è data conferma, per cui allora si riparte dall'ultima effetivamente arrivata 

