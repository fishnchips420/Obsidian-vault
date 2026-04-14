\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[italian]{babel}
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{geometry}
\geometry{a4paper, margin=2cm}

\title{Trascrizione Appunti di Algebra Lineare}
\author{Esercizi Completi}
\date{}

\begin{document}

\maketitle

\section*{Pagina 1: Prima Scheda Esercizi - Sottospazi Vettoriali}

\subsection*{Esercizio 1}
Dato $V = \mathbb{R}^2$ e $W = \left\{ \begin{pmatrix} x \\ y \end{pmatrix} : x \ge 0, y \ge 0, x,y \in \mathbb{R} \right\}$.

\textbf{Proprietà 1 (Chiusura rispetto alla somma):} \\
Siano $w_1 = \begin{pmatrix} x_1 \\ y_1 \end{pmatrix}$ e $w_2 = \begin{pmatrix} x_2 \\ y_2 \end{pmatrix}$ con $x_i, y_i \ge 0$. \\
$w_1 + w_2 = \begin{pmatrix} x_1 + x_2 \\ y_1 + y_2 \end{pmatrix}$. Poiché la somma di numeri positivi è positiva, $w_1 + w_2 \in W$.

\textbf{Proprietà 2 (Chiusura rispetto al prodotto per scalare):} \\
Sia $w_1 = \begin{pmatrix} x_1 \\ y_1 \end{pmatrix} \in W$ e $\lambda \in \mathbb{R}$. \\
Se $\lambda < 0$, allora $\lambda w_1 = \begin{pmatrix} \lambda x_1 \\ \lambda y_1 \end{pmatrix}$ avrà componenti negative. \\
\textbf{Conclusione:} $W$ non è un sottospazio vettoriale perché non è chiuso rispetto al prodotto per scalare negativo.

\subsection*{Esercizio 2}
$V = \mathbb{R}^2$, $J = \left\{ \begin{pmatrix} x \\ y \end{pmatrix} : xy = 0, x,y \in \mathbb{R} \right\}$. \\
La condizione $xy=0$ implica $x=0$ oppure $y=0$ (l'insieme è l'unione degli assi cartesiani).

\textbf{Verifica somma:} \\
Prendiamo $w_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \in J$ e $w_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \in J$. \\
$w_1 + w_2 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$. \\
Verifichiamo la condizione: $1 \cdot 1 = 1 \neq 0$. Quindi il vettore somma $\notin J$. \\
\textbf{Conclusione:} Non è un sottospazio vettoriale.

\subsection*{Esercizio d1}
$V = \mathbb{R}^3$; $W = \left\{ \begin{pmatrix} a \\ a+1 \\ 2a \end{pmatrix} : a \in \mathbb{R} \right\}$.

\textbf{Verifica vettore nullo:} \\
Per avere il vettore nullo $\begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$, dovremmo avere:
$\begin{cases} a = 0 \\ a+1 = 0 \implies a = -1 \\ 2a = 0 \end{cases}$ \\
Il sistema è impossibile. Il vettore nullo non appartiene a $W$. \\
\textbf{Conclusione:} Non è un sottospazio.

\subsection*{Esercizio d2}
$V = \mathbb{R}^3$; $W = \left\{ \begin{pmatrix} 2\lambda \\ \lambda + \mu \\ 2\mu \end{pmatrix} : \lambda, \mu \in \mathbb{R} \right\}$.

\textbf{Verifica Somma (P1):} \\
$w_1 = \begin{pmatrix} 2\lambda_1 \\ \lambda_1 + \mu_1 \\ 2\mu_1 \end{pmatrix}, w_2 = \begin{pmatrix} 2\lambda_2 \\ \lambda_2 + \mu_2 \\ 2\mu_2 \end{pmatrix} \implies w_1+w_2 = \begin{pmatrix} 2(\lambda_1+\lambda_2) \\ (\lambda_1+\lambda_2) + (\mu_1+\mu_2) \\ 2(\mu_1+\mu_2) \end{pmatrix} \in W$.

