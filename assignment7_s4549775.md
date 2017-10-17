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
					\node at (\va * 7 + \vb * 4 + \vd, \vc * 4 + \vd) (\va\vb\vc\vd) {\va\vb\vc\vd};
				}
			}
		}
	}
\end{tikzpicture}
