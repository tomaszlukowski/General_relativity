# Week 4 (missing)


## Symmetry and antisymmetry

Given tensor $T_{\mu\nu}$ we can define two new tensors:

$$
\begin{align*}
T_{[\mu\nu]}=\frac{1}{2}\left(T_{\mu\nu}-T_{\nu\mu}\right)=: A_{\mu\nu}\\
T_{(\mu\nu)}=\frac{1}{2}\left(T_{\mu\nu}+T_{\nu\mu}\right)=: S_{\mu\nu}
\end{align*}
$$

We have the following simple properties of the new tensors:

$$
\begin{align*}
&A_{\mu\nu}=A_{[\mu\nu]},\qquad A_{\mu\nu}=-A_{\nu\mu}\\
&S_{\mu\nu}=S_{(\mu\nu)},\qquad S_{\mu\nu}=S_{\nu\mu}
\end{align*}
$$

Furthermore, we have

$$
T_{\mu\nu}=T_{[\mu\nu]}+T_{(\mu\nu)}
$$

We call the tensor $A_{\mu\nu}$ the antisymmetrisation of $T_{\mu\nu}$ and the tensor $S_{\mu\nu}$ the symmetrisation of $T_{\mu\nu}$.

There are more complicated examples that we can construct if we have tensors with more indices. For example

$$
R_{[\mu\nu][\lambda\kappa]}=\frac{1}{2}\left(R_{\mu\nu[\lambda\kappa]}-R_{\nu\mu[\lambda\kappa]}\right)=\frac{1}{4}\left(R_{\mu\nu\lambda\kappa-R_{\mu\nu\kappa\lambda}+R_{\nu\mu\kappa\lambda-R_{\nu\mu\lambda\kappa\right)
$$

We can also define an (anti)-symmetrisation of more than two indices. For example:

$$
X_{[\mu\nu\lambda]}=\frac{1}{3!}\left(X_{\mu\nu\lambda}+X_{\nu\lambda\mu}+X_{\lambda\mu\nu}-X_{\nu\mu\lambda}-X_{\mu\lambda\nu}-X_{\lambda\nu\mu}\right)
$$

If we set $A_{\mu\nu\lambda}=X_{[\mu\nu\lambda]}$ and $S_{\mu\nu\lambda}=X_{(\mu\nu\lambda)}$ then $A_{\mu\nu\lambda}=-A_{\nu\mu\lambda}$ and $S_{\mu\nu\lambda}=S_{\nu\mu\lambda}$.

```{note}
If we contract symmetric indeces with antisymmetric indices then the answer is zero!
```

For example: if $A_{\mu\nu}^{\lambda}=A_{[\mu\nu]}^{\lambda}$ and $B^{\mu\nu\lambda}=B^{(\mu\nu\lambda)}$ then $B^{\mu\nu\lambda}A_{\nu\lambda}^\kappa=0$.

Moreover, if we antisymmetrise the indices of a tensor that is already symmetric in these indices then we also get zero. For example, of $g_{\mu\nu}=g_{(\mu\nu)}$ the $g_{\mu\nu}=\frac{1}{2}\left(g_{\mu\nu}-g_{\nu\mu}\right)=\frac{1}{2}\left(g_{\mu\nu}-g_{\mu\nu}\right)=0$.

Important theorem: If we have $A\cdot B=C$ where $C$ is a tensor for any tensor $B$ then this implies that $A$ is a tensor.

## Differentiation of Tensors
Let us consider a scalar field $\phi(x)$. We can define a covector field $\partial_\mu\phi$. It transforms as:

$$
\left(\frac{\partial \phi}{\partial x'^\mu}\right)=\left(\frac{\partial \phi}{\partial x^\nu}\right) \frac{\partial x^\nu}{\partial x'^\mu}
$$

Similarly, if we have a covector field $\omega_{\mu}(x)$, we can ask if $\partial_\mu\omega_\nu$ is a tensor? By simple calculation:

$$
\begin{align*}
\partial'_\mu \omega'_\nu&=\frac{\partial}{\partial x'^\mu}\left(\frac{\partial x^\lambda}{\partial x'^\nu}\omega_\lambda\right)=\left[\frac{\partial}{\partial x'^\mu}\left(\frac{\partial x^\lambda}{\partial x'^\nu}\right)\right]\omega_\lambda+\frac{\partial x^\lambda}{\partial x'^\nu}\left(\frac{\partial}{\partial x'^\mu}\omega_\lambda\right)=\\
&= \left(\frac{\partial^2 x^\lambda}{\partial x'^\mu \partial x'^\nu}\right)\omega_{\lambda}+\left(\frac{\partial x^\lambda}{\partial x'^\nu}\frac{\partial x^\kappa}{\partial x'^\mu}\right)\left(\frac{\partial}{\partial x^\kappa}\omega_\lambda\right)
\end{align*}
$$

where we can see that the second term transforms as we would expect from a tensor. However, the first term does not and therefore the derivative $\partial_\mu\omega_\nu$ in **not** a tensor.

But notice the following fact: if we took $\partial_{\mu}\omega_\nu-\partial_{\nu}\omega_\mu=2\partial_{[\mu}\omega_{\nu]}$ instead then since the partial derivatives commute

$$
\frac{\partial^2 x^\lambda}{\partial x'^{[\mu]}\partial x'^{\nu]}}=0
$$

