```c
extern int bias 
```
 //per far leggere al compilatore variabili esterne al file

```c
#define PI_V = 3,14

```

```c
#debug = 0 
```
se attivato ( = 1 ) permette di disattivare un certo numero di funzioni 

define ==non è una variabile== , mette un etichetta di testo ad un valore e ==non è modificabile==


# Istruzioni

esistono due tipi di funzioni 
- di controllo
- semplice 

```c
const float F1=9
```
le ==variabili== const servono a rendere una variabile non modificabile 

## Istruzioni condizionali 

...? .... : ..... 
se e vero prima senno seconda 

condizioni mutuament eesclusive : o una o laltra 

```c
if ( n > 0 && n < 10){
	printf("inside 1");
else if ( n>=10){
	printf("printf inside 2");
	
}

}
```

```c
scanf("%c" , &oggetto); //tramite il puntatore & facciamo modificare alla macchina il valore

```

```c
toupper(int c)
tolower(int A)
```
\\per convertire un carattere in maiuscola/minuscola