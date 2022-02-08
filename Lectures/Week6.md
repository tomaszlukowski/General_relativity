# Week 6 (under construction)

## Acceleration

Define covariant derivative of $W^\mu$ with respect to $\lambda$ by

$$
\frac{DW^\mu}{D\lambda}=\frac{d W^\mu}{d\lambda}+\dot{x}^\rho \,\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu
$$

We claim that $\frac{DW^\mu}{D\lambda}$ is a vector. To show that, let us suppose that $W^\mu$ was a vector field $W^{\mu}(x)$ and set $W^\mu(\lambda)=W^\mu(x(\lambda))$. then

$$
\frac{DW^\mu}{D\lambda}=\frac{d W^\mu}{d\lambda}+\dot{x}^\rho \,\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu=\frac{d x^\rho}{d\lambda}\left(\frac{\partial W^\mu}{\partial x^\rho}+\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu\right)=\frac{d x^\rho}{d\lambda}\left(\nabla_\rho W^\mu\right)
$$

Since $\frac{d x^\rho}{d\lambda}$ is a vector and $\nabla_\rho W^\mu$ is a tensor then also $\frac{DW^\mu}{D\lambda}$ is a tensor. Since it has one upper index then it is a vector.

Let $v^\mu(\tau)=\frac{dx^\mu}{d\tau}$, the four-velocity along a timelike path. We define

$$
A^\mu:=\frac{D v^\mu}{D\tau}
$$

the four-acceleration along a timelike path. This is a reasonable definition because

- $A^\mu$ reduces to $\frac{d^2 x^\mu}{d\tau^2}$ in flat space (SR limit).
- $A^\mu=\frac{Dv^\mu}{D\tau}$ is a vector.
- A free particle has $A^\mu=\ddot{x}^\mu+\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\dot{x}^\nu \dot{x}^\lambda=0$

## Geodesic deviation

>picture

Nearby geodesics correspond to values of $s$ which are close. The separation between geodesics at $s$ and $s+\delta s$ at 'time' $\tau$ is

$$
x^\mu(\tau,s+\delta s)-x^\mu(\tau,s)\approx \frac{\partial x^\mu}{\partial s}\delta s
$$

To examine the relative acceleration, we look at $\frac{D^2\xi}{D\tau^2}$ where

$$
\begin{cases} \xi^\mu=\frac{\partial x^\mu}{\partial s}& \textnormal{separation}\\v^\mu=\frac{\partial x^\mu}{\partial \tau}& \textnormal{four-velocity}\end{cases}
$$

We claim that

$$
\frac{D\xi^\mu}{D\tau}=\frac{Dv^\mu}{Ds}
$$

To show this we first observe that

$$
\frac{\partial\xi^\mu}{\partial \tau}=\frac{\partial^2 x^\mu}{\partial\tau\partial s}=\frac{\partial^2 x^\mu}{\partial s\partial \tau}=\frac{\partial V^\mu}{\partial s}
$$

But in LIC $\frac{D\xi^\mu}{D\tau}\stackrel{\star}{=}\frac{\partial \xi^\mu}{\partial \tau}$ and $\frac{Dv^\mu}{Ds}\stackrel{\star}{=}\frac{\partial v^\mu}{\partial s}$ and therefore this equality is true in any coordinate system.

Let us now work in LIC. We have

$$
\begin{align*}
\frac{D^2\xi^\mu}{D\tau^2}&=\frac{D}{D\tau}\left(\frac{D\xi^\mu}{D\tau}\right)=\frac{\partial}{\partial \tau}\left(\frac{D\xi^\mu}{D\tau}\right)+v^\lambda \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu}\left(\frac{D\xi^\nu}{D\tau}\right)\\
&\stackrel{\star}{=}\frac{\partial}{\partial \tau}\left(\frac{\partial \xi^\mu}{\partial \tau}+v^\lambda \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu}\xi^\nu\right)\stackrel{\star}{=}\frac{\partial^2\xi^\mu}{\partial\tau^2}+v^\lambda \partial_\tau(\Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu})\xi^\nu\stackrel{\star}{=}\frac{\partial^2\xi^\mu}{\partial\tau^2}+v^\lambda v^\kappa (\partial_\tau\Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu})\xi^\nu
\end{align*}
$$

Now we can use the geodesic equation

$$\frac{\partial^2 x^\mu}{\partial \tau^2}+\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}$$

to find that

$$
\begin{align*}
&\frac{\partial}{\partial s}\left(\frac{\partial^2 x^\mu}{\partial \tau^2}\right)=\frac{\partial}{\partial \tau}\left(\frac{\partial v^\mu}{\partial s}\right)=\frac{\partial^2 \xi^\mu}{\partial\tau^2}\\
&=-\frac{\partial}{\partial s}\left[\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}v^\nu v^\lambda\right]\stackrel{\star}{=}-\left(\frac{\partial}{\partial s}\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\right)v^\nu v^\lambda\stackrel{\star}{=}-\xi^\kappa\left(\partial_\kappa\Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu}\right)v^\nu v^\lambda
\end{align*}
$$

We can substitute this in our previous calculation to get

