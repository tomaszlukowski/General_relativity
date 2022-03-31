# Week 5

## Local inertial coordinates

At any point $p$ in spacetime, it is possible to choose coordinates such that:

- $g_{\mu\nu}\Big|_p=\eta_{\mu\nu}$,
- $\partial_\mu g_{\nu\rho}\Big|_p=0$.

Such coordinates are called **local inertial coordinates (LIC)** at $p$.

```{note}
The fact that $\partial_\mu g_{\nu\rho}\Big|_p=0$ implies that $\Gamma_{\mu\,\,\,\rho}^{\,\,\,\nu}\Big|_p=0$. This makes calculations involving for example $R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}$ easier!
```

```{important}
In a local inertial coordinates at $p$, $\partial_\mu\partial_\nu g_{\lambda\kappa}$ and $\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\lambda}$ might not vanish.
```

If we can establish that the components of two tensors are equal in LIC at $p$ (usually taken to be $x^\mu=0$) then this implies that they are equal in all coordinate systems (because they are tensors) and the point $p$ was generic so this implies that it is true at all points in spacetime.

### Construction of LIC

- Setting $x'^\mu=x^\mu+a^\mu$ for some constant $a^\mu$, we can choose $a^\mu$ such that $x'^\mu=0$ at our chosen point $p$.
- By the previous point, and without loss of generality, we have that $x^\mu=0$  at $p$. Now set $x^\mu=U^\mu_{\,\,\nu}x'^\nu$ for some constant $U^\mu_{\,\,\nu}$. Then $\frac{\partial x^\lambda}{\partial x'^\mu}=U^\lambda_{\,\,\mu}$ so:

$$
g'_{\mu\nu}=\frac{\partial x^\lambda}{\partial x'^\mu}\frac{\partial x^\kappa}{\partial x'^\nu}g_{\lambda\kappa}=U^\lambda_{\,\,\mu}g_{\lambda\kappa}U^\kappa_{\,\,\nu}\,,
$$

or equivalently

$$
g'=U^T g \,U\,,
$$

as matrices. As $g$ is a symmetric matrix, it is then a standard result in linear algebra that there exists an invertible matrix $W$ such that

$$
W^T g \, W =\begin{pmatrix}-1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1\end{pmatrix}=\eta\,,
$$

which means that there exists a coordinate system for which the metric is equal to $\eta$ at point $p$.

- By the previous two points, we may assume that without loss of generality we can start with $x^\mu=0$ at $p$ and $g_{\mu\nu}=\eta_{\mu\nu}$ at $p$. Then set

$$
x^\mu=x'^\mu+\frac{1}{2}\gamma^\mu_{\,\,\nu\lambda} x'^\nu x'^\lambda\,,
$$

with a constant $\gamma$. This implies that

$$
\frac{\partial x^\mu}{\partial x'^\lambda}=\delta^\mu_{\,\,\lambda}+\gamma^\mu_{\,\,\lambda\rho}x'^\rho\,.
$$

Then

$$
\begin{align*}
g'_{\mu\nu}&=g_{\lambda\kappa}(\delta^\lambda_{\,\,\mu}+\gamma^\lambda_{\,\,\mu\rho}x'^\rho)(\delta^\kappa_{\,\,\nu}+\gamma^\kappa_{\,\,\nu\sigma}x'^\sigma)\\
&=g_{\lambda\kappa}\delta^\lambda_{\,\,\mu}\delta^\kappa_{\,\,\nu}+(g_{\lambda\kappa}\delta^\kappa_{\,\,\nu}\gamma^\lambda_{\,\,\mu\rho}+g_{\lambda\kappa} \delta^\lambda_{\,\,\mu}\gamma^\kappa_{\,\,\nu\rho})x'^\rho+\mathcal{O}(x'^2)\\
&=g_{\mu\nu}+(\gamma_{\nu\mu\rho}+\gamma_{\mu\nu\rho})x'^\rho+\mathcal{O}(x'^2)
\,.\end{align*}
$$