\textbf{Verifica Prodotto (P2):} \\
$k w_1 = \begin{pmatrix} 2(k\lambda_1) \\ (k\lambda_1) + (k\mu_1) \\ 2(k\mu_1) \end{pmatrix} \in W$. \\
\textbf{Conclusione:} È un sottospazio vettoriale.

\newpage

\section*{Pagina 2: Altri Esercizi sui Sottospazi}

\subsection*{Esercizio d3}
$V = \mathbb{R}^2$, $W = \left\{ \begin{pmatrix} x \\ x^2 \end{pmatrix} : x \in \mathbb{R} \right\}$ (Parabola).

\textbf{Verifica Somma:} \\
$w_1 = \begin{pmatrix} x_1 \\ x_1^2 \end{pmatrix}, w_2 = \begin{pmatrix} x_2 \\ x_2^2 \end{pmatrix}$. \\
$w_1 + w_2 = \begin{pmatrix} x_1+x_2 \\ x_1^2+x_2^2 \end{pmatrix}$. \\
Affinché appartenga a $W$, la seconda componente dovrebbe essere il quadrato della prima: $(x_1+x_2)^2$. \\
Ma $(x_1+x_2)^2 = x_1^2 + x_2^2 + 2x_1x_2 \neq x_1^2 + x_2^2$ (a meno che $x_1$ o $x_2$ siano 0). \\
\textbf{Conclusione:} Non è chiuso rispetto alla somma, non è un sottospazio.

\subsection*{Esercizio d4}
$V = M_{2,2}(\mathbb{R})$; $W = \left\{ \begin{pmatrix} 2\alpha & 2\beta \\ 3\beta & 3\alpha \end{pmatrix} : \alpha, \beta \in \mathbb{R} \right\}$.

Verificando somma e prodotto per scalare, si nota che la struttura si conserva. \\
Ad esempio per la somma: le componenti corrispondenti si sommano e si possono raccogliere i coefficienti 2 e 3. \\
\textbf{Conclusione:} È un sottospazio vettoriale.

\subsection*{Esercizio d5}
$V = \mathbb{R}_3[t]$; $W = \{ 2at + 3b : a, b \in \mathbb{R} \}$. \\
Polinomi di grado $\le 1$. La somma di polinomi di grado 1 è ancora di grado 1 (o 0). \\
\textbf{Conclusione:} È un sottospazio.

\subsection*{Esercizio d6}
$V = \mathbb{R}_2[t]$; $W = \{ at^2 - 1 : a \in \mathbb{R} \}$. \\
Il vettore nullo ($0t^2 + 0t + 0$) appartiene a $W$? \\
$at^2 - 1 = 0 \implies -1 = 0$ impossibile. \\
\textbf{Conclusione:} Non contiene lo zero, non è un sottospazio.

\subsection*{Esercizio d7}
$V = M_{2,3}(\mathbb{R})$; $W = \left\{ \begin{pmatrix} 0 & a & b \\ 0 & 0 & c \end{pmatrix} : a, b, c \in \mathbb{R} \right\}$. \\
Somma e prodotto mantengono gli zeri nelle posizioni fisse. \\
\textbf{Conclusione:} È un sottospazio.

\subsection*{Esercizio d8}
$V = \mathbb{R}^2$; $W = \left\{ \begin{pmatrix} x \\ y \end{pmatrix} : x^2 + y^2 = 1 \right\}$ (Circonferenza unitaria). \\
Il vettore nullo $\begin{pmatrix} 0 \\ 0 \end{pmatrix}$ non soddisfa $0^2+0^2=1$. \\
\textbf{Conclusione:} Non è un sottospazio.

\newpage

\section*{Pagina 3: Continuazione Sottospazi e Combinazioni Lineari}

\subsection*{Esercizio d9}
$V = \mathbb{R}^2$; $W = \left\{ \begin{pmatrix} x \\ y \end{pmatrix} : x^2 - y^2 = 0 \right\}$. \\
$x^2 - y^2 = 0 \implies (x-y)(x+y) = 0 \implies y=x \cup y=-x$. \\
È l'unione delle due bisettrici.

