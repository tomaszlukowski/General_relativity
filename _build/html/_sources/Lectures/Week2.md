# Week 2 (under development)

## Tidal forces

If we have a non-uniform gravitational field with potentila $\phi(\underline{x}$, there will be tidal forces.

For example: consider the field due to a point mas (e.g. a planet) at two nerby points $\underline{x}_1$ and $\underline{x}_2$:

> picture

The  force vectors are not parallel and particles will have a relative acceleration (towards each other). In a freely falling frame, the free particles will seem to accelerate towards each other.

More generally: if we have two nearby particles at $\underline{x}_1=\underline{x}(t)$ and $\underline{x}_2=\underline{x}(t)+\underline{y}(t)$, then both satisfy $\ddot{\underline{x}}=-\underline{\nabla}\phi$, namely $\ddot{\underline{x}}_1=-\underline{\nabla}\phi\Big|_{\underline{x}_1}$ and $\ddot{\underline{x}}_2=-\underline{\nabla}\phi\Big|_{\underline{x}_2}$. This implies that

$$
\underline{y}=\underline{x}_2-\underline{x}_1 \Rightarrow \ddot{\underline{y}}=-\left(\underline{\nabla}\phi\Big|_{\underline{x}+\underline{y}}-\underline{\nabla}\phi\Big|_{\underline{x}}\right)\Rightarrow \ddot{y}_i=-\left(\partial_i\phi\Big|_{\underline{x}+\underline{y}}-\partial_i\phi\Big|_{\underline{x}}\right)\sim -\left(y^j\partial_j\partial_i\phi\Big|_{\underline{x}}+\mathcal{O}(y^2)\right)
$$

This means that roughly $\ddot{y}_i=-(\partial_j\partial_i\phi)y^j$, so $\ddot{y}_i$, the relative acceleration, is small if $y$ is small. But as the separation $\underline{y}$ graows, the relative acceleration becomes more significant (if $\partial_i\partial_j\phi\neq 0$). In general relativity, we think of gravity as beeing *locally* indistinguishable from accelerating frame:

> Locally = ignoring tidal forces

## Gravitational red-shift and time dilation

Consider photon moving down towards Earth. At some instance:

> picture

Sat this is time $t=0$ in the local inertial frame of the cabin (freely-falling). In local inertial frame: cabin height = $\Delta h$, photon frequency = $\nu$. Local inertial observer just sees Special Relativity.

> picture

But: at $t=0$, the cabin at rest with respect to lattice, which implies that observer also sees photon frequency $\nu$. At event B: now the cabin has velocity downwards:

$$
v\sim gt\sim \frac{g\Delta h}{c}
$$

In the local inertial frame, the lattice observer at B is moving upwards towards the photon with velocity $v$. Then the lattice observer sees a Doppler-shifted frequency:

$$
\nu_{\textnormal{obs}}=\left(1+\frac{v}{c}\right)\nu \Rightarrow \Delta\nu=\nu_{\textnormal{obs}}-\nu=\frac{v}{c}\nu=\frac{g\Delta h}{c^2}\nu
$$

This means that $\frac{\Delta\nu}{\nu}=\frac{g\Delta h}{c^2}$ and $g=-\frac{d\Phi}{dh}$, so $\Delta \Phi=-g\Delta h$, and finally

$$
\Delta \log\nu=-\frac{1}{c^2}\Delta\Phi\Rightarrow \nu_{\textnormal{obs}}=\nu_0 e^{-(\Phi-Phi_0)/c^2}
$$

where $\nu_0$ is the frequency at potential $\Phi_0$.

Important point: the frequency shift is not due to anything happening to the photon as it *falls*. It is due to the clocks of the observer running at different speeds. The fixed observer at B is moving with respect to the local inertial frame of the cabin, so their clock appears to run slow in the local inertial frame (standard special relativity Doppler shift).

## Idea: curved spacetime

Imagine the curved surface of a sphere and a tangent plane to it at some point.

>picture

 In a small neighbourhood of the point where the plane touches the sphere, the sphere *looks flat*. But as you move away from tha point, the effects of curvature become important.

 Could the local inertial frames in general relativity be loke the tangent space (locally) to some curved spacetime?

 In special relativity, a massive particle has action:

 $$
S=-m\Delta\tau=-m\int \sqrt{-\eta_{\mu\nu}\dot{x}^{\mu}\dot{x}^{\nu}}d\lambda
 $$

 Consider a *curved metric*: $\eta_{\mu\nu}\to g_{\mu\nu}(x)$ with

 $$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu=-(1+2\phi)dt^2+(1-2\phi)d\underline{x}^2
 $$

 where $\phi=\phi(\underline{x})$ and $d\underline{x}=\delta_{ij}dx^idx^j$. In this case $g_{tt}=-(1+2\phi)$, $g_{ij}=(1-2\phi)\delta_{ij}$, $g_{ti}=0$. Then

 $$
S=-m\int \sqrt{-g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu}d\lambda=-m\int \sqrt{(1+2\phi)\left(\frac{dt}{d\lambda}\right)^2-(1-2\phi)\left(\frac{d\underline{x}}{d\lambda}\right)^2}d\lambda
 $$

 Trick: use parameter $\lambda=t$:

 $$
S= -m\int\sqrt{(1+2\phi)-(1-2\phi)\left(\frac{d\underline{x}}{dt}\right)^2}dt=-m\int\sqrt{1+2\phi-\left(\frac{d\underline{x}}{dt}\right)^2+2\phi \left(\frac{d\underline{x}}{dt}\right)^2}dt
 $$

Now take small velocity ($\frac{d\underline{x}}{dt}$ small) and weak field ($\phi$ small) limit.  Then we can now remove the last term in the square root since it is negligable. Moreover, we can expand the square root in the Taylor series:

$$
S=-m\int(1+\phi-\frac{1}{2}\left(\frac{d\underline{x}}{dt}\right)^2)dt=\int \left(\frac{1}{2}m\underline{v}^2-m\phi\right)dt+const.
$$

The first term $\frac{1}{2}m\underline{v}^2$ is just the kinetic energy and the second one is a potential energy, and we get the action of a non-relativistic particle in gravitational potential $\phi(x)$.
