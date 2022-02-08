# Week 5 (under construction)

## Local inertial coordinates

At any point $p$ in spacetime, there exist coordinates such that:

- $g_{\mu\nu}\Big|_p=\eta_{\mu\nu}$
- $\partial_\mu g_{\nu\rho}\Big|_p=0$

Such coordinates are called **local inertial coordinates (LIC)** at $p$.

```{note}
The fact that $\partial_\mu g_{\nu\rho}\Big|_p=0$ implies that $\Gamma_{\mu\,\,\,\rho}^{\,\,\,\nu}\Big|_p=0$. This makes calculations involving for example $R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}$ easier!
```

```{important}
In a local inertial coordinates at $p$, $\partial_\mu\partial_\nu g_{\lambda\kappa}$ and $\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\lambda}$ might not vanish.
```

If we can establish that the components of two tensors are equal in LIC at $p$ then this implies that they are equal in all coordinate systems (because they are tensors) and the point $p$ was generic so this implies that it is true at all points in spacetime.

## Riemann tensor in LIC

We will use the symbol $\stackrel{\star}{=}$ to mean 'true in LIC at $x=0$', where $x=0$ means at point $p$. For example $g_{\mu\nu}\stackrel{\star}{=}\eta_{\mu\nu}$, $\partial_\lambda g_{\mu\nu}\stackrel{\star}{=}0$, $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}\stackrel{\star}{=}0$, but $\partial_\mu\partial_\nu g_{\lambda\kappa}\not\stackrel{\star}{=}0$ in general. We then have

$$
R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}=\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\lambda}-\partial_\nu \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\lambda}+ \Gamma_{\mu\,\,\,\rho}^{\,\,\,\lambda} \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\rho}-\Gamma_{\nu\,\,\,\rho}^{\,\,\,\lambda} \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\rho}\stackrel{\star}{=}\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\lambda}-\partial_\nu \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\lambda}
$$

We will be more interested actually in $R_{\mu\nu\lambda\kappa}$ here. Since $\partial_{\lambda}g_{\mu\nu}\stackrel{\star}{=}0$ Then

$$
R_{\mu\nu\lambda\kappa}=g_{\lambda\rho}R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho}\stackrel{\star}{=}\eta_{\lambda\rho}R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho}\stackrel{\star}{=}\eta_{\lambda\rho}(\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\rho}-\partial_\nu \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\rho})\stackrel{\star}{=}\partial_\mu( \eta_{\lambda\rho}\Gamma_{\nu\,\,\,\kappa}^{\,\,\,\rho})-\partial_\nu( \eta_{\lambda\rho}\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\rho})
$$

Now, since

$$
g_{\lambda\rho}\Gamma_{\mu\,\,\,\nu}^{\,\,\,\rho}=\frac{1}{2}(\partial_\mu g_{\nu\lambda}+\partial_\nu g_{\mu\lambda}-\partial_\lambda g_{\mu\nu})
$$

we find

$$
\begin{align*}
R_{\mu\nu\lambda\kappa}&\stackrel{\star}{=}\frac{1}{2}(\partial_\mu\partial_\nu g_{\kappa\lambda}+\partial_\mu\partial_\kappa g_{\nu\lambda}-\partial_{\mu}\partial_\lambda g_{\nu\kappa})-\frac{1}{2}(\partial_\nu\partial_\mu g_{\kappa\lambda}+\partial_\nu\partial_\kappa g_{\mu\lambda}-\partial_\nu\partial_\lambda g_{\mu\kappa})\\
&\stackrel{\star}{=}-(\partial_\lambda\partial_{[\mu}g_{\nu]\kappa}-\partial_\kappa\partial_{[\mu}g_{\nu]\lambda})=-2\partial_{[\lambda|}\partial_{[\mu}g_{\nu]|\kappa]}
\end{align*}
$$

where the last result is antisymmetrised in $\mu\leftrightarrow \nu$ and $\lambda\leftrightarrow \kappa$. For example

$$
R_{\mu\nu\lambda\kappa}\stackrel{\star}{=}-R_{\nu\mu\lambda\kappa}\stackrel{\star}{=}-R_{\mu\nu\kappa\lambda}
$$

We can also check that $R_{\mu\nu\lambda\kappa}\stackrel{\star}{=}R_{\lambda\kappa\mu\nu}$.

All these quantities are tensors and therefore the equations above are true in general!

```{admonition} Example
:class: Warning

  - Check that since $R_{\mu\nu\lambda\kappa}=R_{[\mu\nu]\lambda\kappa}$ implies

$$
3R_{[\mu\nu\lambda]\kappa}=R_{\mu\nu\lambda\kappa}+R_{\lambda\mu\nu\kappa}+R_{\nu\lambda\mu\kappa}
$$

- Using LIC check that $R_{[\mu\nu\lambda]\kappa}=0$

- Check that $\nabla_{[\mu}R_{\nu\lambda]\rho\sigma}=0$ using lattice

- Check that $\nabla_{[\mu}R_{\nu\lambda]}^{\,\,\,\,\,\,\nu\lambda}=0$ and therefore $\nabla_\mu G^{\mu\nu}=0$, where $G^{\mu\nu}=R^{\mu\nu}-\frac{1}{2}g^{\mu\nu}R$.
```

