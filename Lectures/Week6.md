# Week 6

## Acceleration

In this section we want to understand the tidal forces, that we have discussed already in the context of Newtonian mechanics, from the point of view of General Relativity. We start by defining the covariant derivative of a vector $W^\mu$ with respect to $\lambda$ by

$$
\frac{DW^\mu}{D\lambda}=\frac{d W^\mu}{d\lambda}+\dot{x}^\rho \,\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu\,.
$$

We can connect this definition to the definition of a covariant derivative that we introduced before: if $W^\mu$ was a vector field $W^\mu(x)$ and we define $W^\mu(\lambda)=W^\mu(x(\lambda))$ to be its value at the point $x(\lambda)$ then

$$
\frac{DW^\mu}{D\lambda}=\frac{dW^\mu}{d\lambda}+\dot{x}^\rho \Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu=\frac{dx^\rho}{d\lambda}\left(\frac{\partial W^\mu}{\partial x^\rho}+\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu} W^\nu\right)=\frac{dx^\rho}{d\lambda}(\nabla_\rho W^\mu)
$$

where in the last expression we recognise the covariant derivative of a vector field from before.

We established that $\frac{d x^\rho}{d\lambda}$ is a vector and $\nabla_\rho W^\mu$ is a tensor and therefore $\frac{DW^\mu}{D\lambda}$ is a tensor. Since it has one upper index then it is a vector.

**Definition:** let $v^\mu(\tau)=\frac{dx^\mu}{d\tau}$ be the four-velocity of a massive particle along a timelike path. We define

$$
A^\mu:=\frac{D v^\mu}{D\tau}\,,
$$

the four-acceleration along a timelike path. This is a reasonable definition because

- $A^\mu$ reduces to $\frac{d^2 x^\mu}{d\tau^2}$ in the flat space (SR limit).
- $A^\mu=\frac{Dv^\mu}{D\tau}$ is a vector.
- We have $A^\mu=\ddot{x}^\mu+\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\dot{x}^\nu \dot{x}^\lambda=0$ along a geodesic, so the four-acceleration of a free particle is zero.

## Geodesic deviation

Before, we argued that in Newtonian gravity the relative acceleration of two nearby freely-falling particles at $\vec{x}(t)$ and $\vec{x}(t)+\vec{y}(t)$ is given by

$$
\ddot{y}_i=-y^j(\partial_i \partial_j \phi)+\mathcal{O}(y^2).
$$

What is the corresponding statement in GR? To answer this, consider a family of timelike geodesics, smoothly labelled by a parameter $s$, with $\tau$ the proper time along each geodesic so that $x^\mu(\tau;s)$ describe the family:

```{image} ../Week6_pictures/week6_picture1.png
:class: bg-primary mb-1
:width: 300px
:align: center
```


Nearby geodesics then correspond to values of $s$ which are close. The separation between geodesics at $s$ and $s+\delta s$ at 'time' $\tau$ is then described by the derivative $\frac{\partial x^\mu}{\partial s}$ as

$$
x^\mu(\tau,s+\delta s)-x^\mu(\tau,s)\approx \frac{\partial x^\mu}{\partial s}\delta s\,.
$$

To examine the relative acceleration, we look at $\frac{D^2\xi}{D\tau^2}$ where

$$
\begin{cases} \xi^\mu=\frac{\partial x^\mu}{\partial s}& \textnormal{separation}\\v^\mu=\frac{\partial x^\mu}{\partial \tau}& \textnormal{four-velocity}\end{cases}
$$

First, we observe that

$$
\frac{\partial v^\mu}{\partial s}=\frac{\partial^2 x^\mu}{\partial s \partial \tau}=\frac{\partial \xi^\mu}{\partial \tau}\,.
$$

Now, the relative acceleration is the second proper-time derivative of the separation (we drop the $\delta s$ factor). Then we need to examine the following quantity:

$$
\frac{D^2\xi^\mu}{D \tau^2}=\frac{D}{D\tau}\left(\frac{D}{D\tau} \xi^\mu\right).
$$

We claim that

$$
\frac{D\xi^\mu}{D\tau}=\frac{Dv^\mu}{Ds}\,.
$$

To show this we first observe that

$$
\frac{\partial\xi^\mu}{\partial \tau}=\frac{\partial^2 x^\mu}{\partial\tau\partial s}=\frac{\partial^2 x^\mu}{\partial s\partial \tau}=\frac{\partial v^\mu}{\partial s}\,.
$$

