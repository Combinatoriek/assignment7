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
We are given these definitions:

* $u R v \leftrightarrow \{u, v\} \in E$
* There is a loop at every vertex: $\forall v \in V. \{v, v\} \in E$

From these facts, we can derive that the relation is reflexive: $\forall v \in V. v R v$.

1. Assume $u R v$.
2. From (1) we know, that by the definition of $R$: $\{u, v\} \in E$.
3. Because the edges are undirected, $\{u, v\} = \{v, u\}$, so $\{v, u\} \in E$.
4. From (3) we know, that $v R u$.
5. From (1) and (4) we know, that the relation $R$ is symmetric: $\forall v_1, v_2 \in V. v_1 R v_2 \leftrightarrow v_2 R v_1$.

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
$G = (\{a, b, c, f\}, \{\{a, b\}, \{a, f\}, \{b, c\}, \{b, f\}\})$

\begin{tikzpicture}[
	scale=2,
]
	\node at (0, 1) (a) {a};
	\node at (1, 1) (b) {b};
	\node at (2, 1) (c) {c};
	\node at (0, 0) (f) {f};
	\draw (a) -- (b);
	\draw (a) -- (f);
	\draw (b) -- (c);
	\draw (b) -- (f);
\end{tikzpicture}

## b
\begin{tikzpicture}[
	scale=2,
]
	\node at (0, 1) (a) {a};
	\node at (1, 1) (w) {w};
	\node at (2, 1) (c) {c};
	\node at (1, 0) (e) {e};
	\node at (2, 0) (d) {d};
	\draw (a) -- (w);
	\draw (c) -- (w);
	\draw (e) -- (w);
\end{tikzpicture}

# 17
## a
According to the Handshaking Theorem, the degree of a graph is divisible by 2. $2 \not | 15$, so this degree sequence is not graphic.

## e
\begin{tikzpicture}[
	every node/.style={circle, draw, fill=white},
]
	\draw (0: 0) circle (6em);
	\foreach \vx in {1, ..., 6} {
		\node at (\vx * 360 / 6: 6em) (\vx) {};
	}
	\draw (1) -- (3);
\end{tikzpicture}

## f
\begin{tikzpicture}[
	every node/.style={circle, draw},
]
	\foreach \vx in {1, ..., 3} {
		\node at (\vx, 0) (\vx0) {};
		\node at (\vx, 1) (\vx1) {};
		\draw (\vx0) -- (\vx1);
	}
\end{tikzpicture}

# 18
1. In an $n$-regular graph, each node has degree $n$.
2. From (1): We want to increase the degree of a node in $V_1$, so we need to increase the degrees of every other node in $V_1$ as well.
3. Nodes in $V_1$ cannot be connected to other nodes in $V_1$, so they need to be connected to nodes in $V_2$.
4. From (1), (2), and (3): We know that $|V_2| \geq |V_1|$, because we cannot connect more edges to one node in $V_2$, compared to any other node in $V_2$.
5. Assume that $|V_2| > |V_1|$.
6. From (2), and (5): There is some node in $V_2$, that has less edges than every node in $V_1$.
7. From (6): The assumption (5) must be wrong, so $|V_2| \leq |V_1|$.
8. From (4), and (7): $|V_1| = |V_2|$.

# 19
## a
* The graph is planar.
* The number of edges is 13.
* The in-degree of b is 1.
* The out-degree of b is 3.

## b
$W_3$ is the only wheel graph that is complete. Wheel graphs are generated by taking a cycle graph, and adding a new node, which is connected to every other node. In a cycle graph $C_n$, each of the $n$ nodes has degree 2. By adding a new edge, we increase their degree to 3.

For a graph to be complete, the degree of every node must be $|V| - 1$. $W_3$, which has 4 nodes, is the only graph for which this is true:

$W_3 = \begin{bmatrix}
	0 & 1 & 1 & 1\\
	1 & 0 & 1 & 1\\
	1 & 1 & 0 & 1\\
	1 & 1 & 1 & 0\\
\end{bmatrix}$

## c
From the Handshaking Theorem we know that $2e$ is the sum of the degrees of all vertices in $G$. That means that $\frac{2e}{v}$ is the average degree of the vertices.

The average is always at most the maximum, so $\frac{2e}{v} \leq M$.

## d
* The edges are directed, because $(f, c) \in E, (c, f) \not \in E$.
* Multiple edges are allowed, because, for example there are two edges $(b, a)$.
* Loops are allowed because $(f, f) \in E$.
