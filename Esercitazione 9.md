```
\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{enumitem}

\title{Risoluzione Esercizi di Algebra Lineare \\ \large Scheda 9: Spazi Euclidei e Gram-Schmidt}
\author{Basato su "Esercizi COMPLETI algebra.pdf"}
\date{}

\begin{document}

\maketitle

\section*{Esercizio (a) - Verifica Ortogonalità}
\textbf{Testo:} Determina se le basi sono ortogonali e/o ortonormali (Prodotto scalare canonico).

\begin{enumerate}[label=\arabic*.]
    \item **Base:** $v_1=\binom{1}{0}, v_2=\binom{0}{1}, v_3=\binom{-2}{2}, v_4=\binom{0}{1}$ (Nota: Il testo sembra elencare vettori sparsi o basi di diversi spazi. Analizziamo i gruppi come nel manoscritto).
    
    \textbf{Analisi Gruppo 1 [da Manoscritto p.83]:}
    $v_1=\binom{1}{1}, v_2=\binom{1}{-1}, v_3=\binom{-1}{2}, v_4=\binom{0}{-1}$ (Vettori corretti dal manoscritto).
    \begin{itemize}
        \item $\langle v_1, v_2 \rangle = 1(1) + 1(-1) = 0$. (Ortogonali).
        \item $\langle v_1, v_4 \rangle = 1(0) + 1(-1) = -1 \neq 0$.
        \item \textbf{Conclusione:} Non sono una base ortogonale (non tutti ortogonali a coppie).
    \end{itemize}

    \item **Base:** $v_1=\binom{1/\sqrt{3}}{1/\sqrt{3}}{1/\sqrt{3}}, v_2=\binom{0}{1}{-1}, v_3=\binom{-2}{1}{1}$.
    \begin{itemize}
        \item $\langle v_1, v_2 \rangle = 0 + 1/\sqrt{3} - 1/\sqrt{3} = 0$.
        \item $\langle v_1, v_3 \rangle = -2/\sqrt{3} + 1/\sqrt{3} + 1/\sqrt{3} = 0$.
        \item $\langle v_2, v_3 \rangle = 0 + 1 - 1 = 0$.
        \item \textbf{Ortogonalità:} SÌ, è una base ortogonale.
        \item \textbf{Norme:}
        $||v_1||^2 = 1/3+1/3+1/3 = 1$. (Unitario)
        $||v_2||^2 = 0^2+1^2+(-1)^2 = 2 \implies ||v_2||=\sqrt{2} \neq 1$.
        \item \textbf{Conclusione:} Base Ortogonale ma \textbf{non} Ortonormale.
    \end{itemize}

    \item **Base:** $v_1=\binom{1/\sqrt{2}}{0}{1/\sqrt{2}}, v_2=\binom{0}{1}{0}, v_3=\binom{-1/\sqrt{2}}{0}{1/\sqrt{2}}$.
    \begin{itemize}
        \item I prodotti scalari misti sono tutti nulli.
        \item Le norme sono tutte 1.
        \item \textbf{Conclusione:} È una base \textbf{Ortonormale}.
    \end{itemize}
\end{enumerate}

\hrulefill

\section*{Esercizio (b) - Gram-Schmidt}
\textbf{Testo:} Ortogonalizzare la base di $\mathbb{R}^3$: $v_1=(0,2,2), v_2=(3,0,4), v_3=(0,1,-1)$.

\textbf{Svolgimento:}
(Nota: Il manoscritto a pag. 84 decide di riordinare i vettori per semplicità, partendo da quello con zeri o più semplice. Seguiamo l'algoritmo standard sui vettori dati o riordinati).
Poniamo $u_1, u_2, u_3$ la base ortogonale risultante.

\begin{enumerate}
    \item \textbf{Primo vettore:}
    $$ u_1 = v_1 = \binom{0}{2}{2} $$
    
    \item \textbf{Secondo vettore:}
    $$ u_2 = v_2 - \frac{\langle v_2, u_1 \rangle}{\langle u_1, u_1 \rangle} u_1 $$
    Calcoli:
    $\langle v_2, u_1 \rangle = 3(0) + 0(2) + 4(2) = 8$.
    $\langle u_1, u_1 \rangle = 0 + 4 + 4 = 8$.
    $$ u_2 = \binom{3}{0}{4} - \frac{8}{8} \binom{0}{2}{2} = \binom{3}{-2}{2} $$
    Verifica ortogonalità: $u_2 \cdot u_1 = 0 - 4 + 4 = 0$. OK.

    \item \textbf{Terzo vettore:}
    $$ u_3 = v_3 - \frac{\langle v_3, u_1 \rangle}{\langle u_1, u_1 \rangle} u_1 - \frac{\langle v_3, u_2 \rangle}{\langle u_2, u_2 \rangle} u_2 $$
    Calcoli:
    $\langle v_3, u_1 \rangle = 0(0) + 1(2) + (-1)(2) = 0$. (Questo semplifica molto!)
    $\langle v_3, u_2 \rangle = 0(3) + 1(-2) + (-1)(2) = -4$.
    $\langle u_2, u_2 \rangle = 9 + 4 + 4 = 17$.
    $$ u_3 = \binom{0}{1}{-1} - 0 \cdot u_1 - \frac{-4}{17} \binom{3}{-2}{2} = \binom{0}{1}{-1} + \binom{12/17}{-8/17}{8/17} $$
    $$ u_3 = \frac{1}{17} \binom{12}{9}{-9} $$
    (Possiamo moltiplicare per 17 per eliminare le frazioni, ottenendo $\binom{4}{3}{-3}$, che è ortogonale agli altri).
\end{enumerate}

\textbf{Base Ortogonale:} $\{ (0,2,2), (3,-2,2), (4,3,-3) \}$.
Per renderla \textbf{ortonormale}, dividere ogni vettore per la sua norma.

\hrulefill

\section*{Esercizio (c) - Complemento Ortogonale $U^\perp$}

\subsection*{Caso 1: $U = \text{Span}(v_1, v_2)$ in $\mathbb{R}^4$}
Dati $v_1 = (1,0,0,1)^T, v_2 = (0,1,-1,1)^T$.
Cerchiamo $x = (x,y,z,w)^T$ tale che $\langle x, v_1 \rangle = 0$ e $\langle x, v_2 \rangle = 0$.
$$ \begin{cases} x + w = 0 \\ y - z + w = 0 \end{cases} $$
Questo è il sistema cartesiano di $U^\perp$.
Risolvendo: $x=-w$, $y=z-w$. Variabili libere $z, w$.
$$ \binom{-w}{z-w}{z}{w} = z \binom{0}{1}{1}{0} + w \binom{-1}{-1}{0}{1} $$
\textbf{Base di $U^\perp$:} $\{ (0,1,1,0), (-1,-1,0,1) \}$. Dimensione 2.

\subsection*{Caso 2: $U$ definito da equazione $x-y+z=0$ in $\mathbb{R}^3$}
Il sottospazio $U$ è un piano passante per l'origine.
Il complemento ortogonale $U^\perp$ è la retta normale al piano.
I coefficienti dell'equazione cartesiana $(1, -1, 1)$ forniscono direttamente il generatore della normale.
\textbf{Base di $U^\perp$:} $\{ \binom{1}{-1}{1} \}$. Dimensione 1.

\subsection*{Caso 3: $U = \text{Ker}(T)$}
Se $U = \text{Ker}(T)$, allora $U^\perp = (\text{Ker } T)^\perp = \text{Im}(T^T)$ (nel caso di matrici reali con prodotto canonico, il complemento del nucleo è l'immagine della trasposta, ovvero lo spazio righe della matrice originale).
Procedimento:
1. Trova equazioni cartesiane del nucleo.
2. I vettori dei coefficienti di tali equazioni generano $U^\perp$.

\end{document}
```