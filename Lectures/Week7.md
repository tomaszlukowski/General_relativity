# Week 7 (under construction)

## Schwarzschild Spacetimes

Last time we argued that the equation of motion for the gravitational field in a vacuum spacetime should be

$$
R_{\mu\nu}=0
$$

Consider the static gravitational field around a spherically symmetric object

> picture

```{admonition} Birkhoff's theorem
:class: tip
- Any spherically symmetric vacuum solution of Einstein's equations must be
  - static
  - asymptotically flat (i.e. becomes Minkowski at spatial infinity)
- The unique solution is the Schwarzschild solution

$$
ds^2=-(1-\frac{2M}{r})dt^2+\frac{dr^2}{1-\frac{2M}{r}}+r^2(d\theta^2+\sin^2\theta d\phi^2)
$$
```

Notes:
- At fixed $t$ and $r$ (i.e. $dt=dx=0$) we have

$$
ds^2=r^2(d\theta^2+\sin^2\theta d\phi^2)
$$

as we move in the $\theta$ and $\phi$ directions. This gives the *normal* geometry of a two-sphere of radius $r$ in spherical coordinates $(\theta,\phi)$.

- One can show that for $r\gg 2M$, if we introduce a new coordinate $\bar{r}=r-M$ then

$$
ds^2=-(1+2\phi)dt^2+(1-2\phi)d\vec{x}^2
$$

with $\phi=-\frac{M}{r}$. This is the Newtonian limit metric for the gravitational field $\phi=-\frac{M}{r}$ around a spherically symmetric object of mass $M$!

```{important}
We identify $M$ with the mass of the spherically symmetric object.
```

- The solution is valid in the vacuum region around the object of mass $M$ (a different solution is needed inside it, depending on the mass distribution).
- Usually the object itself extends beyond $r=2M$

>picture

But it can happen that all of the matter is contained inside the two-sphere radius $r=2M$. the solution should then remain valid right up to $r=2M$ and beyond. Clearly something interesting happens at $r=2M$ (called the **Schwarzschild radius** of the object)!

- As $r\to \infty$, we have $ds^2\approx -dt^2+d\vec{x}^2$. This means that this is asymptotically flat solution. For $r>2M$ we have $\frac{dr^2}{1-\frac{2M}{r}}>dr^2$. This means that the physical distances between spheres at $r$ and $r+\delta r$ is slightly greater than $\delta r$ (much greated as $r\to 2M$). Physical distance from $r=2M$ to $r=r_0>2M$ is finite though:

$$
\int ds=\int_{r=2M}^{r=r_0}\frac{dr}{\sqrt{1-\frac{2M}{r}}}=\int_{u=0}^{u=u_0}\sqrt{1+\frac{2M}{u}}\approx \int_{u=0}^{u=u_0}\sqrt{\frac{2M}{u}}du\approx 2\sqrt{2M}[u^{\frac{1}{2}}]_0^{u_0}\approx 2\sqrt{2M}(r_0-2M)
$$

- Static spacetime: $g_{\mu\nu}$ has no explicit $t$-dependence. This means that flight-times of light signals will be independent of when they are sent. Also there is no $g_{tr}$, $g_{t\theta}$ or $g_{t\phi}$ element in the metric.
- Symmetric if reverse time $t\to -t$. This means that flight times are independent of the direction around a loop.

## Frequency shifts (revisited)

Consider two fixed observers, one vertically above the other, held in place by rocket engines.

>picture

Then we write the four velocity:

$$
v^\mu=\left(\frac{dx^\mu}{d\tau}\right)=\left(\frac{dt}{d\tau},\frac{dr}{d\tau},\frac{d\theta}{d\tau},\frac{d\phi}{d\tau}\right)=(\dot{t},\dot{r},\dot{\theta},\dot{\phi})
$$

For these observers, $r$, $theta$ and $phi$ are constant. We can then find $\dot{t}$ using $g_{\mu\nu}v^\mu v^\nu=-1$:

