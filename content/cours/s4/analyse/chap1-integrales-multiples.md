---
title: "Chapitre 1: Intégrales multiples"
date: 2023-02-12T11:07:09+01:00
mathjax: true
draft: false
---

## Integrales doubles


---
## TD n°2 - Integrales doubles: Changements de variable

### Exercice 1

> Soit l'intégrale double
> $$
> I = \iint_D \sin({y \over x}) \space \text{d}y \space \text{d}x
> $$
> avec {{< texi `D = \{ (x, y) \in \mathbb{R}^2 \space | \space x \leq y \leq 2x \space ; \space 1 \leq x \leq 2 \}` >}}

1. Tracer le domaine {{< texi `D` >}} et calculer {{< texi `I`>}}.
2. Calculer {{< texi `I`>}} par le changement de variables suivant {{< texi `\begin{cases}
    u = x \\
    v = { y \over x }
\end{cases}` >}}

---
{data-content = " solution "}

> 1. Tracer le domaine {{< texi `D` >}} et calculer {{< texi `I`>}}.

On a le tracé suivant :

{{< figure 
    src="/imgs/s4/analyse/chap1_td2_exo1_q1_ggbra.png?h=400"
    alt="alt-test"
    caption="La zone bleu est le domaine D"
    >}}

Et pour calculer {{< texi `I`>}} :
$$
I = \int_1^2 \bigg( \int_{x}^{2x} \sin({y \over x}) \space \text{d}y \bigg) \space \text{d}x
$$

Pour la {{< texi `\text{1}^\text{ère}`>}} intégrale :
$$
\begin{split}
\int_{x}^{2x} \sin({y \over x}) \space \text{d}y \qquad &
= \bigg[ -x \cos({y \over x}) \bigg]_x^{2x} \newline
\newline
& = x (\cos(1) - \cos(2))
\end{split}
$$

Et pour la {{< texi `\text{2}^\text{ème}`>}} :
$$
\begin{split}
\int_1^2 x (\cos(1) - \cos(2)) \space \text{d}x \qquad &
= (\cos(1) - \cos(2)) \int_1^2 x \space \text{d}x \newline
& = (\cos(1) - \cos(2)) \bigg[ {x^2 \over 2} \bigg]_1^2 \newline \newline
& = {3 \over 2}(\cos(1) - \cos(2))
\end{split}
$$

> 2. Calculer {{< texi `I`>}} par le changement de variables suivant : {{< texi `\begin{cases}
    u = x \\
    v = { y \over x }
\end{cases}` >}}

Pour le calcul du jacobien, on a : {{< texi `\begin{cases}
    u = x \\
    v = { y \over x }
\end{cases}` >}} et donc {{< texi `\begin{cases}
    x = u \\
    y = uv
\end{cases}` >}}

Le calcul :
$$
\begin{split}
& I = \int_1^2 \bigg( \int_{x}^{2x} \sin({y \over x}) \space \text{d}y \bigg) \space \text{d}x
= \int_1^2 \bigg( \int_{u}^{2u} \sin(v) \left|J_\Phi(u,v)\right| \space \text{d}v \bigg) \space \text{d}u \newline \newline
& J_\Phi(u,v) = \begin{vmatrix}
  {{\partial x} \over {\partial u}} & {{\partial x} \over {\partial v}} \newline
  {{\partial y} \over {\partial u}} & {{\partial y} \over {\partial v}}
 \end{vmatrix}
= \begin{vmatrix}
  1 & 0 \newline
  0 & u
 \end{vmatrix}
= u
\end{split}
$$

$$
\begin{split}
\text{donc } I = \int_1^2 \bigg( \int_{1}^{2} \sin(v) u \space \text{d}v \bigg) \space \text{d}u \newline
\end{split}
$$

Pour la {{< texi `\text{1}^\text{ère}`>}} intégrale :
$$
\begin{split}
\int_{1}^{2} \sin(v) u \space \text{d}v 
= u\int_{1}^{2} \sin(v) \space \text{d}v \newline
= u\bigg[ -\cos(v) \bigg]_1^{2} = u (\cos(1) - \cos(2))
\end{split}
$$