## Particle motion and geodesics

For an arbitrary trajectory/path $x^\mu(\lambda)$, as in the Special Relativity we have

$$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu
$$

and we have that the trajectory is

$$
\begin{cases}ds^2<0 &\longleftrightarrow& \textnormal{timelike}\\ds^2=0 &\longleftrightarrow& \textnormal{null}\\ds^2>0 &\longleftrightarrow& \textnormal{spacelike}\end{cases}
$$

Moreover: massive particles move along timelike paths, and massless particles move along null paths.

For timelike trajectories, define the proper times

$$
d\tau^2=-ds^2=-g_{\mu\nu}(x)dx^\mu dx^\nu
$$

and the four-velocity

$$
v^\mu=\frac{dx^\mu}{d\tau}
$$

Therefore

$$
g_{\mu\nu}v^\mu v^\nu=g_{\mu\nu}\frac{dx^\mu}{d\tau}\frac{dx^\nu}{d\tau}=-1
$$

Let $v^\mu$ is a vector. If $x'^\mu=x'^\mu(x)$ then

$$
v'^\mu=\frac{dx'^\mu}{d\tau}=\left(\frac{\partial x'^\mu}{\partial x^nu}\right)\frac{dx^\nu}{d\tau}=\left(\frac{\partial x'^\mu}{\partial x^\nu}\right)v^\nu
$$

In Special Relativity, massive particle action:

$$
S=-m\int d\tau=-m\int \sqrt{-\eta_{\mu\nu}\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}}d\lambda
$$

In General Relativity, free massive particles move along timelike trajectories which extremise

$$
S=-m\int d\tau=-m \int\sqrt{-g_{\mu\nu}(x)\dot{x}^\mu \dot{x}^\nu}d\lambda
$$

Trajectories which extremise the interval/distance in this way are called **geodesics**.

One way to proceed is to:

  - apply Euler-Lagrange equations
  - choose parameter $\lambda=\tau$ so that $\sqrt{-g_{\mu\nu} \dot{x}^\mu\dot{x}^\nu}=1$

If we do this then the affinely parametrised geodesic equation is

$$
\frac{d^2 x^\mu}{d\tau^2}+\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\dot{x}^\nu \dot{x}^\lambda=0
$$

But there is a simpler way  to derive this equation: use the simpler action which also works for null Geodesics

$$
S=\frac{1}{2}\int g_{\mu\nu}\dot{x}^\mu \dot{x}^\nu d\lambda
$$

Euler-Lagrange equation $\frac{d}{d\lambda}\left(\frac{\partial L}{\partial \dot{x}^\mu}\right)=\frac{\partial L}{\partial x^\mu}$ imply

$$
\begin{align*}
\frac{d}{d\lambda}\left(g_{\mu\nu}\dot{x}^\nu\right) &=g_{\mu\nu}\ddot{x}^\nu+\dot{x}^\nu \frac{d}{d\lambda}\left(g_{\mu\nu}(x(\lambda))\right)=g_{\mu\nu} \ddot{x}^\nu+(\partial_\rho g_{\mu\nu})\dot{x}^\rho \dot{x}^\nu=\\
&= \frac{\partial L}{\partial x^\mu}=\frac{\partial}{\partial x^\mu}\left(\frac{1}{2}g_{\rho \nu}(x)\dot{x}^\rho \dot{x}^\nu\right)=\frac{1}{2}(\partial_\mu g_{\rho\nu})\dot{x}^\rho \dot{x}^\nu
\end{align*}
$$

This implies

$$
\ddot{x}^\sigma +\frac{1}{2}g^{\sigma\mu}(2\partial_{\rho}g_{\nu\mu}-\partial_\mu g_{\rho\nu})\dot{x}^\rho \dot{x}^\nu=0
$$

and finally

$$
\ddot{x}^\sigma+\Gamma_{\rho\,\,\,\nu}^{\,\,\,\sigma}\dot{x}^\rho \dot{x}^\nu=0
$$

These equations imply that $g_{\mu\nu} \dot{x}^\mu \dot{x}^\nu=const$. We can choose the affine parameter to fix this constant and get

$$
g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu=\begin{cases}-1&\textnormal{timelike}\\0&\textnormal{null}\\1&\textnormal{spacelike}\end{cases}
$$

In practice, we will rarely use the geodesic equations. We will actually use Euler-Lagrange equations (having put in the explicit form of the metric) together with the conditions for $g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu$ above.
