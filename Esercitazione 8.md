```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 8: Diagonalizzazione}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a) - Verifica Diagonalizzabilità}
\textbf{Testo:} Stabilisci se le matrici sono diagonalizzabili e trova la base di autovettori.

\subsection*{Matrice A}
$$ A = \begin{pmatrix} -5 & 4 & 10 \\ 0 & 1 & 0 \\ -3 & 2 & 6 \end{pmatrix} $$
\begin{enumerate}
    \item \textbf{Polinomio Caratteristico:}
    Sviluppando $\det(A - \lambda I)$ lungo la seconda riga:
    $$ p(\lambda) = (1-\lambda) [(-5-\lambda)(6-\lambda) - (-30)] = (1-\lambda)(\lambda^2 - \lambda) = -\lambda(1-\lambda)^2 $$
    \item \textbf{Autovalori e $m_a$:}
    \begin{itemize}
        \item $\lambda_1 = 0$ con $m_a(0) = 1$.
        \item $\lambda_2 = 1$ con $m_a(1) = 2$ (punto critico).
    \end{itemize}
    \item \textbf{Verifica $m_g$ per $\lambda=1$:}
    $$ A - 1I = \begin{pmatrix} -6 & 4 & 10 \\ 0 & 0 & 0 \\ -3 & 2 & 5 \end{pmatrix} $$
    Le righe sono proporzionali ($R_1 = 2R_3$). Il rango è 1.
    $$ m_g(1) = 3 - \text{rg}(A-I) = 3 - 1 = 2 $$
    Poiché $m_g(1) = m_a(1)$, la matrice è \textbf{diagonalizzabile}.
    \item \textbf{Autospazi (Basi):}
    \begin{itemize}
        \item $V_1 = \text{Ker}(A-I)$: $-3x + 2y + 5z = 0 \implies x = \frac{2y+5z}{3}$.
        Base $V_1$: $\{ \binom{2}{3}{0}, \binom{5}{0}{3} \}$.
        \item $V_0 = \text{Ker}(A)$: Risolvendo il sistema, si trova $v = \binom{2}{0}{1}$.
    \end{itemize}
    \item \textbf{Matrice $P$ e $D$:}
    $$ D = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}, \quad P = \begin{pmatrix} 2 & 5 & 2 \\ 3 & 0 & 0 \\ 0 & 3 & 1 \end{pmatrix} $$
\end{enumerate}

\subsection*{Matrice B}
$$ B = \begin{pmatrix} 1 & 0 & 0 \\ 2 & 2 & -1 \\ 2 & 1 & 0 \end{pmatrix} $$
\begin{enumerate}
    \item \textbf{Autovalori:} Calcolando il determinante si ottiene $(1-\lambda)^3$.
    $\lambda = 1$ con $m_a(1) = 3$.
    \item \textbf{Verifica $m_g$:}
    $$ B - I = \begin{pmatrix} 0 & 0 & 0 \\ 2 & 1 & -1 \\ 2 & 1 & -1 \end{pmatrix} $$
    Il rango è 1. Quindi $m_g(1) = 3 - 1 = 2$.
    \item \textbf{Conclusione:} Poiché $m_g(1) = 2 \neq m_a(1) = 3$, la matrice \textbf{non} è diagonalizzabile.
\end{enumerate}

\hrulefill

\section*{Esercizio (b/c) - Parametro $k$}
\textbf{Testo:} Discutere la diagonalizzabilità di $A_k = \begin{pmatrix} k+2 & 4 & -4 \\ -k & -k & 2 \\ 0 & 0 & -2 \end{pmatrix}$.

\begin{enumerate}
    \item \textbf{Polinomio Caratteristico:}
    Sviluppo lungo la terza riga:
    $$ p(\lambda) = (-2-\lambda) [ (k+2-\lambda)(-k-\lambda) - (-4k) ] $$
    Analizzando il termine quadratico: $\lambda^2 - 2\lambda + (k^2+2k-4k) = \lambda^2 - 2\lambda -k^2+2k$.
    Risolvendo l'equazione di 2° grado: $\Delta/4 = 1 - (-k^2+2k) = (k-1)^2$.
    Radici: $\lambda = 1 \pm (k-1) \implies \lambda_2 = k, \lambda_3 = 2-k$.
    \textbf{Autovalori:} $\{-2, k, 2-k\}$.

    \item \textbf{Discussione Coincidenze:}
    La matrice è certamente diagonalizzabile se i tre autovalori sono distinti. Controlliamo quando coincidono:
    \begin{itemize}
        \item $k = -2$: Autovalori $\{-2, -2, 4\}$. $m_a(-2)=2$.
        \item $k = 2-k \implies k=1$: Autovalori $\{-2, 1, 1\}$. $m_a(1)=2$.
        \item $2-k = -2 \implies k=4$: Autovalori $\{-2, 4, -2\}$. $m_a(-2)=2$.
    \end{itemize}

    \item \textbf{Analisi dei casi critici (dal manoscritto):}
    \begin{itemize}
        \item \textbf{Caso $k=-2$:}
        Calcoliamo $rg(A_{-2} - (-2)I) = rg\begin{pmatrix} 2 & 4 & -4 \\ 2 & 4 & -4 \\ 0 & 0 & 0 \end{pmatrix} = 1$.
        $m_g(-2) = 3-1 = 2$. Poiché $m_g = m_a$, è \textbf{diagonalizzabile}. (Nota: il manoscritto [6] calcola rango 2 e conclude NON diag, verifichiamo: la sottomatrice $2x2$ in alto a sx ha det 0, ma le righe sono uguali. Rango 1. Il manoscritto potrebbe avere un errore di calcolo qui o aver considerato un minore non nullo che non vedo. Correggendo con Gauss: $R_2-R_1 \to$ riga nulla. Rango 1. Quindi diag).
        
        \item \textbf{Caso $k=1$:}
        Autovalori $\{-2, 1, 1\}$. Matrice $A_1$. Cerchiamo $m_g(1)$.
        $A_1 - I = \begin{pmatrix} 2 & 4 & -4 \\ -1 & -2 & 2 \\ 0 & 0 & -3 \end{pmatrix}$.
        Determinante $\neq 0$ (l'ultima riga è indipendente). Rango 3? No, ultima colonna non proporzionale. Rango 2.
        $m_g(1) = 3-2=1$. Poiché $m_g(1) \neq m_a(1)=2$, \textbf{non} è diagonalizzabile.
        
        \item \textbf{Caso $k=4$:}
        Autovalori $\{-2, 4, -2\}$. Cerchiamo $m_g(-2)$.
        $A_4 - (-2)I = \begin{pmatrix} 8 & 4 & -4 \\ -4 & -2 & 2 \\ 0 & 0 & 0 \end{pmatrix}$.
        Righe proporzionali. Rango 1. $m_g(-2) = 2 = m_a(-2)$. \textbf{Diagonalizzabile}.
    \end{itemize}
    
    \item \textbf{Conclusione:}
    La matrice è diagonalizzabile per $k \neq 1$.
\end{enumerate}

\end{document}
```