```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 4: Applicazioni Lineari}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a)}
\textbf{Testo:} Stabilisci se le seguenti funzioni sono lineari.

\begin{enumerate}[label=\arabic*.]
    % Caso 1
    \item $T: \mathbb{R}^2 \to \mathbb{R}^3; \quad T\binom{x}{y} = \binom{x}{2x}{x^2}$
    \begin{itemize}
        \item \textbf{Verifica Addittività:}
        $$ T\left( \binom{x_1}{y_1} + \binom{x_2}{y_2} \right) = T\binom{x_1+x_2}{y_1+y_2} = \binom{x_1+x_2}{2(x_1+x_2)}{(x_1+x_2)^2} $$
        La somma delle immagini è:
        $$ T\binom{x_1}{y_1} + T\binom{x_2}{y_2} = \binom{x_1}{2x_1}{x_1^2} + \binom{x_2}{2x_2}{x_2^2} = \binom{x_1+x_2}{2(x_1+x_2)}{x_1^2+x_2^2} $$
        Poiché $(x_1+x_2)^2 \neq x_1^2 + x_2^2$ (manca il doppio prodotto), l'addittività non vale.
        \item \textbf{Conclusione:} \textbf{Non è lineare}.
    \end{itemize}

    % Caso 2
    \item $T: M_{2,2}(\mathbb{R}) \to \mathbb{R}_2[t]; \quad T\begin{pmatrix} a & b \\ c & d \end{pmatrix} = at^2 + (b-c)t + 7d$
    \begin{itemize}
        \item \textbf{Condizione Necessaria $T(0)=0$:} Se la matrice è nulla ($a=b=c=d=0$), il polinomio risultante è $0t^2+0t+0 = \mathbf{0}$. OK.
        \item \textbf{Linearità:} Le componenti del polinomio risultato sono combinazioni lineari omogenee (di primo grado senza termini noti costanti) dei parametri di input $a,b,c,d$.
        \item \textbf{Conclusione:} \textbf{È lineare}.
    \end{itemize}
    
    % Caso 3
    \item $T: \mathbb{R}_3[t] \to \mathbb{R}_2[t]; \quad T(at^3+\dots+d) = (a+b)t^2 + (c+d)t + 3$
    \begin{itemize}
        \item \textbf{Condizione Necessaria:} Se il polinomio di input è nullo ($a=b=c=d=0$), l'output è il polinomio costante $3$.
        $$ T(\mathbf{0}) = 3 \neq \mathbf{0} $$
        \item \textbf{Conclusione:} \textbf{Non è lineare} (manca l'omogeneità).
    \end{itemize}

    % Caso 4
    \item $T: M_{2,2} \to M_{2,2}; \quad T(A) = 2A - 3A^T$
    \begin{itemize}
        \item Sfruttiamo le proprietà note: la trasposizione è lineare, il prodotto per scalare è lineare, la somma è lineare.
        \item Combinazione lineare di applicazioni lineari è lineare.
        \item \textbf{Conclusione:} \textbf{È lineare}.
    \end{itemize}
\end{enumerate}

\hrulefill

\section*{Esercizio (b)}
\textbf{Testo:} Calcola le coordinate $F_B(v_0)$ rispetto alla base $B$.

\begin{enumerate}[label=\arabic*.]
    % Caso 1
    \item $V = \mathbb{R}_3[t], \quad B=\{1, t, t^2, t^3\}, \quad v_0 = t^3 - t + 5$
    \begin{itemize}
        \item Ordiniamo il vettore $v_0$ secondo le potenze della base:
        $$ v_0 = 5 \cdot (1) + (-1) \cdot (t) + 0 \cdot (t^2) + 1 \cdot (t^3) $$
        \item Le coordinate sono i coefficienti ordinati.
        \item \textbf{Soluzione:} $F_B(v_0) = \begin{pmatrix} 5 \\ -1 \\ 0 \\ 1 \end{pmatrix}$.
    \end{itemize}

    % Caso 3
    \item $V = \mathbb{R}^3, \quad B=\{ v_1=\binom{1}{0}{0}, v_2=\binom{2}{3}{0}, v_3=\binom{0}{1}{1} \}, \quad v_0 = \binom{0}{-4}{0}$ (Nota: base corretta dal manoscritto e testo pdf).
    \begin{itemize}
        \item Impostiamo il sistema $\alpha_1 v_1 + \alpha_2 v_2 + \alpha_3 v_3 = v_0$:
        $$ \alpha_1 \binom{1}{0}{0} + \alpha_2 \binom{2}{3}{0} + \alpha_3 \binom{0}{1}{1} = \binom{0}{-4}{0} $$
        \item Risolviamo dal basso verso l'alto (sistema triangolare):
        \begin{enumerate}
            \item Riga 3: $\alpha_3 \cdot 1 = 0 \implies \alpha_3 = 0$.
            \item Riga 2: $3\alpha_2 + \alpha_3 = -4 \implies 3\alpha_2 = -4 \implies \alpha_2 = -4/3$.
            \item Riga 1: $\alpha_1 + 2\alpha_2 = 0 \implies \alpha_1 = -2(-4/3) = 8/3$.
        \end{enumerate}
        \item \textbf{Soluzione:} $F_B(v_0) = \binom{8/3}{-4/3}{0}$.
    \end{itemize}
\end{enumerate}

\hrulefill

\section*{Esercizio (c)}
\textbf{Testo:} Trova $h \in \mathbb{R}$ affinché $T$ sia lineare.

\textbf{Caso 1:} $T\binom{x}{y}{z} = \binom{2x+hy-z}{\dots}{-h^2+4}$
\begin{itemize}
    \item Affinché $T$ sia lineare, deve mappare il vettore nullo nel vettore nullo ($T(\vec{0})=\vec{0}$).
    \item La terza componente del vettore immagine è $-h^2+4$. Questa non dipende da $x,y,z$, è un termine noto.
    \item Deve essere zero: $-h^2 + 4 = 0 \implies h^2 = 4 \implies h = \pm 2$.
    \item \textbf{Conclusione:} $T$ è lineare se e solo se $h = 2$ oppure $h = -2$.
\end{itemize}

\hrulefill

\section*{Teorema della Dimensione (Esercizi Teorici)}
\textbf{Domanda 1:} Esiste applicazione lineare iniettiva da $\mathbb{R}_3[t]$ a $\mathbb{R}^2$?
\begin{itemize}
    \item Dimensione dominio $V = \mathbb{R}_3[t]$ è $4$ (base $1, t, t^2, t^3$).
    \item Dimensione codominio $W = \mathbb{R}^2$ è $2$.
    \item Se fosse iniettiva, $\dim(Ker T) = 0$.
    \item Teorema dimensione: $\dim V = \dim Ker T + \dim Im T \implies 4 = 0 + \dim Im T$.
    \item Ma $Im T \subseteq W$, quindi $\dim Im T \le 2$.
    \item Assurdo ($4 \le 2$ è falso).
    \item \textbf{Risposta:} No, non esiste.
\end{itemize}

\end{document}
```