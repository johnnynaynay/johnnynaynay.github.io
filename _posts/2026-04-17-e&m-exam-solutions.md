---
layout: post
title: E&M Final Exam Solutions
author: Johnny
comments: false
toc: true
math: true
---

The final exam was alright. It was pretty much what I expected, considering, I studied all the questions that showed up on the exam.
In this post, I'd like to share my solutions to them. It may be helpful in your study if you choose to use it.

Solutions may look different, but it's the correct answer. I just used a specific method, and may have
simplified differently.


## Electric Displacement

A metal sphere of radius $a$ carries a charge $Q$. It is surrounded, out to radius $b$,
by linear dielectric material of permittivity $\epsilon$. Find the potential at the center
(relative to infinity).

![em-q1](/assets/figures/em-q1.svg){: .centered}

### Solution

To find the potential at the center relative to infinity, we need the electric field, and we must look at all space.
First, the electric displacement $\vec{D}$ is only in the radial distance, therefore it must only be a function of
$\vec{D(r)}$. 

We already know, for a conducting sphere of radius $a$, the electric field inside is 0, then 
$$ 
E(r < a) = 0 
$$

Let's look in the sphere $r \leq b$, from Gauss's electric displacement law:

$$
\boxed{\oint \vec{D} \cdot \vec{da} = Q_{f, enc}}
$$

where $Q_{f, enc}$ is the enclosed free charge. If we consider a spherical gaussian surface of radius $r$. You can
convince yourself by **symmetry** that $\vec{D}$ and $\vec{da}$ is always perpendicular to the surface, and:

$$
\vec{da} \parallel \vec{D}
$$

Since $\vec{D}$ is always the same magnitude at a fixed radius, it's a constant in the line integral, we can take it out like so:

$$
\oint \vec{D} \cdot \vec{da} = D \oint \vec{da}
$$

Consider a little area element $da = r^2 \sin\theta d\theta d\phi$:

$$
\begin{aligned}
D\oint da &= Dr^2\int_{0}^{\pi} sin\theta d\theta \int_{0}^{2\pi} d\phi \\
D\oint da &= Dr^2\left[ -cos\theta \right]_{0}^{\pi} \left[ \phi \right]_{0}^{2\pi} \\
D\oint da &= Dr^2\left( 2 \right) \left( 2\pi \right) \\
D\oint da &= D4\pi r^2 = Q_{f, enc}
\end{aligned}
$$

Here, $Q_{f,enc}$, the only free enclosed charge is $Q$, since a conducting sphere's charge is located at the surface and it's free to move. But in between the spheres,
there's still charges but they are bounded because they are polarized by the linear dielectric material. Now we have:

$$
\begin{aligned}
D(4\pi r^2) &= Q \\
D &= \frac{Q}{4\pi r^2} \hat{r}
\end{aligned}
$$

Now, let's look at outside the spheres $r> b$, consider the same gaussian surface but with $r> b$:

$$
\oint \vec{D} \cdot \vec{da} = Q_{f, enc} \\
$$

Again, $Q_{f, enc}$ is just $Q$. Then if you look closely, using the same arguments as before, we will get the same solution!

$$
\begin{aligned}
D &= \frac{Q}{4\pi r^2} \hat{r}
\end{aligned}
$$

For a linear dielectric, we can use the relation $E = \displaystyle \frac{D}{\epsilon}$, in a vacuum $\epsilon = \epsilon_{0}$, then our electric field is:

$$
\begin{equation*}
    E = \begin{cases} 
        \displaystyle \frac{1}{4\pi \epsilon_{0}} \frac{Q}{r^2}, & r > b \\[5pt]
        \displaystyle \frac{1}{4\pi \epsilon} \frac{Q}{r^2}, & a < r < b \\[5pt]
        0, & r < a
    \end{cases}
\end{equation*}
$$

To find the potential from infinity to the center, we use the equation:

$$
V = - \int E \cdot dl = - \int_{\infty}^{0} E \cdot dl
$$

We have to split this integrals up to compensate for our different electric fields at different regions:

$$
\begin{aligned}
-\int_{\infty}^{0} E \cdot dl = -\int_{\infty}^{b}\frac{1}{4\pi \epsilon_{0}}\frac{Q}{r^2} dr - \int_{b}^{a} \frac{1}{4\pi \epsilon}\frac{Q}{r^2}dr
-\cancelto{0}{\int_{a}^{0} 0 dr} \\
= - \frac{Q}{4\pi} \left[ \frac{1}{\epsilon_{0}} \int_{\infty}^{b} \frac{1}{r^2}dr + \frac{1}{\epsilon} \int_{b}^{a} \frac{1}{r^2}dr\right] \\
= - \frac{Q}{4\pi} \left[ \frac{1}{\epsilon_{0}} \left( \frac{-1}{b} - \cancelto{0}{\frac{-1}{\infty}} \right) +\frac{1}{\epsilon} \left( \frac{-1}{a} - \frac{-1}{b} \right)  \right] \\
= - \frac{Q}{4\pi} \left[ \frac{-1}{\epsilon_{0}b} - \frac{1}{\epsilon a} + \frac{1}{b} \right]
\end{aligned}
$$

