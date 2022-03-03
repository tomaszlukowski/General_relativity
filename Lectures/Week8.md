# Week 8

## Non-radial Schwarzschild geodesics

We will take a closer look at geodesics for the Schwarzschild solution. We recall that the Lagrangian for this metric is

$$
L=-\left(1-\frac{2M}{r}\right)\dot{t}^2+\frac{\dot{r}^2}{1-\frac{2M}{r}}+r^2(\dot{\theta}^2+\sin^2\theta \dot{\phi}^2)\,.
$$

To simplify our analysis, we will restrict our focus to the equatorial plane geodesics:

```{image} ../Week8_pictures/week8_picture1.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

This is possible because:
- we can rotate the coordinate system such that our initial conditions turn into $\theta=\frac{\pi}{2}$ and $\dot{\theta}=0$.
- in such a case, the Lagrangian and the initial conditions are symmetric under $\theta\to\pi-\theta$, which means that the orbit remains on the $\theta=\frac{\pi}{2}$ plane. In this case the Lagrangian reduces to

$$
L=-\left(1-\frac{2M}{r}\right)\dot{t}^2+\frac{\dot{r}^2}{1-\frac{2M}{r}}+r^2\dot{\phi}^2\,.
$$

Our strategy is:
- Use Euler-Lagrange equations for $t$ and $\phi$ to find conservation laws
- Use $L=\begin{cases}-1&\textnormal{for }\lambda=\tau\textnormal{ timelike}\\0&\textnormal{for null}\end{cases}$

We start with the Euler-Lagrange equations:

- for $t$ we get the same equation as before

$$
\left(1-\frac{2M}{r}\right)\dot{t}=E\,,
$$

- for $\phi$

$$
\boxed{\frac{d}{d\lambda}\left(\frac{\partial L}{\partial \dot\phi}\right)=\frac{\partial L}{\partial \phi}}\quad \Rightarrow\quad \boxed{\frac{d}{d\lambda}(2r^2\dot\phi)=0}\quad\Rightarrow\quad\boxed{r^2 \dot\phi=J=const}
$$

Note that the metric has no dependence on $t$ and $\phi$. Therefore we have the associated symmetries

$$
\begin{cases}t\to t+const\,,\\\phi\to\phi+const\,,\end{cases}
$$

and we expect to find two conserved quantities. These are the **energy** $E$ and the **angular momentum** $J$.

Now we substitute this into $L=-k$, where $k=1$ for timelike geodesics and $k=0$ for null geodesics. We find

$$
\left(1-\frac{2M}{r}\right)^{-1}\left(-E^2+\dot{r}^2\right)+\frac{J^2}{r^2}=-k\,,
$$

and finally

$$
\dot{r}^2=E^2-\left(k+\frac{J^2}{r^2}\right)\left(1-\frac{2M}{r}\right)\,.
$$

The equation for $\dot{r}$ is tricky to solve. Our strategy will be to set $u=\frac{1}{r}$ and look at $\frac{du}{d\phi}=\frac{\dot{u}}{\dot{\phi}}$. Then

$$
\boxed{\frac{du}{d\phi}=\frac{\dot{u}}{\dot\phi}=\frac{-\frac{1}{r^2}\dot{r}}{\frac{J}{r^2}}=-\frac{\dot{r}}{J}}\quad\Rightarrow\quad \boxed{\dot{r}=-J\frac{du}{d\phi}}
$$

Substituting this into the equation above we get

$$
J^2\left(\frac{du}{d\phi}\right)^2+J^2 u^2=E^2-k+\frac{2Mk}{r}+\frac{2MJ^2}{r^3}\,,
$$

and therefore

$$
\left(\frac{du}{d\phi}\right)^2+u^2=\frac{E^2}{J^2}-\frac{k}{J^2}+\frac{2Mku}{J^2}+2Mu^3\,.
$$

Now we take the derivative $\frac{d}{d\phi}$ of this equation and use

$$
\frac{d}{d\phi}\left(\frac{du}{d\phi}\right)^2=2\frac{du}{d\phi}\frac{d^2 u}{d\phi^2}\,,\qquad\qquad \frac{d}{d\phi}u^2=2u\frac{du}{d\phi}\,,
$$

tp get

$$
2\frac{du}{d\phi}\left(\frac{d^2u}{d\phi^2}+u\right)=\frac{2Mk}{J^2}\frac{du}{d\phi}+6Mu^2\frac{du}{d\phi}\,,
$$

that implies

$$
\frac{d^2u}{d\phi^2}+u=\frac{Mk}{J^2}+3Mu^2\,.
$$

The last term on the right-hand side is coming from General Relativity and was not present there in the solution to this problem in Newtonian physics. We will look at some solutions to this equation to study how GR makes revised predictions about solar system physics.

## Deflection of light

We set $k=0$ in our previous equation so that we get a null geodesic

$$
\frac{d^2u}{d\phi^2}+u=3Mu^2\,.
$$

This is a non-linear equation as it has $u^2$ on the right-hand side, and therefore it is hard to solve. We study approximate solutions at large distance from the star, i.e. $Mu\ll 1$. This implies that $Mu^2=(Mu)u\ll u$, so to first approximation we can ignore the non-linear term to get:

$$
\frac{d^2 u}{d\phi^2}+u=0\,.
$$

The solution of this equation is

$$
u=\frac{1}{b}\sin\phi\,,
$$

where $b$ is a constant that can be interpreted as in the figure below

```{image} ../Week8_pictures/week8_picture2.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