\textbf{Verifica Somma:} \\
Prendiamo $w_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix} \in W$ (sta sulla retta $y=x$) e $w_2 = \begin{pmatrix} 1 \\ -1 \end{pmatrix} \in W$ (sta sulla retta $y=-x$). \\
$w_1 + w_2 = \begin{pmatrix} 2 \\ 0 \end{pmatrix}$. \\
Sostituiamo nella condizione iniziale: $(2)^2 - (0)^2 = 4 \neq 0$. \\
\textbf{Conclusione:} Non è un sottospazio (non chiuso rispetto alla somma).

\section*{Combinazione Lineare}

Dati $v_1, v_2, \dots, v_k$ vettori di $V$ e $\lambda_1, \lambda_2, \dots, \lambda_k \in \mathbb{R}$ scalari. \\
Si definisce \textbf{Combinazione Lineare} il vettore:
$$ v = \lambda_1 v_1 + \lambda_2 v_2 + \dots + \lambda_k v_k = \sum_{i=1}^{k} \lambda_i v_i $$

\textbf{Esempio in $\mathbb{R}^2$:} \\
$v = 2x_1 + \frac{1}{2}x_2$ (Regola del parallelogramma per la somma vettoriale).

\newpage

\section*{Pagina 4: Seconda Scheda Esercizi - Indipendenza Lineare}

Stabilire se i seguenti vettori dello spazio $V$ sono linearmente indipendenti o dipendenti.

\subsection*{Esercizio 2.1}
$V = \mathbb{R}^2$; $w_1 = \begin{pmatrix} 5 \\ 6 \end{pmatrix}, w_2 = \begin{pmatrix} -15 \\ -18 \end{pmatrix}$. \\
Si nota che $w_2 = -3 \cdot w_1$. \\
\textbf{Risposta:} Sono linearmente \textbf{DIPENDENTI} perché proporzionali.

\subsection*{Esercizio 2.2}
$V = \mathbb{R}^3$; $v_1=\begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}, v_2=\begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}, v_3=\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}$. \\
Impostiamo la combinazione lineare uguale a zero: $\alpha v_1 + \beta v_2 + \gamma v_3 = \vec{0}$.
$$ \begin{cases} \alpha + \gamma = 0 \\ \beta + \gamma = 0 \\ \alpha + \beta = 0 \end{cases} \implies \begin{cases} \alpha = -\gamma \\ \beta = -\gamma \\ -\gamma - \gamma = 0 \implies \gamma = 0 \end{cases} \implies \alpha=\beta=\gamma=0 $$
\textbf{Risposta:} I vettori sono linearmente \textbf{INDIPENDENTI}.

\subsection*{Esercizio 2.3}
$V = \mathbb{R}^3$; $v_1=\begin{pmatrix} 2 \\ 3 \\ 4 \end{pmatrix}, v_2=\begin{pmatrix} 1/2 \\ 0 \\ 1 \end{pmatrix}, v_3=\begin{pmatrix} \sqrt{2} \\ -\sqrt{2} \\ 2\sqrt{2} \end{pmatrix}$. \\
Dal calcolo del sistema, se si trovano coefficienti non nulli, sono dipendenti. (L'appunto suggerisce calcoli complessi con radicali, ma verifica la dipendenza).

\subsection*{Esercizio 2.4}
$V = M_{2,2}(\mathbb{R})$; $v_1=\begin{pmatrix} 1 & 1 \\ 0 & 0 \end{pmatrix}, v_2=\begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix}, v_3=\begin{pmatrix} 0 & 0 \\ 4 & 0 \end{pmatrix}$. \\
Combinazione lineare:
$\begin{cases} \alpha + \beta = 0 \\ \alpha = 0 \\ \beta + 4\gamma = 0 \\ \beta = 0 \end{cases} \implies \alpha=0, \beta=0, \gamma=0$. \\
\textbf{Risposta:} Linearmente \textbf{INDIPENDENTI}.