Therefore, for the derivative

$$
\frac{\partial}{\partial x'^\lambda}g'_{\mu\nu}=\frac{\partial}{\partial x'^\lambda}g_{\mu\nu}+2\gamma_{(\mu\nu)\lambda}+\mathcal{O}(x')\,.
$$

If we choose $2\gamma_{(\mu\nu)\lambda}=-\frac{\partial}{\partial x'^\lambda}g_{\mu\nu}\Big|_{x=0}$, then $\frac{\partial}{\partial x'^\lambda}g'_{\mu\nu}\Big|_{x'=0}=0$. Then the coordinates $x'^\mu$ have all the properties of LIC.



## Riemann tensor in LIC

Working in LIC, we will use the symbol $\stackrel{\star}{=}$ to mean "true in LIC at $x=0$", where $x=0$ at point $p$. For example $g_{\mu\nu}\stackrel{\star}{=}\eta_{\mu\nu}$, $\partial_\lambda g_{\mu\nu}\stackrel{\star}{=}0$, $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}\stackrel{\star}{=}0$, but $\partial_\mu\partial_\nu g_{\lambda\kappa}\not\stackrel{\star}{=}0$ in general. We then have

$$
R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}=\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\lambda}-\partial_\nu \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\lambda}+ \Gamma_{\mu\,\,\,\rho}^{\,\,\,\lambda} \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\rho}-\Gamma_{\nu\,\,\,\rho}^{\,\,\,\lambda} \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\rho}\stackrel{\star}{=}\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\lambda}-\partial_\nu \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\lambda}\,.
$$

We will be more interested actually in $R_{\mu\nu\lambda\kappa}$ here. Since $\partial_{\lambda}g_{\mu\nu}\stackrel{\star}{=}0$ then

$$
R_{\mu\nu\lambda\kappa}=g_{\lambda\rho}R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho}\stackrel{\star}{=}\eta_{\lambda\rho}R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho}\stackrel{\star}{=}\eta_{\lambda\rho}(\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\rho}-\partial_\nu \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\rho})\stackrel{\star}{=}\partial_\mu( \eta_{\lambda\rho}\Gamma_{\nu\,\,\,\kappa}^{\,\,\,\rho})-\partial_\nu( \eta_{\lambda\rho}\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\rho})\,.
$$

Now, since

$$
g_{\lambda\rho}\Gamma_{\mu\,\,\,\nu}^{\,\,\,\rho}=\frac{1}{2}(\partial_\mu g_{\nu\lambda}+\partial_\nu g_{\mu\lambda}-\partial_\lambda g_{\mu\nu})\,,
$$

we find

$$
\begin{align*}
R_{\mu\nu\lambda\kappa}&\stackrel{\star}{=}\frac{1}{2}(\partial_\mu\partial_\nu g_{\kappa\lambda}+\partial_\mu\partial_\kappa g_{\nu\lambda}-\partial_{\mu}\partial_\lambda g_{\nu\kappa})-\frac{1}{2}(\partial_\nu\partial_\mu g_{\kappa\lambda}+\partial_\nu\partial_\kappa g_{\mu\lambda}-\partial_\nu\partial_\lambda g_{\mu\kappa})\\
&\stackrel{\star}{=}-(\partial_\lambda\partial_{[\mu}g_{\nu]\kappa}-\partial_\kappa\partial_{[\mu}g_{\nu]\lambda})=-2\partial_{[\lambda|}\partial_{[\mu}g_{\nu]|\kappa]}\,,
\end{align*}
$$

where the last result is antisymmetrised in $\mu\leftrightarrow \nu$ and $\lambda\leftrightarrow \kappa$. For example

$$
R_{\mu\nu\lambda\kappa}\stackrel{\star}{=}-R_{\nu\mu\lambda\kappa}\stackrel{\star}{=}-R_{\mu\nu\kappa\lambda}\,.
$$

We can also check that $R_{\mu\nu\lambda\kappa}\stackrel{\star}{=}R_{\lambda\kappa\mu\nu}$.