This means that the first unwanted term cancels out and we conclude that $\partial_{[\mu}\omega_{\nu]}$ define a tensor.

## Covariant derivatives

We would like to define a way of differentiating such that if we take a tensor and take this new 'derivative' we also end up with a tensor. This is possible and leads to a definition of a covariant derivative:

$$
\begin{align*}
&\nabla_\mu\phi=\partial_\mu \phi\\
&\nabla_\mu v^\nu=\partial_\mu v^\nu+\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}v^\lambda\\
&\nabla_\mu \omega_\nu=\partial_\mu \omega_\nu-\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}\omega_\lambda\\
\end{align*}
$$

In more general cases we add a $\Gamma$-term for each index (as for vector and covector). For example

$$
\begin{align*}
&\nabla_\mu T^{\nu}_{\,\,\,\lambda}=\partial_\mu  T^{\nu}_{\,\,\,\lambda}+\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\nu}T^\kappa_{\,\,\,\lambda}-\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\kappa}T^\nu_{\,\,\,\kappa}\\
&\nabla_\mu S^{\nu\lambda}=\partial_\mu  S^{\nu\lambda}+\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\nu}S^{\kappa\lambda}+\Gamma_{\mu\,\,\,\kappa}^{\,\,\,\lambda}S^{\nu\kappa}
\end{align*}
$$

The covariant derivative have similar proporties to the ordinary derivative. In particular, it is a linear operation and satisfies the Leibnitz product rule:

$$
\nabla_{\mu}(T\ldots S)=\nabla_{\mu}(T\ldots) S+T\ldots \nabla_{\mu}S
$$

It also satisfies $\nabla_{\mu} \delta^\nu_{\,\,\,\lambda}=0$ which means that it commutes wiith contraction of indices. For example:

$$
\nabla_{\mu}(v^\nu\omega_\nu)=\left(\nabla_\mu v^\nu\right)\omega_{\nu}+v^\nu \left(\nabla_\mu \omega_\nu\right)
$$

In all these expression, $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ is a **connection**, i.e. define the transformation of $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ to be such that $\nabla_\mu v^\nu$, $\nabla_\mu \omega_\nu$, etc. are tensors.

```{admonition} Exercise
:class: tip

Check that $\nabla_{\mu} \delta^\nu_{\,\,\,\lambda}=0$.
```
It is important to note that $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ in **not** a tensor!

## Christoffel symbols

In this course, we will take $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$ to be a special choice of connection: the **Christoffel symbols**:

$$
\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}=\frac{1}{2}g^{\nu\kappa}\left(\partial_\mu g_{\lambda\kappa}+\partial_\nu g_{\mu\kappa}-\partial_\kappa g_{\mu\nu}\right)
$$

