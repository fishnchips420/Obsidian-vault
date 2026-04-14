```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 3: Spazi Supplementari e Somma Diretta}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a)}
\textbf{Testo:} Verifica che $U \oplus W = V$ nei seguenti casi.

\begin{enumerate}[label=\arabic*.]
    % Caso 1
    \item $V = \mathbb{R}^2; \quad U = \text{Span}\binom{1}{0}, \quad W = \text{Span}\binom{1}{2}$
    \begin{itemize}
        \item \textbf{Dimensione:} $\dim(U)=1$ (generato da un vettore non nullo), $\dim(W)=1$.
        \item \textbf{Somma delle dimensioni:} $1+1=2 = \dim(\mathbb{R}^2)$.
        \item \textbf{Intersezione:} Mettiamo i generatori in una matrice per verificarne l'indipendenza:
        $$ \det \begin{pmatrix} 1 & 1 \\ 0 & 2 \end{pmatrix} = 2 \neq 0 $$
        I vettori sono indipendenti, quindi formano una base di $\mathbb{R}^2$. L'intersezione è nulla.
        \item \textbf{Conclusione:} $U \oplus W = \mathbb{R}^2$.
    \end{itemize}

    % Caso 2
    \item $V = \mathbb{R}^3; \quad U = \text{Span}(e_1+e_3) = \text{Span}\binom{1}{0}{1}, \quad W = \text{Span}(e_1, e_2) = \text{Span}\left\{ \binom{1}{0}{0}, \binom{0}{1}{0} \right\}$
    \begin{itemize}
        \item \textbf{Dimensione:} $\dim(U)=1$, $\dim(W)=2$ (vettori di $W$ chiaramente indipendenti).
        \item \textbf{Somma dimensioni:} $1+2=3 = \dim(\mathbb{R}^3)$.
        \item \textbf{Indipendenza:} Verifichiamo se l'unione delle basi è libera.
        $$ \det \begin{pmatrix} 1 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0 \end{pmatrix} = 1 \cdot (1-0) = 1 \neq 0 $$
        \item \textbf{Conclusione:} I 3 vettori formano una base di $\mathbb{R}^3$, quindi la somma è diretta: $U \oplus W = \mathbb{R}^3$.
    \end{itemize}

    % Caso 3
    \item $V = \mathbb{R}_2[t]; \quad U = \text{Span}(t+1), \quad W = \{ p(t) : p(1)=0 \}$
    \begin{itemize}
        \item \textbf{Analisi di W:} Un polinomio generico è $p(t) = at^2+bt+c$.
        Condizione $p(1)=0 \implies a(1)^2+b(1)+c=0 \implies c = -a-b$.
        Sostituendo: $at^2+bt-a-b = a(t^2-1) + b(t-1)$.
        Base di $W$: $\{t^2-1, t-1\}$. Quindi $\dim(W)=2$.
        \item \textbf{Analisi di U:} Base $\{t+1\}$. $\dim(U)=1$.
        \item \textbf{Intersezione:} Prendiamo un elemento generico di $U$: $k(t+1)$.
        Vediamo se appartiene a $W$ (cioè se si annulla in 1):
        Valutiamo in $t=1$: $k(1+1) = 2k$.
        Affinché sia zero, deve essere $k=0$.
        \item \textbf{Conclusione:} L'intersezione è solo il polinomio nullo. Poiché $1+2=3=\dim(\mathbb{R}_2[t])$, allora $U \oplus W = V$.
    \end{itemize}
\end{enumerate}

\hrulefill

\section*{Esercizio (b)}
\textbf{Testo:} Dato $U = \{ x \in \mathbb{R}^4 : x_2 = x_1+x_3, x_4 = x_1+x_2+2x_3 \}$, calcola dimensione e scrivi due supplementari.

\begin{itemize}
    \item \textbf{Base di U:}
    Sostituiamo la prima equazione nella seconda:
    $x_4 = x_1 + (x_1+x_3) + 2x_3 = 2x_1 + 3x_3$.
    Variabili libere: $x_1, x_3$.
    Vettore generico: $\begin{pmatrix} x_1 \\ x_1+x_3 \\ x_3 \\ 2x_1+3x_3 \end{pmatrix} = x_1 \begin{pmatrix} 1 \\ 1 \\ 0 \\ 2 \end{pmatrix} + x_3 \begin{pmatrix} 0 \\ 1 \\ 1 \\ 3 \end{pmatrix}$.
    \item \textbf{Dimensione:} $\dim(U) = 2$.
    \item \textbf{Calcolo Supplementari (Metodo completamento):}
    Dobbiamo aggiungere 2 vettori della base canonica $\{e_1, e_2, e_3, e_4\}$ che siano indipendenti dai generatori di $U$.
    
    \textbf{Supplementare $W_1$:} Proviamo con $e_1, e_2$.
    Mettiamo in matrice i generatori di $U$ e $e_1, e_2$:
    $$ \begin{pmatrix} 1 & 0 & 1 & 0 \\ 1 & 1 & 0 & 1 \\ 0 & 1 & 0 & 0 \\ 2 & 3 & 0 & 0 \end{pmatrix} $$
    Riducendo a scala o calcolando il determinante, se il rango è 4, allora $W_1 = \text{Span}(e_1, e_2)$ è un supplementare (Nota: nel manoscritto si scelgono vettori che completano la matrice a scala).
    
    \textbf{Supplementare $W_2$:} Basta scegliere un'altra coppia, ad esempio $e_3, e_4$, e verificare l'indipendenza.
\end{itemize}

\hrulefill

\section*{Esercizio (d) - Matrici a traccia nulla}
\textbf{Testo:} $V = \{ A \in M_{2,2}(\mathbb{R}) : \text{tr}(A)=0 \}$.
\begin{enumerate}
    \item \textbf{Dimensione e Base:}
    $\text{tr}(A) = a_{11} + a_{22} = 0 \implies a_{22} = -a_{11}$.
    La matrice generica è $\begin{pmatrix} a_{11} & a_{12} \\ a_{21} & -a_{11} \end{pmatrix}$.
    Dipende da 3 parametri.
    Base: $B = \left\{ \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}, \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} \right\}$.
    $\dim(V) = 3$.

    \item \textbf{Verifica $A_0$ e Coordinate:}
    $A_0 = \begin{pmatrix} 12 & 7 \\ 1 & -12 \end{pmatrix}$.
    Traccia: $12 + (-12) = 0$. Sì, $A_0 \in V$.
    Coordinate rispetto alla base $B$:
    $A_0 = 12 \cdot M_1 + 7 \cdot M_2 + 1 \cdot M_3$.
    Coordinate: $(12, 7, 1)$.

    \item \textbf{Supplementari:}
    Dato $U = \{ \text{matrici antisimmetriche} \}$ (base $\begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}$) e $W = \text{Span}(\begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix})$.
    Verifica se sono supplementari in $V$.
    Bisogna controllare se la somma delle dimensioni è 3 e se l'intersezione è nulla.
    (Nel manoscritto si nota che $W$ è generato da $M_3$ della nostra base, mentre $U$ introduce una relazione tra $a_{12}$ e $a_{21}$).
\end{enumerate}

\end{document}
```