But in LIC $\frac{D\xi^\mu}{D\tau}\stackrel{\star}{=}\frac{\partial \xi^\mu}{\partial \tau}$ and $\frac{Dv^\mu}{Ds}\stackrel{\star}{=}\frac{\partial v^\mu}{\partial s}$ and therefore this equality is true in any coordinate system.

Let us now work in LIC. We have

$$
\begin{align*}
\frac{D^2\xi^\mu}{D\tau^2}&=\frac{D}{D\tau}\left(\frac{D\xi^\mu}{D\tau}\right)=\frac{\partial}{\partial \tau}\left(\frac{D\xi^\mu}{D\tau}\right)+v^\lambda \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu}\left(\frac{D\xi^\nu}{D\tau}\right)\\
&\stackrel{\star}{=}\frac{\partial}{\partial \tau}\left(\frac{\partial \xi^\mu}{\partial \tau}+v^\lambda \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu}\xi^\nu\right)\stackrel{\star}{=}\frac{\partial^2\xi^\mu}{\partial\tau^2}+v^\lambda \partial_\tau(\Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu})\xi^\nu\stackrel{\star}{=}\frac{\partial^2\xi^\mu}{\partial\tau^2}+v^\lambda v^\kappa (\partial_\kappa\Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu})\xi^\nu
\end{align*}
$$

We can use the geodesic equation

$$\frac{\partial^2 x^\mu}{\partial \tau^2}+\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\frac{\partial x^\nu}{\partial\tau}\frac{\partial x^\lambda}{\partial \tau}=0\,,
$$

to find that

$$
\begin{align*}
&\frac{\partial}{\partial s}\left(\frac{\partial^2 x^\mu}{\partial \tau^2}\right)=\frac{\partial}{\partial \tau}\left(\frac{\partial v^\mu}{\partial s}\right)=\frac{\partial^2 \xi^\mu}{\partial\tau^2}\\
&=-\frac{\partial}{\partial s}\left[\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}v^\nu v^\lambda\right]\stackrel{\star}{=}-\left(\frac{\partial}{\partial s}\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\right)v^\nu v^\lambda\stackrel{\star}{=}-\xi^\kappa\left(\partial_\kappa\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\right)v^\nu v^\lambda\,.
\end{align*}
$$

We can substitute this in our previous calculation

$$
\frac{D^2 \xi^\mu}{D\tau^2}\stackrel{\star}{=}-\xi^\kappa (\partial_\kappa \Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu})v^\nu v^\lambda+v^\lambda v^\kappa (\partial_\kappa \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu})\xi^\nu\stackrel{\star}{=}v^\lambda v^\kappa \xi^\nu \left(\partial_\kappa \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu}-\partial_\nu \Gamma_{\kappa\,\,\,\lambda}^{\,\,\,\mu}\right).
$$

The final bracket is nothing else than the Riemann tensor in LIC and we end up with:

$$
\frac{D^2\xi^\mu}{D\tau^2}\stackrel{\star}{=}R_{\kappa\nu\,\,\,\lambda}^{\,\,\,\,\,\mu}v^\lambda v^\kappa \xi^\nu\,.
$$

Since all ingredients in the equation above are tensors then this equation is true in any coordinate system.

We can now compare this result to the one we derived for tidal forces in the non-relativistic limit:

$$
\begin{array}{ccc}
\textnormal{Newton}&&\textnormal{Einstein}\\
\ddot{y}_i=-(\partial_i\partial_j \phi)y_j&&\frac{D^2\xi^\mu}{D\tau^2}=(v^\lambda v^\kappa R_{\kappa\nu\,\,\,\lambda}^{\,\,\,\,\,\mu}) \xi^\nu
\end{array}
$$

```{note}
- Relative acceleration ('tidal forces') are given by $R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\,\lambda}$, i.e. curvature of spacetime.
- In Newtonian gravity, the vacuum equation for $\phi$ is

$$
\partial^i\partial_i \phi=\delta^{ij}(\partial_i\partial_j\phi)=0\,.
$$

This suggests the vacuum equation for GR should be

$$
v^\kappa v^\lambda R_{\lambda \rho\,\,\,\kappa}^{\,\,\,\,\,\,\rho}=v^\kappa v^\lambda R_{\lambda\kappa}=0\,.
$$

This should be true for all timelike vectors $v^\mu$ and therefore we conslude that

$$
R_{\mu\nu}=0\,.
$$

This is the **vacuum Einstein equation**!
```

## Symmetries

Consider a vector field $\chi^\mu(x)$ satisfying

$$
\nabla_{(\mu}\chi_{\nu)}=\nabla_{\mu}\chi_{\nu}+\nabla_{\nu}\chi_{\mu}=0\,.
$$

Such a vector field is called a **Killing vector field**.