We will later see why this is geometrically a natural choice.

Consider an arbitrary connection $\Gamma_{\mu\,\,\,\lambda}^{\,\,\,\nu}$. We can check a few properties of it. For example by demanding that $A_{\mu\nu}=\partial_\mu\omega_\nu-\partial_\nu\omega_mu$ to be a tensor, as we checked above, we would to have that $A_{\mu\nu}=\nabla_\mu\omega_nu-\nabla_\nu\omega_\mu$.

$$
\nabla_\mu\omega_nu-\nabla_\nu\omega_\mu=\left(\partial_\mu\omega_\nu-\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}\omega_\lambda\right)-\left(\partial_\nu\omega_\mu-\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}\omega_\lambda\right)=\left(\partial_\mu\omega_\nu-\partial_\nu\omega_\mu\right)-\left(\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}\omega_\lambda-\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}\omega_\lambda\right)
$$

So to get $\nabla_\mu\omega_nu-\nabla_\nu\omega_\mu=\left(\partial_\mu\omega_\nu-\partial_\nu\omega_\mu\right)$ we need to have that the Chritoffel symbols are symmetric:

$$
\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}=\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}
$$

We would also like $\nabla_\mu$ to commute with the raising and lowering indices using the metric tensor $g_{\mu\nu}$ and $g^{\mu\nu}$. For example

$$
\nabla_\mu v_\nu=\nabla_\mu(g_{\nu\lambda}v^\lambda)=(\nabla_\mu g_{\nu\lambda})v^\lambda+g_{\nu\lambda}(\nabla_\mu v^\nu)
$$

This implies that $\nabla_\mu g_{\nu\lambda}=0$.

```{admonition} Properties of connection
:class: tip

We require that any connection possesses the following Properties
- $\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}=\Gamma_{\nu\,\,\,\mu}^{\,\,\,\lambda}$  (symmetric)
- $\nabla_\mu g_{\nu\lambda}=0$ (metric compatibility)
```

One can show that the Christoffel symbols satisfy both requirements.

```{admonition} Exercise
:class: tip

Show that if $\nabla_\mu g_{\nu\lambda}=0$ then also $\nabla_\mu g^{\nu\lambda}=0$
```

Sometimes $\nabla_\mu$ is called *connection*. If we take $\Gamma_{\mu\,\,\,\nu}^{\,\,\,\lambda}$ to be the Christoffel symbols then it is called the **Levi-Civita connection**.

## Riemann tensor

The partial derivatives with respect to the coordinates commute:

$$
\left(\frac{\partial}{\partial x^\mu}\frac{\partial}{\partial x^\nu}-\frac{\partial}{\partial x^\nu}\frac{\partial}{\partial x^\mu}\right)(\text{\nything})=\left[\frac{\partial}{\partial x^\mu},\frac{\partial}{\partial x^\nu}\right]=0
$$

There is a natural question what is the commutator of two covariant derivatives $[\nabla_\mu,\nabla_\nu]=?$.

Let us first assume that we act with this commutator on a vector $v^\mu$:

$$
[\nabla_\mu,\nabla_\nu] v^\lambda=R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda} v^\kappa
$$

where $R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\lambda}$ is a tensor (by the quotient theorem). This tensor is called the **Riemann tensor** or the **curvature tensor**.

When acting with a commutator of covariant derivatives on other tensors we get a very similar behaviour. For example, for covectors:

$$
[\nabla_\mu,\nabla_\nu] \omega_\lambda=-R_{\mu\nu\,\,\,\lambda}^{\,\,\,\,\,\,\kappa} \omega_\kappa
$$

For tensors with more indices, we get a sum of terms with each summand corresponding to an index. For example:

$$
[\nabla_\mu,\nabla_\nu] T^\lambda_{\,\,\,\kappa}=R_{\mu\nu\,\,\,\kappa}^{\,\,\,\,\,\,\rho} T^\rho_{\,\,\,\kappa}-R_{\mu\nu\,\,\,\rho}^{\,\,\,\,\,\,\kappa} T^\kappa_{\,\,\,\rho}
$$
