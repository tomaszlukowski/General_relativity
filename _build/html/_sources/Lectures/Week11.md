# Week 11 (under construction)

## The energy-momentum tensor

Einstein's equations are schematically:

$$
\textnormal{"Curvature tensor"="matter tensor"}
$$

The right-hand side is given by the energy-momentum tensor $T_{\mu\nu}$. In vacuum we have $T_{\mu\nu}=0$.

The energy-momentum tensor has two important properties:
- it is conserved $\nabla_\mu T^{\mu\nu}=0$
- it is symmetric $T_{\mu\nu}=T_{\nu\mu}$

The energy-momentum tensor is schematically:

$$
T^{\mu\nu}=\begin{pmatrix}\textnormal{Energy density }\rho&\textnormal{Energy flux }\epsilon^i\\\textnormal{Momentum density }\pi^i&\textnormal{Stress tensor }T^{ij}\end{pmatrix}
$$

For example, consider a box full of particles, which are at rest with respect to the box, in Special Relativity in an inertial frame where the box has three-velocity $\vec{v}$.

>pictures

Say there are $\mathcal{N}$ particles in the box and in its rest frame it is a cube of side $L$. Let us assume that the box is moving along $x$-axis with velocity $v$. The length of the box in the $x$-direction is Lorentz contracted to $\frac{L}{\gamma}$, so its volume is $V=\frac{L}{\gamma}L^2=\frac{L^3}{\gamma}=\frac{V_\star}{\gamma}$, where $V_\star=L^3$ is the volume in the rest frame. The number density (particles/unit volume) is

$$
\begin{cases}n_\star=\frac{\mathcal{N}}{V_\star}& \textnormal{rest frame}\\n=\frac{\mathcal{N}}{V}=\gamma n_\star& \textnormal{lab frame}\end{cases}
$$

Note that its four-velocity is $V^\mu=(\gamma,\gamma \vec{v})$ so we can write $n=n_\star V^t$. If the particles have rest mass $m$, then

$$
\begin{cases}\textnormal{Energy of each particle}=m\gamma=m V^t\\\textnormal{Three-momentum of each particle}=m\gamma v^i=m V^i\end{cases}
$$
