Ecco il testo formattato correttamente per Obsidian, utilizzando `$$` per le formule matematiche:

``
## Quando verificare la forma indeterminata 0/0  

Un limite è nella forma **0/0** quando:  
1. Il **numeratore** tende a 0  
2. Il **denominatore** tende a 0  

Se entrambi tendono a zero, il limite è **indeterminato** e richiede ulteriori tecniche per essere risolto.  

### Tecniche per risolvere 0/0  
- **Scomposizione e semplificazione**: scomporre il numeratore e il denominatore per eliminare fattori comuni.  
- **Raccoglimento**: raccogliere un fattore comune per semplificare.  
- **Razionaleizzazione**: usare il coniugato se compaiono radici.  
- **Teorema di De L'Hôpital**: derivare numeratore e denominatore separatamente.  
- **Sviluppi di Taylor**: approssimare la funzione vicino al punto critico.  

### Esempio  
$$
\lim_{x \to 2} \frac{x^2 - 4}{x - 2}
$$  
Sostituendo x = 2:  
$$
\frac{2^2 - 4}{2 - 2} = \frac{0}{0}
$$  
Essendo una forma indeterminata, scomponiamo il numeratore:  
$$
\frac{(x - 2)(x + 2)}{x - 2}
$$  
Ora semplifichiamo il fattore comune (x - 2):  
$$
\lim_{x \to 2} (x + 2) = 4
$$  
**Risultato**: il limite vale **4**.  

Ecco l'elenco dei risultati indeterminati dei limiti in un formato compatibile con Obsidian:


## Risultati indeterminati dei limiti  

Nei limiti, alcune forme non permettono di determinare immediatamente il risultato e richiedono ulteriori analisi. Le principali forme indeterminate sono:  

- $$ \frac{\infty}{\infty} $$  
- $$ \infty - \infty $$  
- $$ 0 \times \infty $$  
- $$ 0^0 $$  
- $$ \infty^0 $$  
- $$ 1^\infty $$  

Per risolvere queste forme, si possono applicare tecniche come il Teorema di De L'Hôpital, la razionalizzazione, il confronto degli ordini di infinito o gli sviluppi di Taylor.  