Consider an affinely parametrised geodesic $x^\mu(\lambda)$ and the quantity $k=\chi_\mu V^\mu$, where $V^\mu=\frac{dx^\mu}{d\lambda}$. Clearly, $k$ is a scalar quantity, independent of the coordinate choice and the choice of the parameter $\lambda$.

```{admonition} Exercise
:class: Warning

If $\chi$ is Killing vector then $k$ is *constant* along the geodesic. Thus $k$ is a **conserved quantity** of the motion.

Hint: $\frac{d k}{d\tau}=\frac{D k}{D\tau}=\frac{D}{D\tau}(\chi_\mu V^\mu)$
```

If a metric $g_{\mu\nu}$ does not depend on one of the coordinates, then we can find a Killing vector that corresponds to this symmetry. For instance, if $g_{\mu\nu}$ does not depend on say $x^0$, that is $\frac{\partial}{\partial x^0}g_{\mu\nu}=0$, then $\chi^\mu=(1,0,0,0)$ is a Killing vector.

```{admonition} Exercise
:class: warning

Show that $\nabla_{(\mu}\chi_{\nu)}=0$ is equivalent to

$$
\chi^\lambda \partial_{\lambda} g_{\mu\nu}+(\partial_\mu \chi^\lambda)g_{\lambda\nu}+(\partial_{\nu}\chi^\lambda)g_{\mu\lambda}=0\,.
$$
```

The overall message is that

$$
\textnormal{Killing vectors} \longleftrightarrow \textnormal{symmetries of $g_{\mu\nu}$} \longleftrightarrow \textnormal{conserved quantities.}
$$

This is the Noether's theorem in General Relativity.

## Geodesic congruences and parallel transport

Given a path $x^\mu(\lambda)$ we say that a vector $W^\mu$ is parallel transported along the path if $\frac{D W^\mu}{D\lambda}=0$.

```{image} ../Week6_pictures/week6_picture2.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

For example if $x^\mu(\lambda)$ is affinely parametrised geodesic then the tangent vector $V^\mu=\frac{dx^\mu}{d\lambda}$ has $\frac{DV^\mu}{D\lambda}=0$.

Given a vector $W_0^\mu$ at $\lambda=0$, we can solve the equation $\frac{DW^\mu}{D\lambda}=0$, that is a first order ordinary differential equation, to find $W^\mu(\lambda)$ such that $W^\mu(0)=W_0^\mu$ and it is parallel transported along a given path $x^\mu(\lambda)$.

The value of $W^\mu$ at the end of the path depends on which path was taken.

```{image} ../Week6_pictures/week6_picture3.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

If a vector $W^\mu$ is parallel transported along a geodesic with tangent vector $V^\mu=\frac{dx^\mu}{d\lambda}$ then $W^\mu V_\mu$ is constant.

For example, on $S^2$, the $W^i V_i$ is dot product of vectors:

```{image} ../Week6_pictures/week6_picture4.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

We can extend the notion of parallel transport to vector fields: a congruence of curves is a smooth family of curves such that each point in spacetime lies on exactly one of the curves. In four-dimensional spacetime the curves are labelled by 3 parameters + the parameter $\lambda$, i.e. the parameter $\lambda$ along the curves becomes one of the coordinates on spacetime.

The tangent vector $X^\mu=\frac{\partial x^\mu}{\partial \lambda}$ then becomes a vector field over all of the patch of space covered by the curves.

```{image} ../Week6_pictures/week6_picture5.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

We have for any vector field $W^\mu(x)$ on spacetime

$$
\frac{DW^\mu}{D\lambda}=\frac{dW^\mu}{d\lambda}+\frac{dx^\rho}{d\lambda}\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu=\frac{dx^\rho}{d\lambda}\left(\frac{\partial W^\mu}{\partial x^\rho}+\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu\right),
$$

and therefore

$$
\frac{DW^\mu}{D\lambda}=X^\rho \nabla_\rho W^\mu\,.
$$

If the curves in the congruence are affinely parametrised geodesics, then it is called an affinely parametrised geodesic congruences and $X^\mu=\frac{\partial x^\mu}{\partial\lambda}$ is an auto-parallel vector field

$$
X^\nu \nabla_\nu X^\mu=\frac{DX^\mu}{D\lambda}=0\,.
$$

The Riemann tensor can be understood as follows:

```{image} ../Week6_pictures/week6_picture6.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

$$
\frac{Z_1^\mu-Z_2^\mu}{\textnormal{Area}}=R_{\lambda\kappa\,\,\,\nu}^{\,\,\,\,\,\,\mu}X^\lambda Y^\kappa Z^\nu\,.
$$
