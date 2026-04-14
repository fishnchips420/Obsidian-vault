```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 2: Basi e Indipendenza Lineare}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a)}
\textbf{Testo:} Stabilisci se i seguenti vettori sono linearmente dipendenti o indipendenti.

\begin{enumerate}[label=\arabic*.]
    % Caso 1
    \item $V = \mathbb{R}^2; \quad v_1 = \binom{5}{6}, v_2 = \binom{-15}{-18}$
    \begin{itemize}
        \item Notiamo che $v_2 = -3 \cdot v_1$.
        \item Esiste una combinazione lineare non nulla ($3v_1 + v_2 = \vec{0}$).
        \item \textbf{Conclusione:} I vettori sono linearmente \textbf{dipendenti}.
    \end{itemize}

    % Caso 2
    \item $V = \mathbb{R}^3; \quad v_1=\binom{1}{0}{1}, v_2=\binom{0}{1}{1}, v_3=\binom{1}{1}{0}$
    \begin{itemize}
        \item Impostiamo la combinazione lineare nulla: $\alpha v_1 + \beta v_2 + \gamma v_3 = \vec{0}$.
        $$ \begin{cases} \alpha + \gamma = 0 \\ \beta + \gamma = 0 \\ \alpha + \beta = 0 \end{cases} \implies \begin{cases} \alpha = -\gamma \\ \beta = -\gamma \\ -2\gamma = 0 \implies \gamma=0 \end{cases} $$
        \item Otteniamo $\alpha = \beta = \gamma = 0$.
        \item \textbf{Conclusione:} I vettori sono linearmente \textbf{indipendenti}.
    \end{itemize}

    % Caso 3
    \item $V = \mathbb{R}^3; \quad v_1=\binom{2}{3}{4}, v_2=\binom{1/2}{0}{1}, v_3=\binom{\sqrt{2}}{-\sqrt{2}}{2\sqrt{2}}$
    \begin{itemize}
        \item Impostiamo il sistema:
        $$ \begin{cases} 2\alpha + \frac{1}{2}\beta + \sqrt{2}\gamma = 0 \\ 3\alpha - \sqrt{2}\gamma = 0 \\ 4\alpha + \beta + 2\sqrt{2}\gamma = 0 \end{cases} $$
        \item Dalla seconda equazione: $\sqrt{2}\gamma = 3\alpha \implies \gamma = \frac{3}{\sqrt{2}}\alpha$.
        \item Sostituendo si trova che il sistema ammette soluzioni non nulle (infinite soluzioni).
        \item \textbf{Conclusione:} I vettori sono linearmente \textbf{dipendenti}.
    \end{itemize}

    % Caso 4
    \item $V = M_{2,2}(\mathbb{R}); \quad A=\begin{pmatrix}1&0\\0&0\end{pmatrix}, B=\begin{pmatrix}1&0\\1&1\end{pmatrix}, C=\begin{pmatrix}0&0\\4&0\end{pmatrix}$
    \begin{itemize}
        \item Impostiamo $\alpha A + \beta B + \gamma C = \mathbf{0}$.
        $$ \begin{pmatrix} \alpha+\beta & 0 \\ \beta+4\gamma & \beta \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} $$
        \item $\beta=0$ (dall'elemento $a_{22}$). $\alpha=0$ (da $a_{11}$ sapendo $\beta=0$). $\gamma=0$ (da $a_{21}$).
        \item \textbf{Conclusione:} Sono linearmente \textbf{indipendenti}.
    \end{itemize}

    % Caso 5
    \item $V = \mathbb{R}_2[t]; \quad p_1=t+1, p_2=3t^2-5, p_3=2t+2$
    \begin{itemize}
        \item Notiamo subito che $p_3 = 2(t+1) = 2p_1$.
        \item Poiché un vettore è multiplo di un altro, l'insieme è legato.
        \item \textbf{Conclusione:} Sono linearmente \textbf{dipendenti}.
    \end{itemize}
\end{enumerate}

\hrulefill

\section*{Esercizio (b)}
\textbf{Testo:} Scrivi tutti i possibili sottoinsiemi massimali di vettori linearmente indipendenti dell'insieme $A$.

\textbf{Caso 1:} $V = \mathbb{R}^3; A = \{ v_1=\binom{1}{0}{4}, v_2=\binom{-1}{-1}{0}, v_3=\binom{0}{1}{-4}, v_4=\binom{0}{0}{1} \}$
\begin{itemize}
    \item Analizziamo con il metodo degli scarti successivi (o osservazione diretta delle risoluzioni):
    \item $v_1$ e $v_2$ sono indipendenti (non proporzionali).
    \item Proviamo $v_1, v_2, v_3$:
    $$ \binom{1}{0}{4} + \binom{-1}{-1}{0} = \binom{0}{-1}{4} = -1 \cdot \binom{0}{1}{-4} = -v_3 $$
    \item Quindi $v_1 + v_2 + v_3 = \vec{0}$. $v_3$ dipende dai primi due.
    \item $v_4$ è chiaramente indipendente da $v_1, v_2$ (ha l'ultima componente che "rompe" le combinazioni precedenti per generare zeri).
    \item \textbf{Sottoinsiemi massimali (Basi estraibili):}
    $$ B_1 = \{v_1, v_2, v_4\}; \quad B_2 = \{v_2, v_3, v_4\}; \quad B_3 = \{v_1, v_3, v_4\} $$
\end{itemize}

\hrulefill

\section*{Esercizio (c)}
\textbf{Testo:} Trova le coordinate di $v_0$ rispetto alla base $B$.

\textbf{Caso 1:} $V = \mathbb{R}^2, v_0 = \binom{7}{15}, B = \{ \binom{2}{1}, \binom{1}{-1} \}$
\begin{itemize}
    \item Equazione vettoriale: $x \binom{2}{1} + y \binom{1}{-1} = \binom{7}{15}$
    \item Sistema associato:
    $$ \begin{cases} 2x + y = 7 \\ x - y = 15 \end{cases} $$
    \item Sommando le due equazioni: $3x = 22 \implies x = \frac{22}{3}$ (Nota: nel manoscritto originale c'era un calcolo diverso che portava a $x=-8, y=23$, verifichiamo la coerenza).
    \item \textit{Verifica sul manoscritto [6]:} Il manoscritto risolve:
    $$ \begin{cases} 2\alpha + \beta = 7 \\ \alpha - \beta = 15 \end{cases} \implies \alpha=15+\beta \implies 2(15+\beta)+\beta=7 \implies 30+3\beta=7 \implies 3\beta=-23 \implies \beta=-23/3 $$
    Allora $\alpha = 15 - 23/3 = 22/3$.
    \item \textbf{Soluzione Corretta:} $[\alpha]_B = \binom{22/3}{-23/3}$.
    \item \textit{Nota:} Se il manoscritto riportava $\alpha=-8, \beta=23$, c'era un errore di calcolo nel segno ($2(-8)+23 = 7$ OK, ma $-8-23 = -31 \neq 15$). Seguo il calcolo matematico corretto qui sopra.
\end{itemize}

\textbf{Caso 3 (Matrici):} $V = M_{2,3}, v_0 = \begin{pmatrix} 1 & 5 & 10 \\ -1 & 0 & 7 \end{pmatrix}$
\begin{itemize}
    \item Rispetto alla \textbf{Base Canonica} delle matrici ($E_{11}, E_{12}, \dots$), le coordinate sono semplicemente le entrate della matrice lette in ordine.
    \item \textbf{Coordinate:} $(1, 5, 10, -1, 0, 7)$.
\end{itemize}

\end{document}
```