Et pour la {{< texi `\text{2}^\text{ème}`>}} :
$$
\begin{split}
I = \int_1^2 u (\cos(1) - \cos(2)) \space \text{d}u \qquad
& = (\cos(1) - \cos(2)) \int_1^2 u \space \text{d}u \newline
& = (\cos(1) - \cos(2)) \bigg[ {u^2 \over 2} \bigg]_1^2 \newline \newline
& = {3 \over 2}(\cos(1) - \cos(2))
\end{split}
$$

### Exercice 3

> Calculer {{< texi `\iint_D f(x,y) \space \text{d}x \space \text{d}y` >}}  dans les cas suivants :
1. {{< texi `D = \{ (x, y) \in \mathbb{R}^2 \space ; \space x \geq 0\space , \space y \geq 0 \space , \space 1 \leq x^2 + y^2 \leq 4 \}`>}} et {{< texi `f(x,y)={ {xy} \over {x^2 + y^2} }`>}}
2. {{< texi `D = \{ (x, y) \in \mathbb{R}^2 \space ; \space x \geq 0\space , \space  1 \leq x^2 + y^2 \leq 2y \}`>}} et {{< texi `f(x,y)=\sqrt{x^2 + y^2}`>}}

---
{data-content = " solution "}

1. On passe en polaire. Le domaine D est entre un quart des deux cercles (le premier a pour rayon 2 et l'autre 1). 
$$
\begin{split}
x & = \rho\cos(\theta) \newline
y & = \rho\sin(\theta)
\newline \newline
f(\rho\cos(\theta), \rho\sin(\theta)) & = { {\rho^2\sin(\theta)\cos(\theta)} \over {\rho^2} } = \sin(\theta)\cos(\theta)
\newline \newline \newline \newline
I & = \int_0^{\pi \over 2} \int_1^2 \sin(\theta)\cos(\theta)\rho \space \text{d}\rho \space \text{d}\theta
\end{split}
$$

Pour la {{< texi `\text{1}^\text{ère}`>}} intégrale :
$$
\begin{split}
\int_1^2 \sin(\theta)\cos(\theta)\rho \space \text{d}\rho \space
& = \sin(\theta)\cos(\theta) \int_1^2 \rho\space \text{d}\rho \newline
& = \sin(\theta)\cos(\theta) \bigg[ {\rho^2 \over 2} \bigg]_1^2 = \sin(\theta)\cos(\theta) ({4\over 2} - {1\over 2}) \newline 
& = {3\over 2}\sin(\theta)\cos(\theta) 
\end{split}
$$

Et pour la {{< texi `\text{2}^\text{ème}`>}} :
$$
\begin{split}
I = \int_0^{\pi \over 2} {3\over 2}\sin(\theta)\cos(\theta)  \space \text{d}\theta \qquad
& = {3\over 2}\int_0^{\pi \over 2} \sin(\theta)\cos(\theta)  \space \text{d}\theta \newline
& = {3\over 2} \bigg[ {\sin(\theta)^2 \over 2} \bigg]_0^{\pi \over 2} \newline \newline
& = {3 \over 2}({\sin({\pi \over 2})\over 2} - {\sin(0)\over 2}) \newline
& = {3 \over 4}
\end{split}
$$

### Exercice 8

> Soit {{< texi `\Delta = \{ (x, y) \in \mathbb{R}^2 \space | \space x \geq 0 \space , \space y \geq 0 \space , \space x + y \leq 1 \}`>}}.

* Calculer {{< texi `I = \iint_\Delta (x+y)^2e^{x^2-y^2} \space \text{d}x \text{d}y`>}} en utilisant le changement de variable {{< texi `u = x + y`>}} et {{< texi `v = x - y`>}} 

---
{data-content = " solution "}

* Pour effectuer le jacobien, on a : {{< texi `\begin{cases}
    u = x + y \\
    v = x - y
\end{cases}` >}} et donc {{< texi `\begin{cases}
    x = { {u + v} \over 2 } \\
    y = { {u - v} \over 2 }
\end{cases}` >}}

Le calcul :
$$
\begin{split}
& I = \iint_\Delta (x+y)^2e^{x^2-y^2} \space \text{d}x \text{d}y
 = \iint_\Delta u^2 e^{uv} \left|J_\Phi(u,v)\right| \space \text{d}u \text{d}v
 \newline \newline
& J_\Phi(u,v) = \begin{vmatrix}
  { {\partial x} \over {\partial u}} & { {\partial x} \over {\partial v}} \newline
  { {\partial y} \over {\partial u}} & { {\partial y} \over {\partial v}}
 \end{vmatrix}
= \begin{vmatrix}
  {1 \over 2} & {1 \over 2} \newline
  {1 \over 2} & -{1 \over 2}
 \end{vmatrix}
= -{1 \over 4} -{1 \over 4} = -{1 \over 2}
\end{split}
$$

$$
\text{donc } I = \iint_\Delta u^2 e^{uv} {1 \over 2} \space \text{d}u \text{d}v
$$

On a le tracé suivant :

{{< figure 
    src="/imgs/s4/analyse/chap1_td2_exo8_q1_ggbra.png?h=400"
    alt="alt-test"
    caption="La zone bleu est le domaine avec le changement de variable"
    >}}

En utilisant le théorème de Fubini, on a:

$$
I = \int_0^1 \bigg( \int_{-u}^u u^2 e^{uv} {1 \over 2} \space \text{d}v \bigg) \text{d}u = \int_0^1 {u^2 \over 2} \bigg( \int_{-u}^u  e^{uv}  \space \text{d}v \bigg) \text{d}u
$$

Pour la {{< texi `\text{1}^\text{ère}`>}} intégrale :
$$
\begin{split}
\int_{-u}^u e^{uv} \space \text{d}v \space
& = \bigg[ {e^{uv} \over u} \bigg]_{-u}^u = {e^{u^2} \over u} - {e^{-u^2} \over u} \newline 
& = { {e^{u^2} - e^{-u^2}} \over u}
\end{split}
$$

Pour la {{< texi `\text{2}^\text{ème}`>}} intégrale :
$$
\begin{split}
{1 \over 2} \int_0^1 u^2 { {e^{u^2} - e^{-u^2}} \over u} \space \text{d}u \space
& = {1 \over 2} \int_0^1 u (e^{u^2} - e^{-u^2}) \newline
& = {1 \over 2} \bigg[ {e^{u^2} \over 2} + {e^{-u^2} \over 2} \bigg]_0^1 
& = {e \over 4} + {e^{-1} \over 4} - {1 \over 4} - {1 \over 4} \newline 
& = {1 \over 4}(e + {1 \over e}) - {1 \over 2}
\end{split}
$$

### Exercice 11

> On considère le domain {{< texi `\Delta`>}} défini par
$$
\begin{split}
\Delta = \\{ (x, y) \in \mathbb{R}^2 \space | \space x \leq 2 \space ; \space x^2 + y^2 - 2x \geq 0 \text{ et } \space y^2 \leq 4x \\}
\end{split}
$$

1. Dessiner {{< texi `\Delta.`>}}
2. Déterminer l'aire de {{< texi `\Delta.`>}}
3. Calculer {{< texi `\iint_\Delta y + 1 \space \text{d}x\text{d}y`>}}

---
{data-content = " solution "}

> 1. Dessiner {{< texi `\Delta.`>}}

{{< figure 
    src="/imgs/s4/analyse/chap1_td2_exo11_q1_ggbra.png"
    alt="alt-test"
    caption="La zone bleu foncé est le domaine."
    >}}

> 2. Déterminer l'aire de {{< texi `\Delta.`>}}

L'aire du cercle vaut {{< texi `\pi.`>}}

Et pour l'aire de la parabole :
$$
\int_0^2 \bigg( \int_{-2\sqrt{x}}^{2\sqrt{x}} \text{d}y \bigg) \text{d}x = \int_0^2 4\sqrt{x} \space \text{d}x = 4\bigg[ { {2\sqrt{x}^3} \over 3 } \bigg]_0^2 = {16 \over 3}\sqrt{2}
$$

Et donc l'aire de {{< texi `\Delta`>}} est bien {{< texi `{16 \over 3}\sqrt{2}.`>}}

> 3. Calculer {{< texi `\iint_\Delta y + 1 \space \text{d}x\text{d}y`>}}

#### TODO