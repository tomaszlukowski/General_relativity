# Week 4

## Differentiation of Tensors

Given a scalar field $\phi(x)$, we checked that $\partial_\mu\phi$ gives the components of a covector field since:

$$
\left(\frac{\partial \phi}{\partial x'^\mu}\right)=\left(\frac{\partial \phi}{\partial x^\nu}\right) \frac{\partial x^\nu}{\partial x'^\mu}\,.
$$

Say we have a vector field $V^\mu(x)$, does $\partial_\mu V^\nu$ give the components of a $(1,1)$-tensor? By simple calculation:

$$
\begin{align*}
\partial'_\mu V'^\nu&=\frac{\partial}{\partial x'^\mu}\left(\frac{\partial x'^\nu}{\partial x^\lambda}V^\lambda\right)=
\frac{\partial x^\kappa}{\partial x'^\mu}\frac{\partial}{\partial x^\kappa}\left(\frac{\partial x'^\nu}{\partial x^\lambda}V^\lambda\right)=\\
&=\frac{\partial x^\kappa}{\partial x'^\mu}\left\{\left[\frac{\partial}{\partial x^\kappa}\left(\frac{\partial x'^\nu}{\partial x^\lambda}\right)\right]V^\lambda+\frac{\partial x'^\nu}{\partial x^\lambda}\left(\frac{\partial}{\partial x^\kappa}V^\lambda\right)\right\}=\\
&=\frac{\partial x^\kappa}{\partial x'^\mu}\left\{ \left(\frac{\partial^2 x'^\nu}{\partial x^\kappa \partial x^\lambda}\right)V^\lambda+\frac{\partial x'^\nu}{\partial x^\lambda}\partial_\kappa V^\lambda\right\}\,,
\end{align*}
$$

where we can see that the second term transforms as we would expect from a $(1,1)$-tensor. However, the first term does not, and therefore the derivative $\partial_\mu V^\nu$ in **not** a tensor.

Similarly, we find that if $\omega_\mu$ is a covector, then $\partial_\mu\omega_\nu$ is not a tensor.

$$
\begin{align*}
\partial'_{\mu}\omega'_\nu=\left(\frac{\partial x^\kappa}{\partial x'^\mu}\frac{\partial}{\partial x^\kappa}\right)\left(\frac{\partial x^\lambda}{\partial x'^\nu} \omega_\lambda\right)=\frac{\partial x^\kappa}{\partial x'^\mu}\frac{\partial x^\lambda}{\partial x'^\nu}(\partial_\kappa \omega_\lambda)+\frac{\partial^2 x^\lambda}{\partial x'^\mu \partial x'^\nu}\omega_\lambda\,.
\end{align*}
$$

However, if we set $A_{\mu\nu}=\partial_\mu\omega_\nu-\partial_\nu\omega_\mu=2\partial_{[\mu}\omega_{\nu]}$ then since the partial derivatives commute

$$
\frac{\partial^2 x^\lambda}{\partial x'^{[\mu]}\partial x'^{\nu]}}=0\,,
$$

this means that the unwanted term cancels out and we conclude that $\partial_{[\mu}\omega_{\nu]}$ defines a tensor.

## Covariant derivatives

We would like to define a way of differentiating such that if we take a tensor and take this new 'derivative' we also end up with a tensor. This is possible and leads to a definition of a **covariant derivative**:

$$
\begin{align*}
&\nabla_\mu\phi=\partial_\mu \phi\,,\\
&\nabla_\mu v^\nu=\partial_\mu v^\nu+\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}v^\lambda\,,\\
&\nabla_\mu \omega_\nu=\partial_\mu \omega_\nu-\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}\omega_\lambda\,,
\end{align*}
$$

where $\Gamma^{\,\,\lambda}_{\mu\,\,\nu}$ is defined in such a way that the covariant derivative acting on vectors or covectors transforms as tensors.

In more general cases we add a $\Gamma$-term for each index (as for vector and covector). For example

$$
\begin{align*}
&\nabla_\mu T^{\nu}_{\,\,\,\lambda}=\partial_\mu  T^{\nu}_{\,\,\,\lambda}+\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\nu}T^\kappa_{\,\,\,\lambda}-\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\kappa}T^\nu_{\,\,\,\kappa}\,,\\
&\nabla_\mu S^{\nu\lambda}=\partial_\mu  S^{\nu\lambda}+\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\nu}S^{\kappa\lambda}+\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\lambda}S^{\nu\kappa}\,.
\end{align*}
$$

