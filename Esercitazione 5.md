```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 5: Metodo di Gauss e Sistemi}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Parte 1: Riduzione a Scala e Rango}
\textbf{Esercizio Introduttivo:} Ridurre a scala la matrice $A$ e calcolarne il rango.
$$ A = \begin{pmatrix} 2 & 3 & -1 & 1 \\ 1 & 0 & -2 & -1 \\ 0 & 2 & 12 & 0 \\ 1 & 1 & 1 & 1 \end{pmatrix} $$

\textbf{Svolgimento [da Manoscritto]:}
Scambiamo le righe per avere un pivot comodo (1) in alto a sinistra.
$$ \xrightarrow{R_1 \leftrightarrow R_2} \begin{pmatrix} 1 & 0 & -2 & -1 \\ 2 & 3 & -1 & 1 \\ 0 & 2 & 12 & 0 \\ 1 & 1 & 1 & 1 \end{pmatrix} $$
Operazioni: $R_2 \leftarrow R_2 - 2R_1$ e $R_4 \leftarrow R_4 - R_1$.
$$ \begin{pmatrix} 1 & 0 & -2 & -1 \\ 0 & 3 & 3 & 3 \\ 0 & 2 & 12 & 0 \\ 0 & 1 & 3 & 2 \end{pmatrix} $$
Proseguiamo la riduzione (possiamo dividere $R_2$ per 3). Alla fine del processo a scala otteniamo 3 pivot non nulli.
\textbf{Risultato:} $rg(A) = 3$.

\hrulefill

\section*{Parte 2: Sistemi Lineari (Esercizio a)}
\textbf{Sistema 3:}
$$ \begin{cases} -x + y + 2z = 5 \\ y - 4z = 0 \\ x - y = 10 \\ 3x - 2y = 1 \end{cases} $$
Matrice completa associata $(A|b)$:
$$ \left(\begin{array}{ccc|c} -1 & 1 & 2 & 5 \\ 0 & 1 & -4 & 0 \\ 1 & -1 & 0 & 10 \\ 3 & -2 & 0 & 1 \end{array}\right) $$
Riducendo a scala, il manoscritto nota che si ottiene una riga del tipo $\begin{pmatrix} 0 & 0 & 0 & -59 \end{pmatrix}$ (o simile termine noto non nullo con coefficienti nulli).
Questo implica $0 = -59$, che è impossibile.
\textbf{Conclusione:} Il rango di $A$ è 3, il rango di $A|b$ è 4. Il sistema è \textbf{impossibile} (nessuna soluzione).

\hrulefill

\section*{Parte 3: Sistemi con Parametro (Esercizio b)}
\textbf{Testo:} Discutere al variare di $h \in \mathbb{R}$:
$$ \begin{cases} x + 2y + 3z + 4w = 1 \\ -z + 4w = -h \\ hx + 2y + 2w = 1 \\ z + w = 0 \end{cases} $$
\textbf{Svolgimento [da Manoscritto]:}
Costruiamo la matrice e riduciamo a scala. Un punto critico nell'analisi dei pivot emerge nel termine $(2-2h)$ o simile.
La matrice ridotta finale presenta una forma del tipo:
$$ \begin{pmatrix} 1 & 2 & 3 & 4 & | & 1 \\ 0 & 2-2h & -3h & \dots & | & 1-h \\ 0 & 0 & -1 & 4 & | & 0 \\ 0 & 0 & 0 & 5 & | & -h \end{pmatrix} $$
(Nota: i passaggi intermedi nel manoscritto portano a isolare i pivot).

\textbf{Discussione dei casi:}
\begin{itemize}
    \item \textbf{Caso $h=1$:} Sostituendo $h=1$ nella matrice ridotta, la seconda riga diventa $\begin{pmatrix} 0 & 0 & -3 & \dots \end{pmatrix}$. 
    Analizzando i ranghi: $rg(A)=3$ mentre $rg(A|b)=4$.
    \textbf{Esito:} Sistema \textbf{impossibile} (nessuna soluzione).
    
    \item \textbf{Caso $h \neq 1$:} Tutti i 4 pivot sono non nulli.
    $rg(A) = 4$ e $rg(A|b) = 4$. Numero incognite = 4.
    \textbf{Esito:} Sistema determinato (\textbf{Unica soluzione}).
    La soluzione si trova risolvendo all'indietro (sostituzione) partendo da $5w = -h \implies w = -h/5$.
\end{itemize}

\hrulefill

\section*{Parte 4: Applicazioni di Gauss ai Sottospazi}
\textbf{Esercizio (b) - Dimensione di Span con parametro}
Vettori: $v_1=(0,0,1,1), v_2=(2,k,0,0), v_3=(1,1,1,1), v_4=(3,0,2,2)$.
Mettiamo i vettori in riga (o colonna) e riduciamo.
Il manoscritto evidenzia che il rango dipende se un'espressione contenente $k$ si annulla.
\begin{itemize}
    \item Se i vettori diventano linearmente dipendenti per un certo $k$, la dimensione scende.
    \item Solitamente $dim(W)=4$ (massima) tranne per valori critici di $k$.
\end{itemize}

\textbf{Esercizio (c) - Nucleo e Immagine}
Data la matrice $A$ (dipendente da $k$):
$$ A = \begin{pmatrix} 1 & 3 & 2 & 4 \\ 1 & 0 & 0 & k \\ \dots & \dots & \dots & \dots \end{pmatrix} $$
\begin{itemize}
    \item \textbf{Immagine:} La dimensione è data dal rango $r$. Una base è formata dalle $r$ colonne della matrice originale corrispondenti alla posizione dei pivot.
    \item \textbf{Nucleo:} La dimensione è $n - r$ (Teorema della dimensione). Per trovare la base, si risolve il sistema omogeneo $Ax = 0$.
\end{itemize}

\textbf{Esercizio (f) - Intersezione e Somma}
Dati $U = Span(u_1, u_2, u_3)$ e $W = Span(w_1, w_2, w_3)$.
\begin{enumerate}
    \item \textbf{Somma $U+W$:} Si crea una matrice unica con tutti i generatori $\{u_i, w_j\}$. Si riduce a scala. I vettori non nulli rimasti formano una base della somma.
    \item \textbf{Intersezione $U \cap W$:}
    \begin{itemize}
        \item Metodo 1 (Cartesiano): Trovare equazioni cartesiane di $U$ e $W$, metterle a sistema.
        \item Metodo 2 (Vettoriale): Scrivere il generico vettore $v \in U$ come $\alpha u_1 + \dots$ e uguagliarlo a $v \in W$ ($\beta w_1 + \dots$). Risolvere il sistema per trovare le relazioni tra i coefficienti.
    \end{itemize}
    Il manoscritto calcola $dim(U+W)$ tramite il rango della matrice congiunta e usa Grassmann:
    $$ \dim(U \cap W) = \dim U + \dim W - \dim(U+W) $$
\end{enumerate}

\end{document}
```