In this approximation, the ray passes by the object in a straight line, as it would in Newtonian theory.

Now we can include GR corrections. We re-introduce the $3Mu^2$ term and expand $u$ in powers of $\frac{1}{b}$:

$$
u=\frac{1}{b}\sin\phi+\frac{1}{b^2}u_2(\phi)+\frac{1}{b^3}u_3(\phi)+\ldots\,.
$$

We now work keeping terms up to order $\frac{1}{b^2}$. In particular, note that $u^2=\frac{1}{b^2}\sin^2\phi+\mathcal{O}(\frac{1}{b^3})$. Putting this into our equation we obtain:

$$
\frac{d^2}{d\phi^2}\left(\frac{1}{b}\sin\phi+\frac{1}{b^2}u_2\right)+\left(\frac{1}{b}\sin\phi+\frac{1}{b^2}u_2\right)=\frac{3M}{b^2}\sin^2\phi
$$

that implies

$$
\frac{d^2u_2}{d\phi^2}+u_2=3M\sin^2\phi+\mathcal{O}\left(\frac{1}{b}\right)=\frac{3M}{2}(1-\cos(2\phi))+\mathcal{O}\left(\frac{1}{b}\right).
$$

We want a solution which is symmetric about $\phi=\frac{\pi}{2}$.

```{image} ../Week8_pictures/week8_picture3.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

We do not want to consider the homogeneous equation part of solution (like $A\sin\phi+B\cos\phi$), and we just want to focus on a particular solution. We try:

$$
u_2=A+B\cos(2\phi)\,.
$$

Substituting into our equation we get:

$$
\boxed{(-4B\cos(2\phi))+(A+B\cos(2\phi))=\frac{3M}{2}-\frac{3M}{2}\cos(2\phi)}\quad\Rightarrow\quad\boxed{ \begin{cases}A=\frac{3M}{2}\\B=\frac{M}{2}\end{cases}}
$$

and finally

$$
u_2=\frac{M}{2}(3+\cos(2\phi))\,.
$$

This means that our overall solution is

$$
u=\frac{1}{b}\sin\phi+\frac{M}{2b^2}(3+\cos(2\phi))+\mathcal{O}\left(\frac{1}{b^3}\right).
$$

What does this look like? For $\phi$ around zero we have $u_2\approx 2M>0$, so $r<\frac{1}{b}\sin\phi$. For $\phi=\frac{\pi}{2}$ we have $u_2\approx M$ so $r<\frac{1}{b}\sin\phi$ but it is closer to $\frac{1}{b}\sin\phi$ than near $\phi=0$. For $\phi\approx \pi$, same as for $\phi\approx 0$ by symmetry.

```{image} ../Week8_pictures/week8_picture4.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

