% Assignment 7\
	Group 4

---
author: Hendrik Werner
date: \today
fontsize: 12pt
geometry: margin=5em
header-includes:
	- \usepackage{tikz}
	- \usetikzlibrary{calc}
---

# 12

# 13

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
				}
			}
		}
	}
	\foreach \va in {0, 1} {
		\foreach \vb in {0, 1} {
			\foreach \vc in {0, 1} {
				\foreach \vd in {0, 1} {
                    \draw let \n1={\va==0?1:0} in (\va\vb\vc\vd) -- (\n1\vb\vc\vd);
                    \draw let \n1={\vb==0?1:0} in (\va\vb\vc\vd) -- (\va\n1\vc\vd);
                    \draw let \n1={\vc==0?1:0} in (\va\vb\vc\vd) -- (\va\vb\n1\vd);
                    \draw let \n1={\vd==0?1:0} in (\va\vb\vc\vd) -- (\va\vb\vc\n1);
				}
			}
		}
	}
\end{tikzpicture}

# 15
## a
## b
## c
## d

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
## b
## c
## d
