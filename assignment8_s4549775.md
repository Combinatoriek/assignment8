% Assignment 8\
	Group 4

---
author: Hendrik Werner s4549775
date: \today
fontsize: 12pt
geometry: margin=5em
header-includes:
	- \usepackage{tikz}
	- \usetikzlibrary{positioning}
	- \usetikzlibrary{shapes}
---

# 13

The graphs are not isomorphic, because one graph contains two adjacent vertices $u_3, u_4$ with $deg(u_3) = deg(u_4) = 4$, and the other one does not.

$deg(v_2) = deg(v_4) = 4$, but $\{v_2, v_3\} \not \in E$.

# 14
## d
The adjacency matrix for $K_4$ looks like this:
$A_{K_4} = \begin{bmatrix}
	0 & 1 & 1 & 1\\
	1 & 0 & 1 & 1\\
	1 & 1 & 0 & 1\\
	1 & 1 & 1 & 0\\
\end{bmatrix}$

If we want to know the paths between vertices of length 5, we need to calculate $A^5_{K_4}$.

$A^5_{K_4} = \begin{bmatrix}
	60 & 61 & 61 & 61\\
	61 & 60 & 61 & 61\\
	61 & 61 & 60 & 61\\
	61 & 61 & 61 & 60\\
\end{bmatrix}$

There are 61 paths of length 5 between every two different vertices in $K_4$.

# 15
## c
* $\kappa(G) = 2$

	vertex cut: $\{a, k\}$
* $\lambda(G) = 2$

	edge cut: $\{\{a, b\}, \{k, l\}\}$
* $min_{v \in V} deg(v) = 3$

	$deg(a) = 3$
* $\kappa(G) \leq \lambda(G) < min_{v \in V} deg(v)$

## d
* $\kappa(G) = 4$

	vertex cut: $\{b, c, d, f\}$
* $\lambda(G) = 4$

	edge cut: $\{\{a, d\}, \{a, b\}, \{a, c\}, \{a, f\}\}$
* $min_{v \in V} deg(v) = 4$

	$deg(a) = 4$
* $\kappa(G) \leq \lambda(G) \leq min_{v \in V} deg(v)$

# 16

There does not exist an Euler circuit, because $deg(a) \mod 2 = 1$. For an Euler path to exist $\forall v \in V deg(v) \mod 2 = 0$ must hold.

An Euler path does exists, because $deg(a), deg(d)$ are uneven, and all other vertices have an even degree. Euler paths exist if there are exactly two vertices of uneven degree. An Euler path is: $a, b, d, b, c, d, c, a, d$.

# 17

For $n = 4$ such a graph does not exist, according to Dirac's theorem. For $n = 5$ we can construct a graph.

\begin{tikzpicture}[
	scale=2,
	every node/.style={circle, draw},
]
	\node at (1, 1) (0) {0};
	\node at (0, 2) (1) {1};
	\node at (2, 2) (2) {2};
	\node at (0, 0) (3) {3};
	\node at (2, 0) (4) {4};
	\draw (0) -- (1);
	\draw (0) -- (2);
	\draw (0) -- (3);
	\draw (0) -- (4);
	\draw (1) -- (3);
	\draw (2) -- (4);
\end{tikzpicture}

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

The given graph is homeomorphic to $K_{3, 3}$. It can be constructed by adding the elementary subdivisions $\{b, d, f, h, j, l\}$ to $K_{3, 3}$.

The partitions are $\{\{a, e, i\}, \{c, g, k\}\}$.

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
$\chi(G) \geq 4$, because the subgraph induced by the vertices $\{b, c, h, i\}$ is $K_4$. $\chi(G) \leq 4$, as we can make a coloring with 4 colors. So $\chi(G) = 4$. If we want to reduce this number, we need to remove one of $\{b, c, h, i\}$, as they induce $K_4$, for which $\chi(K_4) = 4$.

\begin{tikzpicture}[
	scale=2,
	every node/.style={draw},
	b/.style={star},
	d/.style={circle},
	f/.style={circle},
	g/.style={diamond},
	h/.style={circle},
	i/.style={diamond},
]
	\foreach[count=\vi] \vx in {a, ..., i} {
		\node[\vx/.try] at (\vi * 360 / 9: 1) (\vx) {\vx};
	}
	\draw (a) -- (b);
	\draw (a) -- (g);
	\draw (a) -- (h);
	\draw (a) -- (i);
	\draw (b) -- (c);
	\draw (b) -- (h);
	\draw (b) -- (i);
	\draw (c) -- (d);
	\draw (c) -- (f);
	\draw (c) -- (g);
	\draw (c) -- (h);
	\draw (c) -- (i);
	\draw (d) -- (e);
	\draw (d) -- (g);
	\draw (d) -- (i);
	\draw (e) -- (f);
	\draw (e) -- (i);
	\draw (f) -- (g);
	\draw (g) -- (h);
	\draw (h) -- (i);
\end{tikzpicture}

As is evident from the coloring given, by removing $b$, $\chi(G)$ is reduced to 3.

## b
We cannot reduce the chromatic number by removing a single vertex. The graph contains 5 triangles, and by removing any edge, we can only remove a single triangle, so $\chi(G) \geq 3$. I can give a coloring with 3 colors, so $\chi(G) \leq 3$. $\chi(G) = 3$

$\begin{aligned}
	color(a) &= b &
	color(b) &= r\\
	color(c) &= w &
	color(d) &= w\\
	color(e) &= r &
	color(f) &= b\\
	color(g) &= w &
	color(h) &= r\\
	color(i) &= b &
	color(j) &= b\\
	color(k) &= r &
	color(l) &= w\\
	color(m) &= w &
	color(n) &= r\\
	color(o) &= b &
\end{aligned}$

# 22
## a
A nonplanar graph contains a subgraph homeomorphic to $K_5$, or $K_{3, 3}$. Because $\lambda(K_5) \neq 1$, and $\lambda(K_{3, 3}) \neq 1$, we need to add a vertex, so we start with $K_5$, which is smaller, because we want $|V|$ to be minimal. We add one vertex, connected to one other vertex, so $\lambda(G) = 1$:

G:
\begin{tikzpicture}[
	every node/.style={circle, draw},
]
	\foreach \vx in {1, ..., 5} {
		\node at (\vx * 360 / 5: 1) (\vx) {};
	}
	\foreach \vx in {1, ..., 5} {
		\foreach \vy  in {\vx, ..., 5} {
			\draw (\vx) -- (\vy);
		}
	}
	\node at (1: 2) (0) {};
	\draw (0) -- (5);
\end{tikzpicture}

## b
$\chi(H) \geq 4$, because $H$ contains the subgraph $K_4$.

$\chi(G) \leq 4$, because the graph is planar.

Putting these facts together we get that $\chi(G) = 4$.
