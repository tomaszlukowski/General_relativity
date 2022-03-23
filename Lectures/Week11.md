# Week 11 (under construction)

## The energy-momentum tensor

Einstein's equations are schematically:

$$
\textnormal{"Curvature tensor"="matter tensor".}
$$

The right-hand side is given by the energy-momentum tensor $T_{\mu\nu}$. In vacuum we have $T_{\mu\nu}=0$.

The energy-momentum tensor has two important properties:
- it is conserved $\nabla_\mu T^{\mu\nu}=0$,
- it is symmetric $T_{\mu\nu}=T_{\nu\mu}$.

The energy-momentum tensor is schematically:

$$
T^{\mu\nu}=\begin{pmatrix}\textnormal{Energy density }\rho&\textnormal{Energy flux }\epsilon^i\\\textnormal{Momentum density }\pi^i&\textnormal{Stress tensor }T^{ij}\end{pmatrix}\,.
$$

For example, consider a box full of particles, which are at rest with respect to the box, in Special Relativity in an inertial frame where the box has three-velocity $\vec{v}$.

>pictures

Say there are $\mathcal{N}$ particles in the box and in its rest frame it is a cube of side $L$. Let us assume that the box is moving along $x$-axis with velocity $v$. The length of the box in the $x$-direction is Lorentz contracted to $\frac{L}{\gamma}$, so its volume is $V=\frac{L}{\gamma}L^2=\frac{L^3}{\gamma}=\frac{V_\star}{\gamma}$, where $V_\star=L^3$ is the volume in the rest frame. The number density (particles/unit volume) is

$$
\begin{cases}n_\star=\frac{\mathcal{N}}{V_\star}& \textnormal{rest frame,}\\n=\frac{\mathcal{N}}{V}=\gamma n_\star& \textnormal{lab frame.}\end{cases}
$$

Note that its four-velocity is $V^\mu=(\gamma,\gamma \vec{v})$ so we can write $n=n_\star V^t=n_\star \gamma$. If the particles have rest mass $m$, then

$$
\begin{cases}\textnormal{Energy of each particle}=m\gamma=m V^t\,,\\\textnormal{Three-momentum of each particle}=m\gamma v^i=m V^i\,.\end{cases}
$$

We have that *Energy density = (number density) x (energy of each particle)*, and therefore

$$
\rho=(n_\star V^t)(m V^t)=n_\star m V^t V^t=\rho_\star V^t V^t\,,
$$

where $\rho_\star=n_\star m$ is the energy (mass) density in rest frame.

Similarly, the three-momentum density in the $i^{th}$ direction is

$$
\pi^i=(n_\star V^t)(mV^i)=mn_\star V^t V^i=\rho_\star V^t V^i\,,
$$

and therefore we have

$$
\begin{cases}T^{tt}=\rho_\star V^t V^t\,,\\T^{it}=\rho_\star V^iV^t\,.\end{cases}
$$

We still need to determine the stress-energy tensor $T^{ij}$. This gives the force in the $i^{th}$ direction acting on a surface of normal direction $j$ per unit area

>picture

If we assume that our particles just sit there and do not interact then $T^{ij}=0$. Then in the rest frame of the box

$$
T^{\mu\nu}\stackrel{\star}{=}\begin{pmatrix}\rho_\star&0\\0&0\end{pmatrix}.
$$

But, in the rest frame $V^\mu\stackrel{\star}{=}(1,\vec{0})$ so

$$
T^{\mu\nu}\stackrel{\star}{=}\rho_\star V^\mu V^\nu\,.
$$

This is a tensor equation and threfore it is valid in any coordinate system.

Another possibility is a **perfect fluid**, characterised by **energy density $\rho$** and **pressure $p$**. Pressure always acts normal to the surface it presses on and is isotropic so $T^{ij}=p\,\delta^{ij}$. So, in the rest frame

$$
T^{\mu\nu}\stackrel{\star}{=}\begin{pmatrix}\rho_\star&0\\0&p\,\delta^{ij}\end{pmatrix},
$$

and we have

$$
V^\mu V^\nu\stackrel{\star}{=}\begin{pmatrix}1&0\\0&0\end{pmatrix},\qquad \eta^{\mu\nu}=\begin{pmatrix}-1&0\\0&\delta^{ij}\end{pmatrix},
$$

so

$$
T^{\mu\nu}\stackrel{\star}{=}(\rho_\star+p)V^\mu V^\nu+p\,\eta^{\mu\nu}\,.
$$

This is a tensor equations (in Special Relativity).

In General Relativity, we can always describe our system in a local inertial frame and get the same equation as above. Therefore in any coordinate system we have

$$
T^{\mu\nu}=(\rho_\star+p)V^{\mu}V^\nu+p\,g^{\mu\nu}\,,
$$

where $V^\mu (x)$ is the four-velocity field of the fluid.

In Special Relativity, the equations $\partial_\mu T^{\mu\nu}=0$ directly become the standard equations for the conservation of energy and momentum in a perfect fluid.