Let $\delta$ be the total deflection angle. When $r=\infty$, we have $u=0$ and moreover $\phi$ is small when $u=0$. We look at $\phi\approx 0$ and we set $u=0$. Then

$$
0=\frac{1}{b}\sin\phi+\frac{M}{2b^2}(3+\cos(2\phi))\approx \frac{1}{b}\phi+\frac{M}{2b^2}(3+1)=\frac{\phi}{b}+\frac{2M}{b^2}\,.
$$

This implies that $\phi\approx -\frac{2M}{b}$ and the deflection angle is

$$
\delta\approx \frac{4M}{b}\,.
$$

## Orbit precession

In Newtonian gravity: planets should orbit the Sun following periodic elliptic orbits.

```{image} ../Week8_pictures/week8_picture5.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

However, the orbit of Mercury was observed to rotate (or "precess") so that it does not just repeat the same path for each period.

```{image} ../Week8_pictures/week8_picture6.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

We will show that General Relativity predicts the correct angle of precession $\Delta\phi$ for an almost circular orbit.

To start, consider the orbital equation for a massive orbit

$$
\frac{d^2u}{d\phi^2}+u=\frac{M}{J^2}+3Mu^2\,.
$$

Again assume that $Mu\ll 1$, that means that we can ignore the $3Mu^2$ term. To first approximation, we have Newtonian equation

$$
\frac{d^2u}{d\phi^2}+u=\frac{M}{J^2}=\frac{1}{l}\,,
$$

where $l=\frac{J^2}{M}$. Generic solution to this equation is

$$
u=A\cos\phi+B\sin\phi+\frac{1}{l}\,.
$$

Now rotate axes such that

```{image} ../Week8_pictures/week8_picture7.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

Then the solution is

$$
u=A\cos\phi+\frac{1}{l}=\frac{1}{l}(1+e\cos\phi)\,.
$$

This describes Newtonian orbits.

We now include the GR correction term, taking $u$ to be approximated by the Newtonian orbit. We will take the following simplification relevant to Mercury: take $e=0$ so that $u_1=\frac{1}{l}$, i.e. first approximation is a circular orbit. Let the real solution be

$$
u=\frac{1}{l}+w(\phi)\,,
$$

and let us work to first order in $w$. Substituting into full geodesic equation

$$
\frac{d^2u}{d\phi^2}+u=\frac{1}{l}+3Mu^2\,,
$$

that implies

$$
\frac{d^2w}{d\phi^2}+\left(\frac{1}{l}+w\right)=\frac{1}{l}+3M\left(\frac{1}{l}+w\right)^2=\frac{1}{l}+3M\left(\frac{1}{l^2}+\frac{2w}{l}+w^2\right).
$$

To leading order in $w$ we get

$$
\boxed{\frac{d^2w}{d\phi^2}+w-\frac{6M}{l}w=\frac{3M}{l^2}}\quad\Rightarrow\quad\boxed{\frac{d^2w}{d\phi^2}+\Omega^2 w=\frac{3M}{l^2}}
$$

where $\Omega^2=\left(1-\frac{6M}{l}\right)$. This is the same type of equation as we encountered before. We can find generic solution (with $\frac{dw}{d\phi}=0$ at $\phi=0$) to be

$$
w=C+D\cos(\Omega\phi)\,,
$$

period of $w$ is $\frac{2\pi}{\Omega}=2\pi\left(1-\frac{6M}{l}\right)^{-\frac{1}{2}}$. Note that our approximation was $Mu\ll 1$ and our solution is near $u=\frac{1}{l}$ so we are assuming that $\frac{M}{l}\ll 1$.

```{image} ../Week8_pictures/week8_picture8.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

We can now approximate $\left(1-\frac{6M}{l}\right)^{-\frac{1}{2}}\approx 1+\frac{3M}{l}+\mathcal{O}\left(\left(\frac{M}{l}\right)\right)^2$, and therefore the period is approximately

$$
2\pi\left(1+\frac{3M}{l}\right)=2\pi+\frac{6\pi M}{l}\,.
$$

This means that the angle $\phi$ must increase by $2\pi+\Delta\phi$ before it gets to next maximum, where

$$
\Delta\phi=\frac{6\pi M}{l}\,.
$$
