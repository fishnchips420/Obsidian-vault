# Software 
__dati e istruzioni generati dalla macchina per generare un determinato risultato__

- __software di base__ : ( sistema operativo ) 
- __Firmware__ : Un software per fare funzionare un determinato dispositivo 

- __api__ : interfaccia 
- __macchina virtuale__  : virtualizzazione dell'hardware
---
## Sistema operativo 
_strato di programmi che opera al di sopra di hardware e firmware e gestisce l'elaboratore._

### Funzioni del sistema operativo 
- __gestione delle risorse__ 
- __gestione della memoria centrale__
- __organizzazione e gestione della memoria di massa__ 
- __interpetre ed esecuzione di comandi elementari__ (promt comandi)
- __gestione di un sistema multiutente__ 

esistono 
- sistemi senza S.O (sistema operativo) in linguaggio macchina 
- sistemi con S.O : comandi , programmi , dati 
---
## Ruolo del sistema operativo 



---
## Classificazione dei S.O 
- __monoprogrammato__ : un programma alla volta
- __multiprogrammato__ : piu programmi alla volta // con il __timesharing__ , piu programmi girano su un solo processore , suddividendo in tempistica i vari programmi, gestendo piu processi gestendoli uno alla volta  
---
## Programmi applicativi 

- __portabilita__ : la possibilita di portare un software da una macchina all altra ( c non e molto portabile )
---
## Ambiente di sviluppo 
- componente : editor 
- traduttore/compilatore : genera dal codice sorgente al codice eseguibile 
- debugger : eliminazione errori logici 
___
## Esecuzione programmi 
programma sorgente -> programma eseguibile -> esecuzione
Linguaggio utente -> linguaggio macchina -> esecuzione 
__Compilatore__ -> __linker__ (collega l nostro codice con le librerie ) -> __loader__ 
___
# Programmazione 
operazioni eseguite prima del main ad esempio : __inizializzazione delle variabili globali__ 
``float a = sqrtt(2,0);``  __sqrt__ = _funzione_  

- ``fprint`` __stampa su file__ 

``printf("%d %u %x\n" , x1 , x2, x2*x2);`` //__i numeri esadecimali__ sono la somma dei caratteri singoli ( 19 = 1+9)
	-255 = f 
# Extra 

- ripassa unsigned int %u 

// hex file : estensione di file da caricare in un dispositivo fisico
Cube programmer , editor di codice per modificare firmware di hardware // 

FreeRTOS : sistema operativo realtieme x microcontroller (integrato in software ) e microprocessori (hardware )
Erica : sistema operativo realtime usato in elettrodomestici / moto ecc. 