All these quantities are tensors and therefore the equations above are true in general!

```{admonition} Exercise
:class: Warning

  - Check that since $R_{\mu\nu\lambda\kappa}=R_{[\mu\nu]\lambda\kappa}$ then

$$
3R_{[\mu\nu\lambda]\kappa}=R_{\mu\nu\lambda\kappa}+R_{\lambda\mu\nu\kappa}+R_{\nu\lambda\mu\kappa}\,.
$$

- Using LIC check that $R_{[\mu\nu\lambda]\kappa}=0$.

- Check that $\nabla_{[\mu}R_{\nu\lambda]\rho\sigma}=0$ using LIC.

- Check that $\nabla_{[\mu}R_{\nu\lambda]}^{\,\,\,\,\,\,\nu\lambda}=0$ and therefore $\nabla_\mu G^{\mu\nu}=0$, where $G^{\mu\nu}=R^{\mu\nu}-\frac{1}{2}g^{\mu\nu}R$.
```

### Summary of Riemann tensor symmetries and identities

Consider the Riemann tensor $R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho}$, and lower an index

$$
R_{\mu\nu\lambda\kappa}=g_{\lambda\rho}R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho}\,.
$$

Symmetries:
- $R_{\mu\nu\lambda\kappa}=R_{[\mu\nu]\lambda\kappa}=R_{\mu\nu[\lambda\kappa]}=R_{[\mu\nu][\lambda\kappa]}$,
- $R_{\mu\nu\lambda\kappa}=R_{\lambda\kappa\mu\nu}$,
- $R_{[\mu\nu\lambda]\kappa}=0$.

Using the second relation from above we have

$$
g^{\mu\lambda}R_{\mu\nu\lambda\kappa}=g^{\mu\lambda}R_{\lambda\kappa\mu\nu}=R_{\nu\kappa}=R_{\kappa\lambda}\,,
$$
and therefore the Ricci tensor is symmetric.

Bianchi identity:

$$
\nabla_{[\mu}R_{\nu\lambda]\kappa\rho}=0\,.
$$

Contracting this, we will also find

$$
\nabla_\mu G^{\mu\nu}=0\,,
$$

where

$$
G_{\mu\nu}=R_{\mu\nu}-\frac{1}{2}g_{\mu\nu}R\,,
$$

is the **Einstein tensor**.



## Particle motion and geodesics

For an arbitrary trajectory/path $x^\mu(\lambda)$, as in the Special Relativity we have

$$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu\,,
$$

and we have that the trajectory is

$$
\begin{cases}\textnormal{timelike, if } ds^2<0\,, \\ \textnormal{null, if }ds^2=0 \,,\\\textnormal{spacelike, if }ds^2>0\,. \end{cases}
$$

Moreover: massive particles move along timelike paths, and massless particles move along null paths.

For timelike trajectories, we define the proper time by

$$
d\tau^2=-ds^2=-g_{\mu\nu}(x)dx^\mu dx^\nu\,,
$$

and the four-velocity

$$
v^\mu=\frac{dx^\mu}{d\tau}\,.
$$

This immediately gives

$$
g_{\mu\nu}v^\mu v^\nu=g_{\mu\nu}\frac{dx^\mu}{d\tau}\frac{dx^\nu}{d\tau}=-1\,,
$$

along the path.

```{admonition} Exercise
:class: warning
Check that $v^\mu$ is a vector.
```

Answer: if $x'^\mu=x'^\mu(x)$ then

$$
v'^\mu=\frac{dx'^\mu}{d\tau}=\left(\frac{\partial x'^\mu}{\partial x^\nu}\right)\frac{dx^\nu}{d\tau}=\left(\frac{\partial x'^\mu}{\partial x^\nu}\right)v^\nu\,.
$$

In Special Relativity, free massive particles move along trajectories which extremise the proper time $\int\tau$ and thus the action:

