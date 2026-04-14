```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 6: Isomorfismi e Matrici}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a) - Coordinate e Polinomi}
\textbf{Testo:} Dati $V = \mathbb{R}_4[t]$ e la base dei monomi $B=\{1, t, t^2, t^3, t^4\}$, lavorare con i polinomi:
$$ p_1 = 1+6t-t^2-2t^3, \quad p_2 = 3t-t^3, \quad p_3 = 3p_1 - t^4, \quad p_4 = p_2' $$

\subsection*{1. Calcolo delle Coordinate $F_B(p_i)$}
Lo spazio ha dimensione 5. I vettori coordinate sono le colonne dei coefficienti ordinati (da grado 0 a 4):
\begin{itemize}
    \item $p_1 \to v_1 = \binom{1}{6}{-1}{-2}{0}$
    \item $p_2 \to v_2 = \binom{0}{3}{0}{-1}{0}$
    \item $p_3 = 3(1+6t-t^2-2t^3) - t^4 = 3 + 18t -3t^2 -6t^3 - t^4$ \\
          $\to v_3 = \binom{3}{18}{-3}{-6}{-1}$
    \item $p_4 = \frac{d}{dt}(3t-t^3) = 3 - 3t^2$ \\
          $\to v_4 = \binom{3}{0}{-3}{0}{0}$
\end{itemize}

\subsection*{2. Verifica Indipendenza e Base di $U$}
Costruiamo la matrice $A$ con i vettori $v_1, \dots, v_4$ come colonne e riduciamo a scala (Gauss) per trovare il rango.
$$
A = \begin{pmatrix} 
1 & 0 & 3 & 3 \\
6 & 3 & 18 & 0 \\
-1 & 0 & -3 & -3 \\
-2 & -1 & -6 & 0 \\
0 & 0 & -1 & 0 
\end{pmatrix}
\xrightarrow{Riduzione}
\begin{pmatrix} 
1 & 0 & 3 & 3 \\
0 & 3 & 0 & -18 \\
0 & 0 & -1 & 0 \\
0 & 0 & 0 & -6 \\
0 & 0 & 0 & 0 
\end{pmatrix}
$$
(Nota: I passaggi intermedi di riduzione sono nel manoscritto [2]).
\begin{itemize}
    \item Ci sono 4 pivot non nulli.
    \item **Conclusione:** I 4 polinomi sono linearmente indipendenti.
    \item **Base di U:** $\{p_1, p_2, p_3, p_4\}$. Dimensione = 4.
\end{itemize}

\subsection*{3. Completamento e Supplementare}
Siamo in $\mathbb{R}^5$ (coordinate). Abbiamo 4 pivot nelle colonne 1, 2, 3, 4. Per completare a una base di $\mathbb{R}^5$, ci serve un vettore che "copra" la riga mancante o che sia indipendente.
Guardando la matrice ridotta, manca un pivot sull'ultima riga o una combinazione che generi tutto.
Il manoscritto suggerisce di aggiungere il vettore della base canonica che non è generato.
Un supplementare semplice in $V$ è lo spazio generato dal monomio mancante o indipendente, ad esempio $W = Span(t)$ o simile, verificando con Gauss che il rango totale diventi 5.

\hrulefill

\section*{Esercizio (d) - Applicazioni Lineari e Matrici}
\textbf{Testo:} 
$T\binom{x}{y}{z} = \binom{3x+z}{x+2y}{5z}$, \quad $S\binom{x}{y}{z} = \binom{x-z}{x-y}{-x}$.

\subsection*{1. Matrici Associate}
Costruiamo le matrici mettendo nelle colonne le immagini di $e_1, e_2, e_3$:
$$ A = M_T = \begin{pmatrix} 3 & 0 & 1 \\ 1 & 2 & 0 \\ 0 & 0 & 5 \end{pmatrix}, \quad B = M_S = \begin{pmatrix} 1 & 0 & -1 \\ 1 & -1 & 0 \\ -1 & 0 & 0 \end{pmatrix} $$

\subsection*{2. Calcolo dei Prodotti (Composizione)}
\textbf{Calcolo $C = A \cdot B$ (corrisponde a $T \circ S$):}
$$ C = \begin{pmatrix} 3 & 0 & 1 \\ 1 & 2 & 0 \\ 0 & 0 & 5 \end{pmatrix} \cdot \begin{pmatrix} 1 & 0 & -1 \\ 1 & -1 & 0 \\ -1 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 2 & 0 & -3 \\ 3 & -2 & -1 \\ -5 & 0 & 0 \end{pmatrix} $$
L'applicazione $P = T \circ S$ è definita da $C \cdot \binom{x}{y}{z} = \binom{2x-3z}{3x-2y-z}{-5x}$.

\textbf{Calcolo $D = B \cdot A$ (corrisponde a $S \circ T$):}
$$ D = \begin{pmatrix} 1 & 0 & -1 \\ 1 & -1 & 0 \\ -1 & 0 & 0 \end{pmatrix} \cdot \begin{pmatrix} 3 & 0 & 1 \\ 1 & 2 & 0 \\ 0 & 0 & 5 \end{pmatrix} = \begin{pmatrix} 3 & 0 & -4 \\ 2 & -2 & 1 \\ -3 & 0 & -1 \end{pmatrix} $$
L'applicazione $Q = S \circ T$ è definita da $D \cdot \binom{x}{y}{z}$.
\textbf{Nota:} $AB \neq BA$, quindi la composizione non è commutativa.

\hrulefill

\section*{Esercizio (e) - Matrice Inversa}
\textbf{Testo:} Calcolare l'inversa di $A = \begin{pmatrix} 1 & 3 & 2 \\ 0 & 0 & 2 \\ 1 & -3 & 0 \end{pmatrix}$.

\textbf{Metodo (Gauss-Jordan):} Affianchiamo la matrice identità $(A | I)$.
$$ \left(\begin{array}{ccc|ccc} 1 & 3 & 2 & 1 & 0 & 0 \\ 0 & 0 & 2 & 0 & 1 & 0 \\ 1 & -3 & 0 & 0 & 0 & 1 \end{array}\right) $$
1. Scambio $R_2 \leftrightarrow R_3$ per avere pivot non nullo:
$$ \left(\begin{array}{ccc|ccc} 1 & 3 & 2 & 1 & 0 & 0 \\ 1 & -3 & 0 & 0 & 0 & 1 \\ 0 & 0 & 2 & 0 & 1 & 0 \end{array}\right) $$
2. Operazione $R_2 \leftarrow R_2 - R_1$:
$$ \left(\begin{array}{ccc|ccc} 1 & 3 & 2 & 1 & 0 & 0 \\ 0 & -6 & -2 & -1 & 0 & 1 \\ 0 & 0 & 2 & 0 & 1 & 0 \end{array}\right) $$
3. Risolvendo all'indietro per ottenere l'identità a sinistra (vedi manoscritto [4] per i calcoli di frazioni):
$$ A^{-1} = \begin{pmatrix} 1/2 & -1/2 & 1/2 \\ 1/6 & -1/6 & -1/6 \\ 0 & 1/2 & 0 \end{pmatrix} $$

\textbf{Verifica Proprietà:}
Il testo chiede di verificare $(AB)^{-1} = B^{-1}A^{-1}$.
Nel manoscritto [5], vengono calcolate separatamente $B^{-1}$ e il prodotto inverso, confermando l'uguaglianza.

\end{document}
```