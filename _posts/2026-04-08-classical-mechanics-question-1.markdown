---
layout: post
title: "Classical Mechanics Question #1"
date: 2026-04-08 01:53:45 -0300
categories: Physics
math: true
---

The shortest path between two points on a curved surface, such as the surface of a sphere, is called a geodesic. To find a geodesic, one has first to set up an integral that gives the length of a path on the surface in question. This will always be similar to the integral $\autoref{eqn:mention}$

\begin{equation}
    L = \int_{1}^2 ds = \int_{x_1}^{x_2} \sqrt{1 + y'(x)^2} dx
    \label{eqn:mention}
\end{equation}

but may be more complicated (depending on the nature of the surface) and may involve different coordinates than $x$ and $y$. 

To illustrate this, use spherical polar coordinates $(r, \theta, \phi)$ to show that the length of a path joining two points on a sphere of radius $R$ is:

\begin{equation}
    L = R \int_{\theta_1}^{\theta_2} \sqrt{1 + \sin^2 \theta  \phi'(\theta)^2} d\theta \label{eqn:path}
\end{equation}

if $(\theta_1, \phi_1)$ and $(\theta_2, \phi_2)$ specify the two points and we assume that the path is expressed as $\phi = \phi(\theta)$.

To solve this question, we have to use Calculus of Variations.

\begin{equation} 
    d\phi = \phi'd\theta \label{eqn:assume}
\end{equation}

Let's consider a small part of the path. On a sphere of constant radius $R$, the radial element $dr = 0$. The line element in spherical coordinates is:

$$ ds^2 = R^2 d\theta^2 + R^2 \sin^2\theta d\phi^2 $$

Substituting $\autoref{eqn:assume}$ into this expression:

$$
\begin{aligned}
    ds^2 &= R^2 d\theta^2 + R^2 \sin^2 \theta (\phi' d\theta)^2 \\
    ds^2 &= R^2 (1 + \sin^2 \theta (\phi')^2) d\theta^2
\end{aligned}
$$

Taking the square root of both sides gives the arc length element $ds$:

\begin{equation}
    ds = R \sqrt{1 + \sin^2\theta (\phi')^2} d\theta
\end{equation}

Integrating from $\theta_1$ to $\theta_2$ yields the final integral for $L$ in $\autoref{eqn:path}$.
