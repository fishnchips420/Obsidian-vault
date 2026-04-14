```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 7: Matrici Associate e Determinanti}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a) - Matrice Associata}
\textbf{Testo:} Scrivi la matrice associata a $T$ rispetto a basi a tua scelta.

\subsection*{Caso 1: $T: M_{2,3}(\mathbb{R}) \to \mathbb{R}_3[t]$}
$$ T\begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \end{pmatrix} = a_{21}t^3 + (a_{11}+a_{22})t^2 + (a_{12}+a_{23})t + a_{13} $$
\begin{itemize}
    \item \textbf{Basi:} Scegliamo le basi canoniche.
    Domino (dim 6): $E_{11}, E_{12}, E_{13}, E_{21}, E_{22}, E_{23}$.
    Codominio (dim 4): $\{1, t, t^2, t^3\}$.
    \item \textbf{Costruzione Colonne:}
    \begin{itemize}
        \item $T(E_{11})$ (dove $a_{11}=1$, altri 0) $\to t^2 \to (0,0,1,0)^T$
        \item $T(E_{12})$ (dove $a_{12}=1$) $\to t \to (0,1,0,0)^T$
        \item $T(E_{13})$ $\to 1 \to (1,0,0,0)^T$
        \item $T(E_{21})$ $\to t^3 \to (0,0,0,1)^T$
        \item $T(E_{22})$ $\to t^2 \to (0,0,1,0)^T$
        \item $T(E_{23})$ $\to t \to (0,1,0,0)^T$
    \end{itemize}
    \item \textbf{Matrice $A$ ($4 \times 6$):}
    $$ A = \begin{pmatrix} 
    0 & 0 & 1 & 0 & 0 & 0 \\
    0 & 1 & 0 & 0 & 0 & 1 \\
    1 & 0 & 0 & 0 & 1 & 0 \\
    0 & 0 & 0 & 1 & 0 & 0 
    \end{pmatrix} $$
\end{itemize}

\subsection*{Caso 2: $T: M_{2,2} \to M_{2,2}; \quad T(B) = B^T + 2B$}
\begin{itemize}
    \item \textbf{Base:} Canonica di $M_{2,2}$: $E_1=\binom{1\ 0}{0\ 0}, E_2=\binom{0\ 1}{0\ 0}, E_3=\binom{0\ 0}{1\ 0}, E_4=\binom{0\ 0}{0\ 1}$.
    \item \textbf{Calcolo Immagini:}
    \begin{itemize}
        \item $T(E_1) = E_1^T + 2E_1 = E_1 + 2E_1 = 3E_1 \to (3,0,0,0)^T$
        \item $T(E_2) = \binom{0\ 0}{1\ 0} + 2\binom{0\ 1}{0\ 0} = E_3 + 2E_2 \to (0,2,1,0)^T$
        \item $T(E_3) = \binom{0\ 1}{0\ 0} + 2\binom{0\ 0}{1\ 0} = E_2 + 2E_3 \to (0,1,2,0)^T$
        \item $T(E_4) = 3E_4 \to (0,0,0,3)^T$
    \end{itemize}
    \item \textbf{Matrice $A$ ($4 \times 4$):}
    $$ A = \begin{pmatrix} 3 & 0 & 0 & 0 \\ 0 & 2 & 1 & 0 \\ 0 & 1 & 2 & 0 \\ 0 & 0 & 0 & 3 \end{pmatrix} $$
\end{itemize}

\hrulefill

\section*{Esercizio (c) - Calcolo Determinanti}
\textbf{Nota:} Per i determinanti $3 \times 3$ usiamo Sarrus o Laplace. Per dimensioni superiori, Laplace o Gauss.

\subsection*{Matrice B (4x4)}
$$ B = \begin{pmatrix} 1 & -3 & 2 & 1 \\ 1 & 2 & -2 & -1 \\ 2 & -3 & 0 & 1 \\ 0 & -3 & 0 & 2 \end{pmatrix} $$
Sviluppiamo con Laplace lungo la \textbf{terza colonna} (ha due zeri):
$$ \det(B) = 2 \cdot (-1)^{1+3} \det M_{13} + (-2) \cdot (-1)^{2+3} \det M_{23} $$
$$ = 2 \cdot \det \begin{pmatrix} 1 & 2 & -1 \\ 2 & -3 & 1 \\ 0 & -3 & 2 \end{pmatrix} + 2 \cdot \det \begin{pmatrix} 1 & -3 & 1 \\ 2 & -3 & 1 \\ 0 & -3 & 2 \end{pmatrix} $$
I calcoli specifici nel manoscritto portano al risultato finale:
\textbf{Risultato:} $\det(B) = -4$ (confermato dalla soluzione [3]).

\subsection*{Matrice C (5x5)}
Matrice triangolare a blocchi o riducibile.
$$ C = \begin{pmatrix} 0 & 3 & 4 & -1 & 0 \\ 1 & 1 & -2 & -1 & 1 \\ 0 & 0 & 1 & -1 & 0 \\ 1 & 2 & 2 & 2 & 1 \\ 2 & 3 & 3 & 1 & 0 \end{pmatrix} $$
Strategia del manoscritto: Operazione $R_4 \leftarrow R_4 - R_2$ (o simili) per creare zeri nella prima colonna e poi Laplace.
\textbf{Risultato:} $\det(C) = 36$.

\hrulefill

\section*{Esercizio (d) - Invertibilità con Parametro}
\textbf{Testo:} Determina per quali $k$ la matrice è invertibile ($\det \neq 0$).

\subsection*{Matrice $B_h$ ($4 \times 4$)}
$$ B_h = \begin{pmatrix} h & 0 & 3 & h \\ h & 0 & 2 & h \\ 0 & h-1 & 1 & \sqrt{2} \\ h & 0 & 2 & -1 \end{pmatrix} $$
Sviluppo di Laplace lungo la \textbf{seconda colonna} (che ha un solo elemento non nullo $h-1$):
$$ \det(B_h) = (h-1) \cdot (-1)^{3+2} \cdot \det \begin{pmatrix} h & 3 & h \\ h & 2 & h \\ h & 2 & -1 \end{pmatrix} $$
Raccogliamo $h$ dalla prima colonna della sottomatrice:
$$ = -(h-1) \cdot h \cdot \det \begin{pmatrix} 1 & 3 & h \\ 1 & 2 & h \\ 1 & 2 & -1 \end{pmatrix} $$
Calcolando il determinante $3 \times 3$ (vedi manoscritto: $R_2-R_1$ etc.):
$$ \det(3 \times 3) = -(-1-h) - (h-h) = 1+h $$
Determinante totale:
$$ \det(B_h) = -h(h-1)(h+1) $$
\textbf{Condizione Invertibilità:} $\det \neq 0 \implies h \neq 0, h \neq 1, h \neq -1$.

\end{document}
```