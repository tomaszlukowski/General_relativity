# Week 1

## introduction



## Newtonian physics:

In Newtonian physics, time is **absolute** $\rightarrow$ all observables and clocks agree on all time measurements.

```{image} ../Week1_pictures/week1_picture1.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

Laws of Newtonian physics are invariant under the transformation:

$$
\begin{align*}
&x'=x-vt\\
&t'=t
\end{align*}
$$

For example, $\ddot{x}=0\Rightarrow \ddot{x}'=\ddot{x}-\frac{d^2}{dt^2}(vt)=\ddot{x}=0$.

In particular, this defines an absolute global time coordinate.

Experiments show that this is *good* for velocities $|v|\ll c$. But for $v=\mathcal{O}(c)$, this breaks down and we need **special relativity** (SR).

In SR we still have *inertial frames* with coordinates $(t,\underline{x})$ in which free particles travel at constant velocity $\frac{d^2x}{dt^2}=0$.

But, the transformation between them is different!

## Special relativity: Lorentz transformations.

```{image} ../Week1_pictures/week1_picture2.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

$$
\begin{pmatrix}ct'\\x'\end{pmatrix}=\begin{pmatrix}\gamma&-\frac{\gamma v}{c}\\ -\frac{\gamma v}{c}&\gamma\end{pmatrix}\begin{pmatrix}ct\\x\end{pmatrix}
$$

where $\gamma=\frac{1}{\sqrt{1-\frac{v^2}{c^2}}}\geq 1$. (As $c\to \infty$, this reduces to Newtonian rule).

A very important consequence is that time measurements are **not** the same for all observers.

The amount of time which passes according to a physical clock depends on how the clock moves.

```{image} ../Week1_pictures/week1_picture3.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

The time recorded by the two clocks $A$ and $B$ may not be the same.

Recall: Write $(x^0,x^1,x^2,x^3)=(ct,x,y,z)=(x^\mu)$

$$
(\eta_{\mu\nu})=\begin{pmatrix}-1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1\end{pmatrix}
$$

i.e. $\eta_{00}=-1$ and $\eta_{ij}=\delta_{ij}$ where $i,j=1,2,3$.

The separation $\Delta x^\mu=x_2^\mu-x_1^\mu$ between events at $x_1$ and $x_2$ transforms under Lorentz transformations:

$$
\Delta x^{'\mu}=\Lambda^{\mu}_{\,\,\nu}\Delta x^\nu \,\,\textnormal{  with  }\,\, \eta_{\mu\nu}\Lambda^{\mu}_{\,\,\mu'}\Lambda^{\nu}_{\,\,\nu'}=\eta_{\mu'\nu'}
$$

So, the quantity

$$
\Delta s^2=\eta_{\mu\nu}\Delta x^\mu\Delta x^\nu=-c^2\Delta t^2+\Delta x^2+\Delta y^2+\Delta z^2
$$

is invariant. The interval $\Delta x^\mu$ is
- **spacelike** if $\Delta s^2>0$
- **null** if $\Delta s^2=0$
- **timelike** if $\Delta s^2<0$

```{image} ../Week1_pictures/week1_picture4.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

Consider a path in spacetime (with parameter $\lambda$)

```{image} ../Week1_pictures/week1_picture5.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

Let $\delta s^2=\eta_{\mu\nu}\delta x^\mu\delta x^\nu\sim \frac{dx^\mu}{d\lambda}\delta\lambda$. The path is spacelike/null/timelike if $\delta s^2$ is spacelike/null/timelike along the whole path.

In Special Relativity:
- **massless** particles (e.g. photons) follow null trajectories
- **massive** particles (e.g. clocks) follow timelike trajectories
- (A spacelike trajectory corresponds to an extended object, e.g. a rod)

The proper time recorded by a clock moving along a timelike trajectory:

$$
c\Delta \tau=\int_{\textnormal{Start}}^{\textnormal{End}}\sqrt{-ds^2}=\int_{\lambda=\lambda_0}^{\lambda=\lambda_1}\sqrt{-\left(\frac{ds}{d\lambda}\right)^2}d\lambda
$$

For timelike trajectories we have $ds^2<0$ that implies $ds^2=-c^2 d\tau^2$. Then $c\,d\tau=\sqrt{-ds^2}$

$$
c\Delta\tau=\int c\, d\tau=\int \sqrt{-ds^2}=\int\sqrt{-\left(\frac{ds}{d\lambda}\right)^2}d\lambda=\int \sqrt{-\eta_{\mu\nu}\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}}d\lambda
$$

The $t$ coordinate of an inertial frame corresponds to the proper time as recorded by a clock which is stationary in that frame.

```{image} ../Week1_pictures/week1_picture6.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

In this case $\frac{dx^{\mu}}{d\lambda}=(\frac{d(c\lambda)}{d\lambda},\underline{0})=(c,\underline{0})$ and $\eta_{\mu\nu}\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}=(-1)c^2=-c^2$.

$$
c\Delta \tau=\int\sqrt{c^2}d\lambda=c\int d\lambda=c\Delta\lambda=c\Delta t
$$

For any timelike path, we can use $\tau$ as the parameter and then $ds^2=-c^2 d\tau^2=\eta{dx^\mu}dx^{\nu}$ that implies $\eta_{\mu\nu}\frac{dx^\mu}{d\tau}\frac{dx^\nu}{d\tau}=-c^2$.

We define the **4-velocity** of the particle as

$$
v^\mu=\frac{dx^\mu}{d\tau}=\left(\frac{d(ct)}{d\tau},\frac{d\underline{x}}{d\tau}\right)=\frac{dt}{d\tau}\left(c,\frac{d\underline{x}}{dt}\right)=\gamma(v)(c,\underline{v})
$$