$$
g_{\mu\nu}v^\mu v^\nu=g_{tt}v^t v^t=-\left(1-\frac{2M}{r}\right)\dot{t}^2=-1\quad \Rightarrow \quad \dot{t}=\left(1-\frac{2M}{r}\right)^{-\frac{1}{2}}
$$

A proper time interval $\Delta \tau_0$ for the observer fixed at $r=r_0$ is related to the coordinate time interval $\Delta t_0$ by

$$
\frac{\Delta t_0}{\Delta\tau_0}=\left(1-\frac{2M}{r_0}\right)^{-\frac{1}{2}}
$$

Similarly for the observer at $r=r_1$:

$$
\frac{\Delta t_1}{\Delta\tau_1}=\left(1-\frac{2M}{r_1}\right)^{-\frac{1}{2}}
$$

Suppose that the observer at $r=r_1$ sends a pulse of light towards the observer at $r=r_2$ at time intervals $\Delta \tau_1$ according to their clock (i.e proper time).

>picture

The coordinate time interval is $\Delta t_1=\left(1-\frac{2M}{r_1}\right)^{-\frac{1}{2}}\Delta\tau_1$

As Schwarzschild is static, the flight time is the same whenever the signal is sent. The difference in the coordinate times of arrival for the two signals at $r=r_2$ will also be $\Delta t_2=\Delta t_1=\Delta t$. Then

$$
\Delta \tau_2=\left(1-\frac{2M}{r_2}\right)^{\frac{1}{2}}\Delta t_2=\left(1-\frac{2M}{r_2}\right)^{\frac{1}{2}}\Delta t_1=\left(1-\frac{2M}{r_2}\right)^{\frac{1}{2}} \left(1-\frac{2M}{r_1}\right)^{-\frac{1}{2}}\Delta\tau_1
$$

If the two pulses were actually two crests of a light wave, the frequency observed by each observer would be $\nu=\frac{1}{\Delta \tau}$ and we would have

$$
\frac{\nu_1}{\nu_2}=\frac{\Delta \tau_2}{\Delta \tau_1}=\frac{\left(1-\frac{2M}{r_2}\right)^{\frac{1}{2}}}{\left(1-\frac{2M}{r_1}\right)^{\frac{1}{2}}}
$$

Comments:
- If $r_2>r_1$ then $\nu_2=\frac{\left(1-\frac{2M}{r_1}\right)^{\frac{1}{2}}}{\left(1-\frac{2M}{r_2}\right)^{\frac{1}{2}}}\nu_1<\nu_1$. This means that the observed frequency is **red-shifted** as the photon climbs out of the field.
- If $r_2=\infty$ then $\nu_2=\left(1-\frac{2M}{r_1}\right)^{\frac{1}{2}}\nu_1$. So if $r_1\to 2M$ then $\nu_2\to 0$. Equivalently, as $r_1\to 2M$, the observed time between the pulses received $\Delta \tau_2\to\infty$. This means that a probe at $r=2M+\epsilon$ will appear to be in slow motion to a far away observer. It will appear to freeze in time at $r=2M$!

## Infalling observer

Consider a probe falling radially into the field ($d\theta=d\phi=0$).

>picture

The probe follows a timelike geodesic: $t=t(\tau), r=r(\tau)$. This means that $L=-1$ where $L$ is the Lagrangian:

$$
L=-\left(1-\frac{2M}{r}\right)\dot{t}^2+\frac{\dot{r}^2}{1-\frac{2M}{r}}
$$

Our strategy is to:
- use Euler-Lagrange equations for $t$
- use $L=-1$

Euler-Lagrange equations for $t$:

$$
\boxed{\frac{d}{d\tau}\left(\frac{\partial L}{\partial \dot{t}}\right)=\frac{\partial L}{\partial t}}\quad\Rightarrow\quad \boxed{\frac{d}{d\tau}\left(-2\left(1-\frac{2M}{r}\right)\dot{t}\right)=0}\quad\Rightarrow\quad \boxed{\left(1-\frac{2M}{r}\right)\dot{t}=E=const}
$$

