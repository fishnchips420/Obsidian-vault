
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 1: Sottospazi Vettoriali}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a)}
\textbf{Testo:} Dato $W = \{ \binom{x}{y} \in \mathbb{R}^2 : x \ge 0, y \ge 0 \}$, dimostrare che è chiuso rispetto alla somma ma non rispetto al prodotto per scalare.

\begin{itemize}
    \item \textbf{Chiusura rispetto alla somma:}
    Siano $w_1 = \binom{x_1}{y_1}$ e $w_2 = \binom{x_2}{y_2}$ due vettori appartenenti a $W$. Questo significa che $x_1, y_1, x_2, y_2 \ge 0$.
    La somma è $w_1 + w_2 = \binom{x_1 + x_2}{y_1 + y_2}$.
    Poiché la somma di numeri non negativi è non negativa ($x_1+x_2 \ge 0$ e $y_1+y_2 \ge 0$), il vettore somma appartiene a $W$.
    
    \item \textbf{Chiusura rispetto al prodotto per scalare (Controesempio):}
    Sia $w = \binom{1}{1} \in W$ e sia $\lambda = -1 \in \mathbb{R}$.
    Il prodotto è $\lambda w = -1 \cdot \binom{1}{1} = \binom{-1}{-1}$.
    Poiché le componenti sono negative ($<0$), il vettore risultato $\notin W$.
\end{itemize}
\textbf{Conclusione:} $W$ \textbf{non} è un sottospazio vettoriale.

\hrulefill

\section*{Esercizio (b)}
\textbf{Testo:} Dato $W = \{ \binom{x}{y} \in \mathbb{R}^2 : xy = 0 \}$, dimostrare che è chiuso rispetto al prodotto per scalare ma non rispetto alla somma.

\begin{itemize}
    \item \textbf{Chiusura rispetto al prodotto per scalare:}
    Sia $w = \binom{x}{y} \in W$ (quindi $xy=0$) e $\lambda \in \mathbb{R}$.
    Il vettore scalato è $\lambda w = \binom{\lambda x}{\lambda y}$.
    Il prodotto delle componenti è $(\lambda x)(\lambda y) = \lambda^2 (xy) = \lambda^2 \cdot 0 = 0$.
    Quindi $\lambda w \in W$.
    
    \item \textbf{Chiusura rispetto alla somma (Controesempio):}
    Consideriamo i vettori $w_1 = \binom{1}{0}$ e $w_2 = \binom{0}{1}$.
    Entrambi appartengono a $W$ perché il prodotto delle loro componenti è 0.
    La somma è $w_1 + w_2 = \binom{1}{1}$.
    Il prodotto delle componenti della somma è $1 \cdot 1 = 1 \neq 0$.
    Quindi $w_1 + w_2 \notin W$.
\end{itemize}
\textbf{Conclusione:} $W$ \textbf{non} è un sottospazio vettoriale.

\hrulefill

\section*{Esercizio (d)}
Stabilire se $W$ è sottospazio vettoriale di $V$ nei seguenti casi.