where $\underline{v}=\frac{d\underline{x}}{dt}$. Recall also the 4-momentum is $p^\mu=mv^\mu$. This has $p^2=\eta_{\mu\nu}p^{\mu}p^{\nu}=m^2\eta_{\mu\nu}v^{\mu}v^{\nu}=-m^2c^2$.

Set $c=1$. The **4-momentum** has components $p^{\mu}=(E,\underline{p})$. Give an invariant expression for the energy of the particle as seen by an observer with 4-velocity $v^{\mu}$.

```{image} ../Week1_pictures/week1_picture7.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

In the rest frame of observer $v^{\mu}=(1,\underline{0})$ and $p^{\mu}=(E,\underline{p})$, we have $\eta_{\mu\nu}v^{\mu}p^{\nu}=-E$ that implies $E=-\eta_{\mu\nu}v^{\mu}p^{\nu}$.

## Action of relativistic particles
We already defined proper time $\Delta\tau=\int\sqrt{-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu}d\lambda=\int d\tau$.

> picture

Define the action $S=-m\int d\tau$. We can use the Euler-Lagrange equations

$$
\frac{d}{d\lambda}\left(\frac{\partial L}{\partial \dot{x}^\mu}\right)=\frac{\partial L}{\partial x^\mu}=0
$$

to get

$$
\frac{\partial L}{\partial\dot{x}^\mu}=
\frac{1}{2\sqrt{-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu}}\cdot\frac{\partial}{\partial\dot{x}^\mu}\left(-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu\right)=
\frac{1}{2\sqrt{-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu}}(-\eta_{\rho\nu})\left(\frac{\partial \dot{x}^\rho}{\partial \dot{x}^\mu}\dot{x}^\nu+\dot{x}^\rho\frac{\partial \dot{x}^\nu}{\partial \dot{x}^\mu}\right)=\\
\frac{1}{2\sqrt{-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu}}(-\eta_{\rho\nu})\left(\delta_\mu^\rho\dot{x}^\nu+\dot{x}^\rho\delta_\mu^\nu\right)=
\frac{1}{2\sqrt{-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu}}\left(-\eta_{\mu\nu}\dot{x}^\nu-\eta_{\rho\mu}\dot{x}^\rho\right)
$$

Then

$$
\frac{d}{d\lambda}\left[\frac{-\eta_{\mu\nu}\dot{x}^\nu}{\sqrt{-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu}}\right]=0
$$

Choose $\lambda=\tau$ to be the parameter, then $\sqrt{-\eta_{\mu\nu} \dot{x}^\mu \dot{x}^\nu}=1$ that implies

$$
\frac{d}{d\tau}\left(-2\eta_{\mu\nu}\dot{x}^\nu\right)=0\Rightarrow \ddot{x}^\mu=0
$$

Consider the case $|\underline{v}|\ll c$. Then

$$
S=-mc^2\int d\tau=-mc^2\int \frac{d\tau}{dt}dt
$$

The 4-velocity $v^\mu=(\frac{d(ct)}{d\tau},\frac{d\underline{x}}{d\tau})=\gamma(c,\underline{v})$, that implies $\frac{dt}{d\tau}=\gamma$.

We have

$$
S=-mc^2\int \gamma^{-1}dt=-mc^2\int \sqrt{1-\frac{v^2}{c^2}}dt\sim -mc^2\int \left(1-\frac{1}{2}\frac{v^2}{c^2}\right)dt=\int \left(\frac{1}{2}mv^2-mc^2\right)dt
$$

This only worked for $m\neq 0$.

Nicer action: $S=-\int \eta_{\mu\nu}\dot{x}^\mu\dot{x}^\nu$. The Euler-Lagrange equations are:

$$
\ddot{x}^\mu=0\Rightarrow\frac{d}{d\lambda}(\eta_{\mu\nu}\dot{x}^{\mu}\dot{x}^\nu)=0\Rightarrow \eta_{\mu\nu}\dot{x}^{\mu}\dot{x}^\nu=\textnormal{constant along the path}=-E
$$

If $E=0$ we have a null path $\rightarrow$ massless particle. If $E>0$ we have a timelike path $\rightarrow$ massive particle. In the latter case rescale $\lambda\to\lambda'=\sqrt{E}\lambda$ that implies $\eta_{\mu\nu}\dot{x}^\mu\dot{x}^\nu=-1$. new parameter $\lambda'$ is the proper time $\tau$.

## Accelerating frames (Newtonian)

Consider two reference frames:

> picture

These frames are related by $t'=t$ and $x'x-\frac{1}{2}at^2$.

Free particle: in the inertial frame the free particle has $x=x_0+vt$. in the $(x',t')$ frame (non-inertial) we have

$$
x'=x-\frac{1}{2}at^2=x_0+vt-\frac{1}{2}at^2=x_0+vt'-\frac{1}{2}at'^2
$$

> picture

This is indistinguishable from a constant gravitational field strength of $g=a$ in the negative $x$-direction. The equations of motion:

$$
F=ma\Rightarrow m\ddot{x}=-mg\Rightarrow \ddot{x}=-g\Rightarrow \ddot{x}=x_0+vt-\frac{1}{2}gt^2
$$

Notes:
- The mass cancelled (in agreement with Galileo)!. The inertial mass is equal to the gravitational mass
- If we think that the acceleration in the non-inertial frame is due to gravity, then the other frame is a freely-falling frame, i.e. **freely-falling frames are inertial**.
