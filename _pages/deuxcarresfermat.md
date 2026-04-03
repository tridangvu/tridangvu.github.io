---
layout: single
title: "Sur le théorème des deux carrés de Fermat"
permalink: /deuxcarresfermat/
author_profile: false
sidebar: null
classes: wide
---


**Théorème.** Un nombre premier $p$ est somme de deux carrés si et seulement s'il est égal à $2$ ou congru à $1$ modulo $4$.

---

Découvert de manière expérimentale et énoncé par Fermat. Nous allons ici présenter la preuve d'Euler présentée dans Cox. Le cas $p=2$ étant trivial, on suppose $p$ impair. Il y a deux étapes dans cette dernière :
1. **La descente :** Si $p$ divise $x^2 + y^2$ où $x$ et $y$ sont premiers entre eux, $p$ s'écrit de cette forme
2. **La réciprocité :** Si $p$ est congru à $1$ modulo $4$ , alors $p$ divise une somme de deux carrés premiers entre eux.

La descente est la première étape franchie par Euler, et découle du lemme :

**Lemme.** Supposons que $N$ est une somme de deux carrés premiers entre eux et que $q = x^2 + y^2$ est un diviseur premier de $N$. Alors $N/q$ est aussi une somme de deux carrés.

---
*Démonstration.* L'idée est de s'inspirer de l'arithmétique de $\mathbb{Z}[i]$. On écrit $N = a^2 + b^2$. Si jamais $N/q = c^2 + d^2$, alors 
$$\begin{align}
N &= (x^2+y^2)(c^2+d^2) = |(x+iy)(c+id)|² = |(x+iy)(c-id)|² \\
&= (xc-yd)² + (xd+yc)² =(xc+yd)² + (xd-yc)²
\end{align}$$
L'idée est donc de penser que $a = xc - yd$ ou $xc + yd$, à un signe près, et pareil pour $b$. 
Faisons une disjonction de cas :
1. $(a,b) = (xc - yd, xd + yc)$ : dans ce cas on peut retrouver $c$ et $d$ via
$$\begin{align}
ax + by &= (x^2 + y^2)c = qc \\
bx-ay &= (x^2+y^2)d = qd
\end{align}
$$

2. $(a,b) = (xc+yd, xd-yc)$, auquel cas 
$$\begin{align}
ax-by &= (x^2+y^2)c = qc \\
ay + bx &= (x^2+y^2)d = qd
\end{align}$$

Des choses similaires se passent dans les autres cas où on change un signe. Quoi qu'il en soit, $qc$ est vraisemblablement égal à $ax+by$ ou $ax-by$. En fait :

$$(ax+by)(ax-by)= (ax)^2 - (by)^2 = a^2 q - Ny^2$$
est donc divisible par $q$ premier. Il s'ensuite que $q$ divise $ax+by$ ou $ax-by$. Supposons sans perte de généralité que $ax+by = qc$ pour un entier naturel $c$. Montrons qu'il existe alors un entier $d$ tel que $b = xd +yc$. En effet cela équivaut à écrire que $x$ divise $b-yc$ ou encore $y(b-yc)$ car $x$ et $y$ sont premiers entre eux. Mais
$$y(b-yc) = yb -y^2c = qc - ax - y^2c = x^2c-ax=x(xc-a)$$
On se retrouve avec les relations voulues du cas 1 et on obtient $N = q(c^2+d^2)$.

---

L'étape de la réciprocité, la plus facile de nos jours, était en fait la plus difficile pour Euler, car il ne disposait pas du bon langage et du bon formalisme, mais cela revient à dire que si $p$ est congru à $1$ modulo $4$, alors $-1$ est un carré modulo $p$. 


On conclut comme suit : soit $p$ le plus petit nombre premier congru à $1$ modulo $4$ qui ne s'écrit pas comme somme de deux carrés. Alors il existe $x$ et $y$ premiers entre eux, qu'on peut choisir de valeurs absolues inférieures ou égales à $\dfrac{p-1}{2}$ , tels que $p$ divise $x^2 + y^2$ i.e. $np = x^2 + y^2$, avec $n \leq p/2$. Par hypothèse de minimalité, tout nombre premier divisant $n$ s'écrit comme somme de deux carrés. On peut alors appliquer le principe de la descente.

## Possibles généralisations

**Descente :** Généralisation à $x^2 + ny^2$ : lorsqu'il existe une seule forme réduite de discriminant $-4n$. Cela marche de la même façon pour $n = 2$ ou $3$ car les anneaux $\mathbb{Z}[\sqrt{-2}]$ et  $\mathbb{Z}[\sqrt{-3}]$ sont factoriels.


**Réciprocité :** La condition se réécrit $$\left(\dfrac{-n}{p}\right) = 1$$
avec le symbole de Legendre.