\begin{enumerate}[label=\arabic*.]
    % Caso 1
    \item $V = \mathbb{R}^3; \quad W = \{ \binom{a}{a+1}{2a} : a \in \mathbb{R} \}$
    \begin{itemize}
        \item \textbf{Verifica del vettore nullo:} Per ottenere il vettore $\vec{0} = \binom{0}{0}{0}$, dovremmo avere $a=0$ dalla prima componente. Sostituendo $a=0$ nel vettore generico otteniamo $\binom{0}{1}{0} \neq \vec{0}$.
        \item \textbf{Conclusione:} Poiché $\vec{0} \notin W$, $W$ \textbf{non} è un sottospazio.
    \end{itemize}

    % Caso 2
    \item $V = \mathbb{R}^3; \quad W = \{ \binom{2\lambda}{\lambda+\mu}{2\mu} : \lambda, \mu \in \mathbb{R} \}$
    \begin{itemize}
        \item Possiamo riscrivere il vettore generico separando i parametri:
        $$ \binom{2\lambda}{\lambda+\mu}{2\mu} = \lambda \binom{2}{1}{0} + \mu \binom{0}{1}{2} $$
        \item $W$ è generato dallo Span dei vettori $v_1=\binom{2}{1}{0}$ e $v_2=\binom{0}{1}{2}$.
        \item \textbf{Conclusione:} Essendo un $Span$, $W$ \textbf{è} un sottospazio vettoriale.
    \end{itemize}

    % Caso 3
    \item $V = \mathbb{R}^2; \quad W = \{ \binom{x}{x^2} : x \in \mathbb{R} \}$
    \begin{itemize}
        \item \textbf{Controesempio Somma:} Siano $w_1 = \binom{1}{1}$ e $w_2 = \binom{1}{1}$. La somma è $\binom{2}{2}$.
        Affinché $\binom{2}{2} \in W$, la seconda componente dovrebbe essere il quadrato della prima ($2^2 = 4$), ma qui abbiamo $2 \neq 4$.
        \item \textbf{Conclusione:} $W$ \textbf{non} è un sottospazio (non è chiuso rispetto alla somma).
    \end{itemize}
    
    % Caso 4
    \item $V = M_{2,2}(\mathbb{R}); \quad W = \{ \begin{pmatrix} 2\alpha & 2\beta \\ 3\beta & 3\alpha \end{pmatrix} : \alpha, \beta \in \mathbb{R} \}$
    \begin{itemize}
        \item Possiamo riscrivere la matrice come combinazione lineare:
        $$ \alpha \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} + \beta \begin{pmatrix} 0 & 2 \\ 3 & 0 \end{pmatrix} $$
        \item \textbf{Conclusione:} $W$ è lo Span di due matrici, quindi \textbf{è} un sottospazio vettoriale.
    \end{itemize}

    % Caso 5
    \item $V = \mathbb{R}_3[t]; \quad W = \{ 2at + 3b : a, b \in \mathbb{R} \}$
    \begin{itemize}
        \item I vettori sono polinomi della forma $p(t) = 2a \cdot t + 3b \cdot 1$.
        \item Questo è lo Span dei polinomi $\{t, 1\}$ (con coefficienti scalati, che non cambiano la natura dello spazio).
        \item \textbf{Conclusione:} $W$ \textbf{è} un sottospazio vettoriale (coincide con i polinomi di grado $\le 1$).
    \end{itemize}

    % Caso 6
    \item $V = \mathbb{R}_2[t]; \quad W = \{ at^2 - 1 : a \in \mathbb{R} \}$
    \begin{itemize}
        \item \textbf{Verifica del vettore nullo:} Il polinomio nullo $\mathbf{0}(t) = 0t^2 + 0t + 0$ deve appartenere a $W$.
        Ponendo $at^2 - 1 = 0$ per ogni $t$, dovremmo avere $-1 = 0$, il che è impossibile.
        \item \textbf{Conclusione:} $\vec{0} \notin W$, quindi \textbf{non} è un sottospazio.
    \end{itemize}

    % Caso 7
    \item $V = M_{2,3}(\mathbb{R}); \quad W = \{ \begin{pmatrix} 0 & a & b \\ 0 & 0 & c \end{pmatrix} : a, b, c \in \mathbb{R} \}$
    \begin{itemize}
        \item La somma di due matrici di questo tipo preserva gli zeri nelle posizioni fisse (colonna 1, elemento 2,2). Anche il prodotto per scalare li preserva.
        \item Si può scrivere come Span di 3 matrici elementari.
        \item \textbf{Conclusione:} $W$ \textbf{è} un sottospazio vettoriale.
    \end{itemize}

    % Caso 8
    \item $V = \mathbb{R}^2; \quad W = \{ \binom{x}{y} : x^2 + y^2 = 1 \}$ (Circonferenza unitaria)
    \begin{itemize}
        \item \textbf{Verifica vettore nullo:} $0^2 + 0^2 = 0 \neq 1$.
        \item \textbf{Conclusione:} $\vec{0} \notin W$, quindi \textbf{non} è un sottospazio.
    \end{itemize}

    % Caso 9
    \item $V = \mathbb{R}^2; \quad W = \{ \binom{x}{y} : x^2 - y^2 = 0 \}$ (Iperbole degenere / $y = \pm x$)
    \begin{itemize}
        \item $W$ è l'unione delle rette $y=x$ e $y=-x$.
        \item \textbf{Controesempio Somma:} Prendo $w_1 = \binom{1}{1}$ (su $y=x$) e $w_2 = \binom{1}{-1}$ (su $y=-x$).
        La somma è $\binom{2}{0}$. Verifica condizione: $2^2 - 0^2 = 4 \neq 0$.
        \item \textbf{Conclusione:} $W$ \textbf{non} è un sottospazio vettoriale.
    \end{itemize}

\end{enumerate}

\end{document}