$$
S=-m\int d\tau=-m\int d\lambda\sqrt{-\eta_{\mu\nu}\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}}\,.
$$

In General Relativity, free massive particles move along timelike trajectories which extremise

$$
S=-m\int d\tau=-m \int d\lambda\sqrt{-g_{\mu\nu}(x)\dot{x}^\mu \dot{x}^\nu}\,.
$$

Trajectories which extremise the interval/distance in this way are called **geodesics**.

We can apply the Euler-Lagrange equations to this action and use $\lambda=\tau$ as the parameter so that $\sqrt{-g_{\mu\nu} \dot{x}^\mu\dot{x}^\nu}=1$ along the trajectory.

If we do this then the geodesic equation is

$$
\frac{d^2 x^\mu}{d\tau^2}+\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\dot{x}^\nu \dot{x}^\lambda=0\,.
$$

By choosing $\lambda=\tau$, we have $\sqrt{-g_{\mu\nu} \dot{x}^\mu\dot{x}^\nu}=const$ in which case the geodesic is called **affinely parametrised**.

But there is a simpler way  to derive this equation: use the simpler action which also works for null geodesics

$$
S=\frac{1}{2}\int d\lambda g_{\mu\nu}\dot{x}^\mu \dot{x}^\nu \,.
$$

The Euler-Lagrange equation $\frac{d}{d\lambda}\left(\frac{\partial L}{\partial \dot{x}^\mu}\right)=\frac{\partial L}{\partial x^\mu}$ implies

$$
\begin{align*}
\frac{d}{d\lambda}\left(g_{\mu\nu}\dot{x}^\nu\right) &=g_{\mu\nu}\ddot{x}^\nu+\dot{x}^\nu \frac{d}{d\lambda}\left(g_{\mu\nu}(x(\lambda))\right)=g_{\mu\nu} \ddot{x}^\nu+(\partial_\rho g_{\mu\nu})\dot{x}^\rho \dot{x}^\nu=\\
&= \frac{\partial L}{\partial x^\mu}=\frac{\partial}{\partial x^\mu}\left(\frac{1}{2}g_{\rho \nu}(x)\dot{x}^\rho \dot{x}^\nu\right)=\frac{1}{2}(\partial_\mu g_{\rho\nu})\dot{x}^\rho \dot{x}^\nu\,.
\end{align*}
$$

This in turn implies that

$$
\ddot{x}^\sigma +\frac{1}{2}g^{\sigma\mu}(2\partial_{\rho}g_{\nu\mu}-\partial_\mu g_{\rho\nu})\dot{x}^\rho \dot{x}^\nu=0\,,
$$

and finally

$$
\ddot{x}^\sigma+\Gamma_{\rho\,\,\,\nu}^{\,\,\,\sigma}\dot{x}^\rho \dot{x}^\nu=0\,.
$$

This is the geodesic equation, but where does the constraint $g_{\mu\nu} \dot{x}^\mu \dot{x}^\nu=const$ come from?

If a Lagrangian $L(x,\dot{x},\lambda)$ does not explicitly depent on $\lambda$, then the Hamiltonian $H=\dot{x}^\mu\frac{\partial L}{\partial\dot{x}^\mu}-L$ has $\frac{dH}{d\lambda}=0$ is constant along the trajectory. Here

$$
H=\dot{x}^\mu(g_{\mu\nu}\dot{x}^\nu)-\left(\frac{1}{2}g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu\right)=\frac{1}{2}g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu=const\,.
$$

We again find affinely parametrised geodesics, but this time we can have any value for the constant. By a constant rescaling $\lambda\to\tilde\lambda=\alpha\lambda$ we have $H\to\frac{1}{\alpha^2}H$ so we can fix

$$
g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu=\begin{cases}-1&\textnormal{timelike,}\\0&\textnormal{null,}\\1&\textnormal{spacelike.}\end{cases}
$$

In practice, we will rarely use the geodesic equations. We will actually use Euler-Lagrange equations (having put in the explicit form of the metric) together with the conditions for $g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu$ above.
