---
title: ME698E Non-planar acoustics in ducts
theme: Berlin
colortheme: dove
author: Aditya Saurabh
date: 2025-04-25
header-includes:
  - \usepackage{siunitx,booktabs}
  - \usepackage[T1]{fontenc}
  - \usepackage{fourier}
  - \usepackage{sourcesanspro}
---

# General formulation

## Wave equation -- simple harmonic waves

$$
\left( \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} + \frac{\partial^2}{\partial z^2} \right)p + \left( \frac{\omega}{c} \right)^2p = 0
$$

For waves propagating along the duct axis (taken as $z$), the solution is of
the form:

. . .

$$
p = \psi (x, y) e^{ik_z z - i\omega t}
$$

## Eigenvalues and Eigenfunctions

The corresponding equation for $\psi$ is therefore:

$$
\left( \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} \right)\psi + \varkappa^2\psi =
0
$$

with,

$$
\kappa^2 + k_z^2 = k^2 = \left(\frac{\omega}{c}\right)^2
$$

. . . 

With the application of the boundary layer, the solution to the problem is a
**discrete set** of eigenfunctions $\kappa_n$ and corresponding eigenvalues, $\psi_n$

## Eigenfunction properties

The eigenfunctions and eigenvalues have the following properties:

\begin{align*}
\left(  \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2}
\right)\psi_n &= -\kappa^2\psi_n\\
p_{\omega} &= \sum_n A_n \psi_n(x,y)e^{ik_n z - i\omega t}\\
k_n &= \sqrt{\left( \frac{\omega}{c} \right)^2-\kappa^2} =
\frac{2\pi}{\lambda_n} + i\pi \gamma_n\\
\iint \psi_n\psi_m dx\ dy &= \begin{cases}
      0, & \text{if}\ m\neq n \\
            \otherLambda_n S, & \text{otherwise}
	        \end{cases}
\end{align*}

Here $\otherLambda_n$ is the mean of $\psi_n^2$ per unit cross sectional area.

## Mode attenuation and phase velocity

$k_n$ has real and imaginary parts such that if the wavelength of the nth mode
is $\lambda_n$, the phase velocity is:
$$
c_n=\frac{\omega\lambda_n}{2\pi}
$$

. . .

and the mode attenuates by a factor $e^{-1}$ within a distance $\displaystyle
\frac{1}{\pi \gamma_n}$


# Cutoff frequency

## Cutoff frequency

$|\kappa_n|$ increases with $n$ -- the corresponding $\lambda_n$ decreases.

$\therefore$ for a given frequency, $\displaystyle\frac{\omega}{2\pi}$, there exists
a mode order, $n$, for which $\displaystyle \mathrm{Re}(\kappa_n^2) <
\left( \frac{\omega}{c}\right)^2 <  \mathrm{Re}(\kappa_{n+1}^2)$

. . .

For all values of $n$ greater, the imaginary part of $\kappa_n$ -- the
attenuation -- is much larger than the imaginary part of smaller $n$.

## Cutoff frequency

For all values of $n$ greater, the imaginary part of $\kappa_n$ -- the
attenuation -- is much larger than the imaginary part of smaller $n$.

- Each mode has a **cutoff frequency**, $\displaystyle \frac{c}{\lambda_n}$
    - for driving frequencies above, corresponding mode
      propagates with small attenuation
    - for lower frequencies, the mode is highly attenuated and not propagating.

. . .

- When wall admittance, $\beta=0$, the lowest eigenvalue is 0, $\psi_0$=1, and
$\Lambda_0=1$: the fundamental planar mode propagating at phase velocity,
$c_0=c$.
- For frequencies below $\displaystyle \omega<\frac{2\pi c}{\lambda_1}$, only
  planar mode propagates in the duct

# Circular ducts

## Eigenfunctions and eigenvalues

For cylindrical ducts with radius $b$, the eigenfunctions (duct modes) for
rigid walls in the $r-\phi$ coordinate system is given by

$$
\psi_{mn}^\sigma = \begin{cases} cos(m\phi)J_m\left(\frac{\pi q_{mn}r}{b}\right), & \text{for}\ \sigma=1 \\
            sin(m\phi)J_m\left(\frac{\pi q_{mn}r}{b}\right), & \text{for}\ \sigma=-1\end{cases}
$$

$\displaystyle\kappa_{mn}=\frac{\pi q_{mn}}{b}$ $J_m$ denotes Bessel function of order $m$. 

- For each $m$, a discrete set of values, $q$ satisfies the governing equation: $q_{m0}, q_{m1}, q_{m2}, ...$
- The $(m,n)^{th}$ wave has $m$ plane nodal surfaces extending radially out of
  the axis, and $n$ cylindrical nodal shells concentric with the axis.
  
## Eigenfunctions and eigenvalues

For rigid wall BC, the solution to the equations are obtained by considering
velocity normal to the wall is zero: or $J'_m(\pi q)=0$; equivalently $\pi qJ_{m-1}(\pi q)=mJ_m(\pi q)$. This gives $q=\alpha_{mn}$:

\begin{align*}
\alpha_{00} = 0\quad \alpha_{01}&=1.2197\quad \alpha_{02} = 2.2331\ ...\\
\alpha_{10} = 0.5861\quad \alpha_{11}&=1.6970\quad \alpha_{12} = 2.7140\ ...\\
\alpha_{20} = 0.9722\quad \alpha_{21}&=2.1346\quad \alpha_{22} = 3.1734\ ...\\
&...\\
\end{align*}

## Cutoff frequency

\begin{align*}
\alpha_{00} = 0\quad \alpha_{01}&=1.2197\quad \alpha_{02} = 2.2331\ ...\\
\alpha_{10} = 0.5861\quad \alpha_{11}&=1.6970\quad \alpha_{12} = 2.7140\ ...\\
\alpha_{20} = 0.9722\quad \alpha_{21}&=2.1346\quad \alpha_{22} = 3.1734\ ...\\
&...\\
\end{align*}

- (0,0) is the fundamental planar mode.
- the cutoff frequency for $(m,n)^{th}$ mode is given as
  $\displaystyle\frac{\alpha_{mn}c}{2b}$.
- As the cutoff frequency for (1,0) and (2,0) is lower than that for (0,1),
  they will activate first.
- Verify that in a duct \SI{50}{\milli\meter} in radius, only planar acoustics
  will be present till about \SI{2000}{\hertz}