Since $L=-1$ then

$$
\boxed{-\left(1-\frac{2M}{r}\right)\dot{t}^2+\dot{r}^2=-\left(1-\frac{2M}{r}\right)}\quad\Rightarrow\quad \boxed{\dot{r}^2=E^2-1+\frac{2M}{r}}
$$

Ler the motion be such that $\dot{r}\to 0$ as $r\to\infty$, i.e. $E=1$. Then

$$
\boxed{\dot{r}^2=\frac{2M}{r}}\quad\Rightarrow\quad \dot{r}=-\sqrt{\frac{2M}{r}}\quad\Rightarrow\quad \boxed{\sqrt{r}dr=-\sqrt{2M}d\tau}
$$

Say that $\tau=\tau_0$ at $r=r_0$ (some arbitrary point). Then $\int_{r_0}^{r_1}\sqrt{r}dr=-\sqrt{2M}\int_{\tau_0}^{\tau_1}$ that implies

$$
\boxed{\frac{2}{3}\left(r_1^{\frac{3}{2}-r_0^{\frac{3}{2}}}\right)=-\sqrt{2M}(\tau_1-\tau_0)=-\sqrt{2M}\Delta\tau}\quad\Rightarrow\quad\boxed{ \Delta\tau=\frac{\sqrt{2}}{3\sqrt{M}}\left(r_0^{\frac{3}{2}}-r_1^{\frac{3}{2}}\right)}
$$

This means that proper time experienced by probe to hit $r_1=2M$ is **finite**!

What about the coordinate time $\Delta t$? ($\Delta t$ is the time interval as seen by an observer watching from $r=\infty$).

In this case:

$$
\frac{dr}{d\tau}=\frac{dr}{dt}\frac{dt}{d\tau}=\frac{dr}{dt}\dot{t}=\frac{E}{1-\frac{2M}{r}}\frac{dr}{dt}
$$

Since $\sqrt{r}\frac{dr}{d\tau}=-\sqrt{2M}$ then $\frac{E\sqrt{r}}{1-\frac{2M}{r}}\frac{dr}{dt}=-\sqrt{2M}$. This equation is harder to integrate, but we are only interested in the qualitative result here. Let $r=2M+\epsilon$, then $dr=d\epsilon$ and we have

$$
1-\frac{2M}{r}=\frac{\epsilon}{r}\approx \frac{\epsilon}{2M\left(1+\frac{\epsilon}{2M}\right)}\approx \frac{\epsilon}{2M}
$$

With this approximation we have

$$
\frac{E\sqrt{r}}{1-\frac{2M}{r}}\frac{dr}{dt}\approx E\sqrt{2M+\epsilon}\left(\frac{\epsilon}{2M}\right)^{-1}\frac{d\epsilon}{dt}\approx \frac{2ME\sqrt{2M}}{\epsilon}\frac{d\epsilon}{dt}
$$

so the equation becomes

$$
\frac{d\epsilon}{\epsilon}\approx -\frac{dt}{2ME}
$$

If the start of the trajectory is at $\epsilon=\epsilon_0$ at $t=t_0$, and the end is at $\epsilon=\epsilon_1$ at $t=t_1$ then

$$
\boxed{\int_{\epsilon_0}^{\epsilon_1}\frac{d\epsilon}{\epsilon}\approx -\frac{1}{2ME}\int_{t=t_0}^{t=t_1}dt}\quad\Rightarrow\quad \boxed{\log(\epsilon_1)-\log(\epsilon_0)}\approx -\frac{t_1-t_0}{2ME}=-\frac{\Delta t}{2ME}
$$

and finally

$$
\Delta t=2ME\left[\log\epsilon_0-\log\epsilon_1\right]
$$

This means that $\Delta t\to\infty$ as $\epsilon_1\to 0$.

```{important}
It takes $\infty$ coordinate time to reach $r=2M$.
```


>