\subsection*{Esercizio R5}
$V = \mathbb{R}_2[t]$; $p_1 = t+1, p_2 = 3t^2-5, p_3 = 2t+2$. \\
Osserviamo che $p_3 = 2(t+1) = 2p_1$. \\
\textbf{Risposta:} Sono linearmente \textbf{DIPENDENTI} (uno è multiplo dell'altro).

\subsection*{Esercizio R6}
$V = \mathbb{R}_2[t]$; $v_1=t^2-3, v_2=5t-1, v_3=t^2+t$. \\
$\alpha(t^2-3) + \beta(5t-1) + \gamma(t^2+t) = 0$. \\
Sistema sui coefficienti:
$\begin{cases} \alpha + \gamma = 0 \quad (\text{coeff } t^2) \\ 5\beta + \gamma = 0 \quad (\text{coeff } t) \\ -3\alpha - \beta = 0 \quad (\text{termine noto}) \end{cases} \implies \alpha=0, \beta=0, \gamma=0$. \\
\textbf{Risposta:} Linearmente \textbf{INDIPENDENTI}.

\newpage

\section*{Pagina 5: Sottoinsiemi Massimali e Basi}

Determinare i sottoinsiemi massimali di vettori linearmente indipendenti dell'insieme A.

\subsection*{Esercizio}
$V = \mathbb{R}^3$. Insieme $A = \{ v_1, v_2, v_3, v_4 \}$. \\
$v_1 = \begin{pmatrix} 1 \\ 0 \\ 4 \end{pmatrix}, v_2 = \begin{pmatrix} -1 \\ -1 \\ 0 \end{pmatrix}, v_3 = \begin{pmatrix} 0 \\ 1 \\ -4 \end{pmatrix}, v_4 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$.

Verifichiamo se $v_1, v_2, v_3$ sono dipendenti:
$v_1 + v_2 + v_3 = \begin{pmatrix} 1-1+0 \\ 0-1+1 \\ 4+0-4 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$. \\
Quindi $v_1 + v_2 + v_3 = 0$. I vettori sono dipendenti. Possiamo scartarne uno (es. $v_1$) per avere un insieme indipendente.
Aggiungendo $v_4$:
Se prendiamo $\{v_2, v_3, v_4\}$, verifichiamo l'indipendenza tramite sistema.
$$ \alpha v_2 + \beta v_3 + \gamma v_4 = 0 \implies \begin{cases} -\alpha = 0 \\ -\alpha + \beta = 0 \\ -4\beta + \gamma = 0 \end{cases} \implies \alpha=0, \beta=0, \gamma=0 $$
Quindi un sottoinsieme massimale è $B = \{v_2, v_3, v_4\}$.
Analogamente, scartando $v_2$, otteniamo $G = \{v_1, v_3, v_4\}$.

\subsection*{Esercizio b2}
$V = \mathbb{R}^2$. Insieme di vettori: $\begin{pmatrix} 1 \\ 2 \end{pmatrix}, \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \begin{pmatrix} 2 \\ 2 \end{pmatrix}$.

1. Prendiamo i primi due: $\begin{pmatrix} 1 \\ 2 \end{pmatrix}$ e $\begin{pmatrix} 2 \\ 1 \end{pmatrix}$.
Sono lin. ind? Sì, non sono proporzionali. $A = \{v_1, v_2\}$.

2. Consideriamo $\begin{pmatrix} 1 \\ 1 \end{pmatrix}$ e $\begin{pmatrix} 2 \\ 2 \end{pmatrix}$.
Sono proporzionali ($v_4 = 2v_3$). Quindi non possono stare insieme in una base.

Combinazioni possibili di vettori indipendenti (Basi di $\mathbb{R}^2$):
\begin{itemize}
    \item $A = \{v_1, v_2\}$
    \item $B = \{v_1, v_3\}$
    \item $C = \{v_2, v_4\}$
    \item $D = \{v_2, v_3\}$
    \item $E = \{v_1, v_4\}$ (Verifica: $\det \begin{pmatrix} 1 & 2 \\ 2 & 2 \end{pmatrix} = 2-4 \ne 0 \implies$ Indipendenti).
\end{itemize}

\end{document}