% Assignment 7\
	Group 4

---
author: Hendrik Werner s4549775
date: \today
fontsize: 12pt
geometry: margin=5em
header-includes:
	- \usepackage{ifthen}
	- \usepackage{tikz}
---

# 12

# 13
We can follow the edges in their opposite direction, to get the answer that we need to execute $S_1, S_2, S_3, S_4$, before we can execute $S_6$.

# 14
## b
$K_{1, 8}$:
\begin{tikzpicture}
	\node at (4.5, 1) (m1) {$m_1$};
	\foreach \vx in {1, ..., 8} {
		\node at (\vx, 0) (n\vx) {$n_\vx$};
		\draw (n\vx) -- (m1);
	}
\end{tikzpicture}

## e
$W_7$:
\begin{tikzpicture}[
	every node/.style={fill=white},
]
	\node at (0: 0) (0) {0};
	\draw (0: 0) circle (6em);
	\foreach \vx in {1, ..., 7} {
		\node at (\vx * 360 / 7: 6em) (\vx) {\vx};
		\draw (0) -- (\vx);
	}
\end{tikzpicture}

## f
$Q_4$:
\begin{tikzpicture}
	\foreach \va in {0, 1} {
		\foreach \vb in {0, 1} {
			\foreach \vc in {0, 1} {
				\foreach \vd in {0, 1} {
					\node at (\va * 8 + \vb * 4 + \vd, \va * 2 + \vc * 4 + \vd) (\va\vb\vc\vd) {\va\vb\vc\vd};
					\ifthenelse{\va=1}{\draw (\va\vb\vc\vd) -- (0\vb\vc\vd);}{};
					\ifthenelse{\vb=1}{\draw (\va\vb\vc\vd) -- (\va0\vc\vd);}{};
					\ifthenelse{\vc=1}{\draw (\va\vb\vc\vd) -- (\va\vb0\vd);}{};
					\ifthenelse{\vd=1}{\draw (\va\vb\vc\vd) -- (\va\vb\vc0);}{};
				}
			}
		}
	}
\end{tikzpicture}

# 15
## a
$K_n$ is pipartite for $n \leq 2$, because above that you get triangles, which cannot be bipartite.

$K_1$:
\begin{tikzpicture}
	\node[circle, draw, fill=black] {};
\end{tikzpicture}

$K_2$:
\begin{tikzpicture}
	\node at (0, 0) (A) [circle, draw, fill=black] {};
	\node at (1, 0) (B) [circle, draw] {};
	\draw (A) -- (B);
\end{tikzpicture}

## b
$C_n$ is bipartite for $n = 1$, and $\{n \in \mathbb{N} |\ 2|n\}$. For even $n$ we can just alternate the node colors.

$C_1$:
\begin{tikzpicture}
	\node[circle, draw, fill=black] {};
\end{tikzpicture}

$C_n, 2|n$:
\begin{tikzpicture}[
	b/.style={circle, draw, fill=black},
	w/.style={circle, draw, fill=white},
]
	\draw (0: 0) circle (3em);
	\node at (0: 3em) [b] {};
	\node at (120: 3em) [w] {};
	\node at (240: 3em) [circle, fill=white] {\dots};
\end{tikzpicture}

## c
$W_n$ can not be bipartite, as is only defined for $n \geq 3$, so the smallest wheel graph is $W_3$. This graph already contain triangles, as do all $W_n$, so none of them are bipartite.

$W_3$:
\begin{tikzpicture}[
	b/.style={circle, draw, fill=black},
	w/.style={circle, draw, fill=white},
]
	\draw (0: 0) circle (3em);
	\node at (0: 0) (Center) [b] {};
	\foreach \vx in {1, ..., 3} {
		\node at (\vx * 360 / 3: 3em) (\vx) [w] {};
		\draw (Center) -- (\vx);
	}
\end{tikzpicture}

## d
$Q_n$ is bipartite for every $n$.

# 16
## a
## b

# 17
## a
## b
## c
## d
## e
## f
## g
## h

# 18

# 19
## a
* The graph is planar.
* The number of edges is 13.
* The in-degree of b is 1.
* The out-degree of b is 3.

## b
## c
## d
* The edges are directed, because $(f, c) \in E, (c, f) \not \in E$.
* Multiple edges are allowed, because, for example there are two edges $(b, a)$.
* Loops are allowed because $(f, f) \in E$.