The covariant derivative have similar proporties to the ordinary derivative. In particular, it is a linear operation and satisfies the Leibnitz product rule:

$$
\nabla_{\mu}(T S)=(\nabla_{\mu}T) S+T \nabla_{\mu}S\,.
$$

It also satisfies $\nabla_{\mu} \delta^\nu_{\,\,\,\lambda}=0$ which means that it commutes with contraction of indices. For example:

$$
\nabla_{\mu}(v^\nu\omega_\nu)=\left(\nabla_\mu v^\nu\right)\omega_{\nu}+v^\nu \left(\nabla_\mu \omega_\nu\right)\,.
$$

In all these expression, $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ is a **connection**, i.e. we define the transformation of $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ to be such that $\nabla_\mu v^\nu$, $\nabla_\mu \omega_\nu$, etc. are tensors.

```{admonition} Exercise
:class: tip

Check that $\nabla_{\mu} \delta^\nu_{\,\,\,\lambda}=0$.
```
It is important to note that $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ is **not** a tensor!

## Christoffel symbols

In this course, we will take $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ to be a special choice of connection: the **Christoffel symbols**:

$$
\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}=\frac{1}{2}g^{\nu\kappa}\left(\partial_\mu g_{\lambda\kappa}+\partial_\lambda g_{\mu\kappa}-\partial_\kappa g_{\mu\lambda}\right)
$$

We will later see why this is geometrically a natural choice.

Consider an arbitrary connection $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$. We can check a few properties of it. For example by demanding that $A_{\mu\nu}=\partial_\mu\omega_\nu-\partial_\nu\omega_\mu$ is a tensor, as we checked above, we would like to have that $A_{\mu\nu}=\nabla_\mu\omega_\nu-\nabla_\nu\omega_\mu$.

$$
\nabla_\mu\omega_\nu-\nabla_\nu\omega_\mu=\left(\partial_\mu\omega_\nu-\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}\omega_\lambda\right)-\left(\partial_\nu\omega_\mu-\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}\omega_\lambda\right)=\left(\partial_\mu\omega_\nu-\partial_\nu\omega_\mu\right)-\left(\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}\omega_\lambda-\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}\omega_\lambda\right)\,.
$$

So to get $(\nabla_\mu\omega_\nu-\nabla_\nu\omega_\mu)=\left(\partial_\mu\omega_\nu-\partial_\nu\omega_\mu\right)$ we need to have that the connection elements are symmetric:

$$
\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}=\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}\,.
$$

We would also like $\nabla_\mu$ to commute with the raising and lowering indices using the metric tensor $g_{\mu\nu}$ and $g^{\mu\nu}$. For example

$$
\nabla_\mu v_\nu=\nabla_\mu(g_{\nu\lambda}v^\lambda)=(\nabla_\mu g_{\nu\lambda})v^\lambda+g_{\nu\lambda}(\nabla_\mu v^\nu)\,.
$$

This implies that $\nabla_\mu g_{\nu\lambda}=0$.

```{admonition} Properties of connection
:class: tip

We require that any connection possesses the following properties
- $\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}=\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}$  (symmetry),
- $\nabla_\mu g_{\nu\lambda}=0$ (metric compatibility).
```

One can show that the Christoffel symbols satisfy both requirements.

```{admonition} Exercise
:class: Warning
Show that $\nabla_\mu g_{\nu\lambda}=0$ implies that also $\nabla_\mu g^{\nu\lambda}=0$.
```

Sometimes $\nabla_\mu$ is also called *connection*. If we take $\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}$ to be the Christoffel symbols then it is called the **Levi-Civita connection**.

## Riemann tensor

If we take a sufficiently nice function $f(x)$ then we know that partial derivatives with respect to the coordinates commute:

$$
\left(\frac{\partial}{\partial x^\mu}\frac{\partial}{\partial x^\nu}-\frac{\partial}{\partial x^\nu}\frac{\partial}{\partial x^\mu}\right)f(x)=\left[\frac{\partial}{\partial x^\mu},\frac{\partial}{\partial x^\nu}\right]f(x)=0\,.
$$