In General Relativity we impose "local conservation" $\nabla_\mu T^{\mu\nu}=0$. This reduces to $\partial_\mu T^{\mu\nu}\stackrel{\star}{=}0$ in a local inertial frame. However, the energy of matter is **not** conserved in the usual sense in dynamical (non-static) spacetimes. For example, photons undergo **red shift** in expanding cosmological spacetimes and this decreases their energy (since $E=\hbar \nu$)!


## Einstein's field equations

We want the field equations to be

- second order in derivatives of $g_{\mu\nu}$ (like $\nabla^2\phi=4\pi G\rho$),
- tensor equations (since only tensor quantities are *physical*),
- reduce to $R_\mu\nu=0$ in vacuum.

This leaves us with the following ansatz for the Einstein's equation in the presence of matter:

$$
R_{\mu\nu}+c_1 R g_{\mu\nu}=c_2 T_{\mu\nu}\,,
$$

where $c_1$ and $c_2$ are constants.

To fix $c_1$ we use local conservation $\nabla_\mu T^{\mu\nu}=0$. before, we showed that for any metric $g_{\mu\nu}$ we have the identity $\nabla_\mu G^{\mu\nu}=0$, where $G^{\mu\nu}=R^{\mu\nu}-\frac{1}{2}g^{\mu\nu}R$. This implies that $c_1=\frac{1}{2}$.

To fix $c_2$ we require the consistency with Newtonian gravity in the non-relativistic limit. In this limit, we have a weak field $\phi(\vec{x})$ and low velocity $|\vec{v}|\ll 1$, and the metric reduces to

$$
ds^2=-(1+2\phi)dt^2+(1-2\phi)d\vec{x}^2\,.
$$

For non-relativistic matter, $|\vec{v}|\ll 1$, the rest mass energy $\rho(\vec{x})$ dominates over kinetic energy $\rho |\vec{v}|^2$ or potential energy $\rho \phi$, or pressure $p$. Therefore $T^{\mu\nu}=\rho V^\mu V^\nu$ with $V^\mu=(1,\vec{0})$. In particular, $T^{tt}=\rho$. For the Newtonian limit metric, we have

$$
G^{tt}=2\partial^i\partial_i\phi=2\nabla^2\phi\,,
$$

so the $tt$-component of Einstein eqution becomes

$$
2\partial^i\partial_i\phi=c_2 \rho\,.
$$

But, Newtonian gravity has $\partial^i\partial_i \phi=4\pi G\rho$, that implies $c_2=8\pi G$. We finally arrive at the Einstein's equation

$$
G_{\mu\nu}=8\pi GT_{\mu\nu}\,.
$$

This gives the relationship between the curvature of spacetime and the distribution of matter/energy in that spacetime.

Comments:

- Einstein's equations provide 10 partial differential equations for $g_{\mu\nu}$ which are non-linear, and therefore much harder to solve than for example Maxwell's equations,
- only six equations are independent. This comes from the fact that there are four Bianchi identities $\nabla_\mu G^{\mu\nu}=0$,
- in a vacuum $T_{\mu\nu}=0$ so $G_{\mu\nu}=0$. This implies that

$$
R_{\mu\nu}-\frac{1}{2}g_{\mu\nu}R=0\quad\Rightarrow\quad g^{\lambda\mu}(R_{\mu\nu}-\frac{1}{2}g_{\mu\nu}R)=0\quad \Rightarrow \quad R^{\lambda}_{\,\,\,\nu}-\frac{1}{2}\delta^\lambda_{\,\,\,\nu}R=0\,,
$$

and we can contract the last equality to get

$$
R^\lambda_{\,\,\,\lambda}-\frac{1}{2}\delta^\lambda_{\,\,\,\lambda}R=R-\frac{1}{2}4R=-R=0\,.
$$

This implies that $R_{\mu\nu}=0$, as required in vacuum.

## Application: Cosmology and the Friedmann equations

The general homogeneous and isotropic universe has

$$
ds^2=-dt^2+a(t)^2\left[\frac{dr^2}{1-kr^2}+r^2(d\theta^2+\sin^2\theta d\phi^2)\right]\,,
$$

where $k=0$ or $k=\pm 1$ for flat or positive or negative spatial curvature solutions.

A homogeneous and isotropic perfect fluid has

$$
T^{\mu\nu}=(\rho+p)U^\mu U^\nu+p\,g^{\mu\nu}\,,
$$

with $U^\mu=(1,\vec{0})$ and $p$ and $\rho$ depending only on $t$.

We can put these into the Einstein equation. A long calculation reveals that $G_{tt}=\frac{3}{a^2}(\dot{a}^2+k)$ so $G_{tt}=8\pi GT_{tt}=8\pi G\rho$ becomes

$$
\left(\frac{\dot{a}}{a}\right)^2=\frac{8\pi G}{3}\rho-\frac{k}{a^2}\,.
$$

This is the Friedmann equation which you may have seen in other modules.

It can be solved to find the scale factor $a(t)$ given assumptions about the matter content of the universe (which relate the density $\rho$ to the pressure $p$).
