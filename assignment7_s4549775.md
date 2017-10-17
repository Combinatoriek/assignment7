% Assignment 7\
	Group 4

---
author: Hendrik Werner
date: \today
fontsize: 12pt
geometry: margin=5em
header-includes:
	- \usepackage{tikz}
---

\begin{tikzpicture}[
	scale=1,
]
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
					\draw (\va\vb\vc\vd) -- (0\vb\vc\vd);
					\draw (\va\vb\vc\vd) -- (1\vb\vc\vd);
					\draw (\va\vb\vc\vd) -- (\va0\vc\vd);
					\draw (\va\vb\vc\vd) -- (\va1\vc\vd);
					\draw (\va\vb\vc\vd) -- (\va\vb0\vd);
					\draw (\va\vb\vc\vd) -- (\va\vb1\vd);
					\draw (\va\vb\vc\vd) -- (\va\vb\vc0);
					\draw (\va\vb\vc\vd) -- (\va\vb\vc1);
				}
			}
		}
	}

\end{tikzpicture}
