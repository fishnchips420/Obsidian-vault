calcolare la media , la media tra due array 
bisogna operare nelle due dimensioni separate 
- media 
	tutti gli int sommati e divisi per il numero degli int 
	for : scorre tutte righe e le aggiunge finche il numero delle righe < delle righe righe totali 
	dividere il numero trovato per le righe totali = media righe/colonne 

- deviazione standard (quanto ogni valore e distante dalla propria media)
	cicle for che scorrendo tutte le variabili , fa una sottrazione con la media , per capire la distanza ( usare il valore assoluto ? )


```c
int somma_righe = 0 //inizializzazione
int somma_colonne = 0 //inizializzazione
double media_righe = 0  
double media_colonne = 0  
for (int i = 0; i < N; i++) {
somma_righe = somma_righe + m[i][0]; //ciclo che somma le righe 
//non so se lo zero viene contato come nullo 
//il dubbio e che se tengo solo [i] possa far confusione tra righe e colonne 
//non dovrebbe sussistere il problema visto che esiste il define che ha il numero di righe 


        for (int j = 0; j < M; j++)
        {
	somma_colonne = somma_colonne + m[0][j];
        }
media_righe = somma_righe / i; 
media colonne = somma_colonne / j; 
for (int a = o; a < N; a++)        
```