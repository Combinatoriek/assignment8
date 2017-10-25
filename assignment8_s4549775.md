% Assignment 8\
	Group 4

---
author: Hendrik Werner
date: \today
fontsize: 12pt
geometry: margin=5em
header-includes:
	- \usepackage{tikz}
	- \usetikzlibrary{positioning}
---

# 13

The graphs are not isomorphic, because one graph contains two adjacent vertices $u_3, u_4$ with $deg(u_3) = deg(u_4) = 4$, and the other one does not.

$deg(v_2) = deg(v_4) = 4$, but $\{v_2, v_3\} \not \in E$.

# 14
## d

# 15
## c
* $\kappa(G) = 2$

	vertex cut: $\{a, k\}$
* $\lambda(G) = 2$

	edge cut: $\{\{a, b\}, \{k, l\}\}$
* $min_{v \in V} deg(v) = 3$
* $\kappa(G) \leq \lambda(G) < min_{v \in V} deg(v)$

## d
* $\kappa(G) = 4$

	vertex cut: $\{b, c, d, f\}$
* $\lambda(G) = 4$

	edge cut: $\{\{a, d\}, \{a, b\}, \{a, c\}, \{a, f\}\}$
* $min_{v \in V} deg(v) = 4$
* $\kappa(G) \leq \lambda(G) \leq min_{v \in V} deg(v)$

# 16

There does not exist an Euler circuit, because $deg(a) \mod 2 = 1$. For an Euler path to exist $\forall v \in V deg(v) \mod 2 = 0$ must hold.

An Euler path does exists, because $deg(a), deg(d)$ are uneven, and all other vertices have an even degree. Euler paths exist if there are exactly two vertices of uneven degree. An Euler path is: $a, b, d, b, c, d, c, a, d$.

# 17

# 18

The graph does not contain subgraphs homeomorphic to $K_5$, or $K_{3, 3}$, so it is planar.

Planar representation:
\begin{tikzpicture}[
	every node/.style={circle, draw, minimum width=2em},
]
	\node (a) {a};
	\node[below=of a] (e) {e};
	\node[left=of e] (b) {b};
	\node[left=of b] (d) {d};
	\node[right=of e] (f) {f};
	\node[below=of e] (c) {c};
	\draw (a) -- (d);
	\draw (a) -- (f);
	\draw (b) -- (d);
	\draw (b) -- (e);
	\draw (c) -- (d);
	\draw (c) -- (e);
	\draw (c) -- (f);
\end{tikzpicture}

# 19

The given graph is homeomorphic to $K_{3, 3}$. By contracting the edges $\{a, b\}, \{c, d\}, \{e, f\}, \{g, h\}, \{i, j\}, \{k, l\}$ we get $K_{3, 3}$.

# 20

The chromatic number of the graph is $\chi(G) = 3$. $\chi(G) \geq 3$, because $b, c, g$ form a triangle. $\chi(G) \leq 3$, because I can give a coloring with 3 colors.

$\begin{aligned}
	color(a) &= w\\
	color(b) &= b\\
	color(c) &= w\\
	color(d) &= b\\
	color(e) &= w\\
	color(f) &= b\\
	color(g) &= r\\
\end{aligned}$

# 21
## a
## b

# 22
## a
## b