$$
\frac{D^2 \xi^\mu}{D\tau^2}\stackrel{\star}{=}-\xi^\kappa (\partial_\kappa \Gamma_{\nu\,\,\,\lambda}^{\,\,\,\mu})v^\nu v^\lambda+v^\lambda v^\kappa (\partial_\kappa \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu})\xi^\nu\stackrel{\star}{=}v^\lambda v^\kappa \xi^\nu \left(\partial_\kappa \Gamma_{\lambda\,\,\,\nu}^{\,\,\,\mu}-\partial_\nu \Gamma_{\kappa\,\,\,\lambda}^{\,\,\,\mu}\right)
$$

The final bracket is nothing else than the Riemann tensor in LIC and we end up with:

$$
\frac{D^2\xi^\mu}{D\tau^2}\stackrel{\star}{=}R_{\kappa\nu\,\,\,\lambda}^{\,\,\,\,\,\mu}v^\lambda v^\kappa \xi^\nu
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
\partialî\partial_i \phi=\delta^{ij}(\partial_i\partial_j\phi)=0
$$

This suggests the vacuum equation for GR should be

$$
v^\kappa v^\lambda R_{\lambda \rho\,\,\,\kappa}^{\,\,\,\,\,\,\rho}=v^\kappa v^\lambda R_{\lambda\kappa}=0
$$

This should be true for all timelike vectors $v^\mu$ and therefore we conslude that

$$
R_{\mu\nu}=0
$$

This is the vacuum Einstein equation.
```

## Symmetries

$\chi^\mu(x)$ is a **Killing vector** field if $\nabla_{(\mu}\chi_{\nu)}=0$.

Consider $x^\mu(\lambda)$ an affinely parametrised geodesic. Consider $k=\chi_\mu V^\mu$.

```{admonition} Exercise
:class: Warning

If $\chi$ is Killing vector then $k$ is *constant* along the geodesic.

Hint: $\frac{d k}{d\lambda}=\frac{D k}{D\lambda}=\frac{D}{D\lambda}(\chi_\mu v^\mu)$
```

Facts:
- if $g_{\mu\nu}$ does not depend on say $x^0$: $\frac{\partial}{\partial x^0}g_{\mu\nu}=0$, then $\chi^\mu=(1,0,0,0)$ is a Killing vector

```{admonition} Exercise
:class: warning

Show that $\nabla_{(\mu}\chi_{\nu)}=0$ is equivalent to

$$
\chi^\lambda \partial_{\lambda} g_{\mu\nu}+(\partial_mu \chi^\lambda)g_{\lambda\nu}+(\partial_{\nu}\chi^\lambda)g_{\mu\lambda}=0
$$
```

The overall message is That

$$
\textnormal{Killing vectors} \longleftrightarrow \textnormal{symmetries of $g_{\mu\nu}$} \longleftrightarrow \textnormal{conserved quantities}
$$

## Geodesic congruences and parallel transport

>picture

We say that $W^\mu$ is parallel transported along $x^\mu(\lambda)$ if $\frac{D W^\mu}{D\lambda}=0$.

For example if $x^\mu(\lambda)$ is affinely parametrised geodesic then the tangent vector $v^\mu=\frac{dx^\mu}{d\lambda}$ has $\frac{Dv^\mu}{D\lambda}=0$.

Given $W_0^\mu$ at $\lambda=0$, we can solve the equation $\frac{DW^\mu}{D\lambda}=0$, that is a first order ordinary differential equation, to find $W^\mu(\lambda)$ such $W^\mu(0)=W_0^\mu$.

The value of $W^\mu$ at the endpoint depends on which path one takes.

If $W^\mu$ is parallel transported along a geodesic with tangent vector $v^\mu=\frac{dx^\mu}{d\lambda}$ then $W^\mu V_\mu$ is constant.

For example, on $S^2$, the $W^i V_i$ is dot product of vectors:

>picture

We can extend the notion of parallel transport to vector fields: a congruence of curves is a smooth family of curves which covers a patch of space. In four-dimensional spacetime the curves are labelled by 3 parameters, i.e. the parameter $\lambda$ along the curves becomes one of the coordinates on spacetime.

The tangent vector $X^\mu=\frac{\partial x^\mu}{\partial \lambda}$ and for any vector field $W^\mu(x)$ on spacetime

$$
\frac{DW^\mu}{D\lambda}=\frac{dW^\mu}{d\lambda}+\frac{dx^\rho}{d\lambda}\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu=\frac{dx^\rho}{d\lambda}\left(\frac{\partial W^\mu}{\partial x^\rho}+\Gamma_{\rho\,\,\,\nu}^{\,\,\,\mu}W^\nu\right)
$$

and therefore

$$
\frac{DW^\mu}{D\lambda}=X^\rho \nabla_\rho W^\mu
$$

If the curves are geodesics, then we have an affinely parametrised geodesic congruences and $X^\mu=\frac{\partial x^\mu}{\partial\lambda}$ is an auto-parallel vector field

$$
X^\nu \nabla_\nu X^\mu=0
$$

The Riemann tensor can be understood as follows

>picture

$$
\frac{z_1^\mu-z_2^\mu}{\textnormal{Area}}=R_{\lambda\kappa\,\,\,\nu}^{\,\,\,\,\,\,\mu}X^\lambda Y^\kappa Z^\nu
$$