Therefore, we can ask a very natural question: what is the commutator of two covariant derivatives $[\nabla_\mu,\nabla_\nu]=?$, when acting on sufficiently nice (smooth) tensor.

Let us first assume that we act with this commutator on a vector $v^\mu$:

$$
[\nabla_\mu,\nabla_\nu] v^\lambda=R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda} v^\kappa\,,
$$

where we introduced a new symbol $R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}$ to encode the coefficients of the commutator when expanded in terms of coordinates of vector $v$. By the quotient theorem, we have that $R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}$ are elements of a tensor. This tensor is called the **Riemann tensor** or the **curvature tensor**.

When acting with a commutator of covariant derivatives on other tensors we get a very similar behaviour. For example, for covectors:

$$
[\nabla_\mu,\nabla_\nu] \omega_\lambda=-R_{\mu\nu\,\,\,\lambda}^{\,\,\,\,\,\,\kappa} \omega_\kappa\,.
$$

For tensors with more indices, we get a sum of terms where each summand corresponds to an index of the tensor. For example:

$$
[\nabla_\mu,\nabla_\nu] T^\lambda_{\,\,\,\kappa}=R_{\mu\nu\,\,\,\rho}^{\,\,\,\,\,\,\lambda} T^\rho_{\,\,\,\kappa}-R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho} T^\lambda_{\,\,\,\rho}\,.
$$

This means that it is sufficient to find a single tensor $R$ to know what is the action of the commutator of covariant derivatives on any tensor.

We claim that for the Levi-Civita tensor, the Riemann tensor takes the following form:

$$
R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}=\partial_\mu \Gamma_{\nu\,\,\,\kappa}^{\,\,\,\lambda}-\partial_\nu \Gamma_{\mu\,\,\,\kappa}^{\,\,\,\lambda}+ \Gamma_{\mu\,\,\,\rho}^{\,\,\,\lambda}\Gamma_{\nu\,\,\,\kappa}^{\,\,\,\rho}-\Gamma_{\nu\,\,\,\rho}^{\,\,\,\lambda}\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\rho}\,,
$$

that can be checked by direct calculation.

For future use we will need to define two more tensors:
- **Ricci tensor**: $R_{\mu\nu}=R_{\lambda\mu\,\,\,\nu}^{\,\,\,\,\,\,\lambda}$,
- **Ricci scalar**: $R=g^{\mu\nu}R_{\mu\nu}$.

### Riemann tensor for the two-sphere

We conclude this section with an explicit calculation of these tensors for the simple case of the two-sphere. The line element of the two-sphere with radius $R_0$ is

$$
ds^2=R_0^2 (d\theta^2+\sin^2\theta d\phi^2)=g_{\theta\theta}d\theta^2+g_{\phi\phi}d\phi^2+2g_{\theta\phi}d\theta d\phi=g_{ij} dx^i dx^j\,,
$$

where $x^1=\theta$ and $x^2=\phi$. We can read off the elements of the metric tensor from this line element: $g_{\theta\theta}=R_0^2$ and $g_{\phi\phi}=R_0^2\sin^2\theta$. In matrix form

$$
g=\begin{pmatrix} R_0^2&0\\0&R_0^2\sin^2\theta\end{pmatrix},\qquad\qquad g^{-1}=\begin{pmatrix} R_0^{-2}&0\\0&R_0^{-2}\sin^{-2}\theta\end{pmatrix}.
$$

First, we find all Christoffel symbols $\Gamma_{i\,\,j}^{\,\,k}$ for this metric where

$$
\Gamma_{i\,\,j}^{\,\,k}=\frac{1}{2}g^{kl}(\partial_i g_{jl}+\partial_j g_{il}-\partial_l g_{ij})=\Gamma_{j\,\,i}^{\,\,k}\,,
$$

and $i,j,k=1,2$. We calculate

$$
\Gamma_{\theta\,\,\theta}^{\,\,\,\theta}=\frac{1}{2}g^{\theta k}(\partial_\theta g_{\theta k}+\partial_{\theta}g_{k\theta}-\partial_{k}g_{\theta\theta})=\frac{1}{2}g^{\theta \theta}(\partial_\theta g_{\theta \theta}+\partial_{\theta}g_{\theta\theta}-\partial_{\theta}g_{\theta\theta})=0\,,
$$

