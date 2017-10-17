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