Multiply everything by $-1$ yields the final solution:

$$
\boxed{V_{(0, 0, 0)} = \frac{Q}{4\pi} \left[ \frac{1}{\epsilon_{0}b} + \frac{1}{\epsilon a} - \frac{1}{\epsilon b} \right]}
$$


## Biot-Savart Law

What is the magnetic field from a straight current carrying wire of infinite
length?

Derive the equation using:  
  1. Biot-Savart Law
  2. Ampere's Law

![em-q3](/assets/figures/em-q3.svg){: .centered}

### Solution

The Biot-Savart Law is given by: 

$$ 
\boxed{\displaystyle B = \frac{\mu_{0} I}{4\pi} \int \frac{\vec{dl} \times \hat{r}}{r^2}}
$$


My procedure when I am doing problems with this law is to start with the cross product and identifying our $\vec{dl}$ and $\hat{r}$
Let's compute the cross-product, notice, $\vec{dl}$ is only in the z-direction.

\begin{aligned}
    \vec{dl} \times \hat{r} &= |dl| \cdot 1\sin\phi \cdot \hat{n} \\
    &= dz\sin\phi
\end{aligned}

Plugging back into our original equation:

$$
    B = \frac{\mu_{0}I}{4\pi} \int \frac{dz\sin\phi}{r^2}
$$

From the diagram, we can use pythagorean theorem to get $r = \sqrt{z^2 + a^2}$, $r^2 = z^2+a^2$.

$$
    B = \frac{\mu_{0}I}{4\pi} \int_{-\infty}^{\infty} \frac{dz\sin\phi}{z^2 + a^2}
$$

Also, using trigonometry, we know $\displaystyle \sin\phi = \frac{a}{r} = \frac{a}{\sqrt{z^2+a^2}} = \frac{a}{\left( z^2+a^2 \right)^{1/2}}$.

$$
\begin{aligned}
    B &= \frac{\mu_{0}I}{4\pi} \int_{-\infty}^{\infty} \frac{adz}{\left( z^2+a^2 \right)^1\left( z^2+a^2 \right)^{1/2}} \\
    B &= \frac{\mu_{0}I}{4\pi} \int_{-\infty}^{\infty} \frac{adz}{\left( z^2+a^2 \right)^{3/2}}
\end{aligned}
$$



From here, the physics is pretty much done and it's just math. More specifically, we have to use trigonometric substitution in order to solve the integral.
If you remember your calculus days, we must use the substitution $z=a\tan\phi$. Taking the derivative yields $\displaystyle \frac{dz}{d\phi} = a\sec^2\phi$, then $\displaystyle dz = \frac{ad\phi}{cos^2\phi}$. 
Now, I am going to write one more thing which is $\displaystyle \cos\phi = \frac{a}{r}$, using trigonometry once again.


Let's rewrite the denominator inside the integral from what we know earlier to simplify the problem, and take out the constant $a$:

$$
\begin{aligned}
    B &= \frac{\mu_{0}I}{4\pi} \int_{-\infty}^{\infty} \frac{adz}{\left(r^2\right)^{3/2}} \\
    B &= \frac{\mu_{0}Ia}{4\pi} \int_{-\infty}^{\infty} \frac{adz}{r^3}
\end{aligned}
$$

Plugging in what we got for $dz$:

$$
\begin{aligned}
    \displaystyle B &= \frac{\mu_{0}Ia}{4\pi} \int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \frac{ad\phi}{\cos^2\phi r^3} \\
    B &= \frac{\mu_{0}Ia^2}{4\pi} \int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \frac{d\phi}{\cos^2\phi r^3}
\end{aligned}
$$

Also, since $\displaystyle r^3 = \frac{a^3}{\cos^3\phi}$

$$
\begin{aligned}
    \displaystyle B &= \frac{\mu_{0}I\cancel{a^2}}{4\pi} \int_{\frac{-\pi}{2}}^{\frac{\pi}{2}} \frac{d\phi\cos^{\cancelto{1}{3}}\phi}{\cancel{\cos^2\phi} a^{\cancelto{1}{3}}} \\
    \displaystyle B &= \frac{\mu_{0}I}{4\pi a}\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \cos\phi d\phi \\
    \displaystyle B &= \frac{\mu_{0}I}{4\pi a}\left[ \sin\phi \right]_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \\
    \displaystyle B &= \frac{\mu_{0}I}{4\pi a}\left[ \overbrace{\sin\left(\frac{\pi}{2} \right)}^{1} - \overbrace{\sin\left(-\frac{\pi}{2} \right)}^{-1}\right] \\
    \displaystyle B &= \frac{2\mu_{0}I}{4\pi a} = \frac{\mu_{0}I}{2\pi a}
\end{aligned}
$$

Therefore, the final answer is given by:

$$
\boxed{B = \frac{\mu_{0}I}{2\pi a}}
$$

## To be continued...

Not gonna lie, I got to this point at 4:24 AM, and I am going to bed, but I'll continue this in the morning.