where we used the fact that $g^{\theta\phi}=0$ and the fact that $g_{\theta\theta}$ does not depend on $\theta$ and therefore $\partial_{\theta}g_{\theta\theta}=0$.

Following similar calculations:

$$
\begin{align*}
\Gamma_{\theta\,\,\,\phi}^{\,\,\,\theta}&=\frac{1}{2}g^{\theta k}(\partial_\theta g_{\phi k}+\partial_{\phi}g_{\theta k}-\partial_k g_{\theta\phi})=\frac{1}{2}g^{\theta \theta}(\partial_\theta g_{\phi \theta}+\partial_{\phi}g_{\theta \theta}-\partial_\theta g_{\theta\phi})=0=\Gamma_{\phi\,\,\,\theta}^{\,\,\,\theta}\,.\\
\Gamma_{\phi\,\,\,\phi}^{\,\,\,\theta}&=\frac{1}{2}g^{\theta k}(\partial_\phi g_{\phi k}+\partial_{\phi}g_{\phi k}-\partial_k g_{\phi\phi})=\frac{1}{2}g^{\theta \theta}(\partial_\phi g_{\phi \theta}+\partial_{\phi}g_{\phi \theta}-\partial_\theta g_{\phi\phi})=\\
&=\frac{1}{2}R_0^{-2}R_0^2 (-\partial_\theta \sin^2\theta)=-\frac{1}{2}2\sin\theta\cos\theta=-\sin\theta\cos\theta\,.\\
\Gamma_{\theta\,\,\,\theta}^{\,\,\,\phi}&=\frac{1}{2}g^{\phi k}(\partial_\theta g_{\theta k}+\partial_{\theta}g_{\theta k}-\partial_k g_{\theta\theta})=\frac{1}{2}g^{\phi \phi}(\partial_\theta g_{\theta \phi}+\partial_{\theta}g_{\theta \phi}-\partial_\phi g_{\theta\theta})=0\,.\\
\Gamma_{\theta\,\,\,\phi}^{\,\,\,\phi}&=\frac{1}{2}g^{\phi \phi}(\partial_\theta g_{\phi \phi}+\partial_{\phi}g_{\theta \phi}-\partial_\phi g_{\theta\phi})=\frac{1}{2}\left(\frac{1}{\sin^2\theta}\right)\left(\partial_\theta \sin^2\theta\right)=\frac{2\sin\theta\cos\theta}{2\sin^2\theta}=\frac{\cos\theta}{\sin\theta}=\Gamma_{\phi\,\,\,\theta}^{\,\,\,\phi}\,.\\
\Gamma_{\phi\,\,\,\phi}^{\,\,\,\phi}&=\frac{1}{2}g^{\phi\phi}(\partial_\phi g_{\phi\phi}+\partial_\phi g_{\phi\phi}-\partial_\phi g_{\phi\phi})=0\,.
\end{align*}
$$

We conclude that the only non-zero Christoffel symbols are

$$
\Gamma_{\phi\,\,\,\phi}^{\,\,\,\theta}=-\sin\theta\cos\theta\,,\qquad\qquad \Gamma_{\theta\,\,\,\phi}^{\,\,\,\phi}=\Gamma_{\phi\,\,\,\theta}^{\,\,\,\phi}=\frac{\cos\theta}{\sin\theta}\,.
$$

Now we can find the Riemann tensor coefficients where

$$
R_{ij\,\,\,l}^{\,\,\,\,\,k}=\partial_i \Gamma_{j\,\,\, l}^{\,\,k}-\partial_j \Gamma_{i\,\,\, l}^{\,\,k}+\Gamma_{i\,\,\, m}^{\,\,k}\Gamma_{j\,\,\, l}^{\,\,m}-\Gamma_{j\,\,\, m}^{\,\,k}\Gamma_{i\,\,\, l}^{\,\,m}\,.
$$

Since $R_{ij\,\,\,l}^{\,\,\,\,\,k}$ is antisymmetric with respect to the first two indices, then we need to take $i\neq j$ to get a non-zero result. Next week we also see the the tensor $R_{ijkl}$ is antisymmetric with respect to the last two indices. Since the metric of the two sphere is diagonal, it means that we need to take $k\neq l$ as well. Therefore the only non-trivial element of the Riemann tensor is $R_{\theta\phi\,\,\,\phi}^{\,\,\,\,\,\,\theta}$:

$$
\begin{align*}
R_{\theta\phi\,\,\,\phi}^{\,\,\,\,\,\,\theta}&=\partial_{\theta}\Gamma_{\phi\,\,\,\phi}^{\,\,\,\theta}-\partial_{\phi}\Gamma_{\theta\,\,\,\phi}^{\,\,\,\theta}+\Gamma_{\theta\,\,\,m}^{\,\,\,\theta}\Gamma_{\phi\,\,\,\phi}^{\,\,\,m}-\Gamma_{\phi\,\,\,m}^{\,\,\,\theta}\Gamma_{\theta\,\,\,\phi}^{\,\,\,m}\\
&=\partial_\theta(-\sin\theta\cos\theta)+\Gamma_{\theta\,\,\,\theta}^{\,\,\,\theta}\Gamma_{\phi\,\,\,\phi}^{\,\,\,\theta}+\Gamma_{\theta\,\,\,\phi}^{\,\,\,\theta}\Gamma_{\phi\,\,\,\phi}^{\,\,\,\phi}-\Gamma_{\phi\,\,\,\theta}^{\,\,\,\theta}\Gamma_{\theta\,\,\,\phi}^{\,\,\,\theta}-\Gamma_{\phi\,\,\,\phi}^{\,\,\,\theta}\Gamma_{\theta\,\,\,\phi}^{\,\,\,\phi}\\
&=-\partial_\theta(\sin\theta\cos\theta)-(-\sin\theta\cos\theta)\left(\frac{\cos\theta}{\sin\theta}\right)\\
&=-(\cos^2\theta-\sin^2\theta)+\cos^2\theta=\sin^2\theta\,.
\end{align*}
$$

By antisymmetry we can find:

$$
\begin{align*}
R_{\phi\theta\,\,\,\phi}^{\,\,\,\,\,\,\theta}&=-R_{\theta\phi\,\,\,\phi}^{\,\,\,\,\,\,\theta}=-\sin^2\theta\,,\\
R_{\theta\phi\,\,\,\theta}^{\,\,\,\,\,\,\phi}&=g^{\phi\phi}R_{\theta\phi\phi\theta}=-g^{\phi\phi}R_{\theta\phi\theta\phi}=-g_{\theta\theta}g^{\phi\phi}R_{\theta\phi\,\,\,\phi}^{\,\,\,\,\,\,\theta}=-R_0^2R_0^{-2}\sin^{-2}\theta \sin^2\theta =-1\,,\\
R_{\phi\theta\,\,\,\theta}^{\,\,\,\,\,\,\phi}&=-R_{\theta\phi\,\,\,\theta}^{\,\,\,\,\,\,\phi}=1\,.
\end{align*}
$$

The Ricci tensor

$$
R_{ij}=R_{ki\,\,j}^{\,\,\,\,k}\,,
$$

can be calculated to get:

$$
R_{\phi\phi}=R_{\phi\phi\,\,\,\phi}^{\,\,\,\,\,\,\,\phi}+R_{\theta\phi\,\,\,\phi}^{\,\,\,\,\,\,\,\theta}=0+\sin^2\theta=\sin^2\theta\,,
$$

and

$$
R_{\theta\theta}=R_{\phi\theta\,\,\,\theta}^{\,\,\,\,\,\,\phi}+R_{\theta\theta\,\,\,\theta}^{\,\,\,\,\,\,\theta}=1+0=1\,,
$$

with the off-diagonal terms vanishing $R_{\theta\phi}=R_{\phi\theta}=0$.

Finally the Ricci scalar is:

$$
R=R_{i}^{\,\,i}=g^{ij}R_{ij}
$$

and for the two-sphere we get:

$$
R=g^{\theta\theta}R_{\theta\theta}+g^{\phi\phi}R_{\phi\phi}=R_0^{-2}\sin^{-2}\theta \cdot \sin^2\theta+R_0^{-2}\cdot 1=\frac{2}{R_0^2}\,.
$$

We get that the curvature (Ricci scalar) for the two-sphere is inverse-proportional to the radius of the sphere which is an expected result: the larger the radius, the smaller the curvature, and vice versa.
