# Week 3 (under development)

## Tensor calculus

In special relativity: Lorentz transformations

$$
x'^\mu=\Lambda^\mu_{\,\,\nu}x^\nu
$$

>picture

Similarly, a covector $\omega_\mu$ transforms via

$$
\omega'_{\mu}=(\Lambda^{-1})^\nu_{\,\,\mu}\omega_\nu
$$

Example: check that $v^\mu\omega_\mu$ is invariant, i.e. $v'^\mu\omega'_\mu=v^\mu\omega_\mu$:

$$
v'^\mu\omega'_\mu=(\Lambda^\mu_{\,\,\nu}v^\nu)((\Lambda^{-1})^\lambda_{\,\,\mu}\omega_\lambda)=(\Lambda^{-1})^\lambda_{\,\,\mu}\Lambda^\mu_{\,\,\nu} v^\mu\omega_\lambda=\delta^\lambda_\nu v^\nu\omega_\lambda=v^\lambda \omega_\lambda
$$

Tensors with more indices transform with one $\Lambda^\mu_{\,\,\nu}$ for each upper index and a $(\Lambda^{-1})^\kappa_{\,\,\nu}$ for each lower index.

Example: $T'^\mu_{\,\,\nu}=\Lambda^\mu_\lambda(\Lambda^{-1})^\kappa_{\,\,\nu}T^\lambda_{\,\,\kappa}$ that implies that $T^\mu_{\,\,\nu}v^\nu$ transforms like a vector (if $v^\mu$ is a vector).

In special relativity:
- $\Lambda^\mu_{\,\,\nu}$ is constant
- the lorentzian metric $\eta_{\mu\nu}=\begin{pmatrix}-1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1\end{pmatrix}$ is invariant

$$
\eta_{\mu\nu}=(\Lambda^{-1})^\lambda_{\,\,\mu}(\Lambda^{-1})^\kappa_{\,\,\nu}\eta_{\lambda\kappa}
$$

General coordinates: for example 2d polar coordinates

>picture

Distance between points:

$$
\delta s^2=\delta x^2+\delta y^2=\begin{pmatrix}\delta x&\delta y\end{pmatrix}\begin{pmatrix} 1&0\\0&1\end{pmatrix}\begin{pmatrix}\delta x\\\delta y\end{pmatrix}
$$

Write $x^1=x$ and $x^2=y$, then $\delta s^2=\delta_{ij}\delta x^i\delta x^j$. What about in $(r,\theta)$ coordinates? We can use the chain rule:

$$
\begin{align*}
\delta x=\frac{\partial x}{\partial r}\delta r+\frac{\partial x}{\partial \theta}\delta \theta\\
\delta y=\frac{\partial y}{\partial r}\delta r+\frac{\partial y}{\partial \theta}\delta \theta
\end{align*}
$$

or equivalently

$$
\begin{pmatrix} \delta x\\\delta y\end{pmatrix}=\begin{pmatrix}\frac{\partial x}{\partial r}&\frac{\partial x}{\partial \theta}\\\frac{\partial y}{\partial r}&\frac{\partial y}{\partial \theta}\end{pmatrix}\begin{pmatrix} \delta r\\\delta \theta\end{pmatrix}
$$

Writing $x'^{1}=r$ and $x'^{2}=\theta$, we have

$$
\delta x^i=\frac{\partial x^i}{\partial x'^j}\delta x'^j
$$

In our case we have

$$
\begin{align*}
x=r\cos\theta\\
y=r\sin\theta
\end{align*}
$$

and

$$
\begin{pmatrix} \delta x\\\delta y\end{pmatrix}=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}\begin{pmatrix} \delta r\\\delta \theta\end{pmatrix}
$$

If we denote by $J=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}$ we get

$$
\begin{align*}
\delta s^2&=\begin{pmatrix}\delta x&\delta y\end{pmatrix}\begin{pmatrix} 1&0\\0&1\end{pmatrix}\begin{pmatrix}\delta x\\\delta y\end{pmatrix}=
\begin{pmatrix}\delta r&\delta \theta\end{pmatrix}(J)^T\begin{pmatrix} 1&0\\0&1\end{pmatrix}(J)\begin{pmatrix}\delta r\\\delta \theta\end{pmatrix}\\
&=\begin{pmatrix}\delta r&\delta \theta\end{pmatrix}\begin{pmatrix} 1&0\\0&r^2\end{pmatrix}\begin{pmatrix}\delta r\\\delta \theta\end{pmatrix}=\delta r^2+r^2 \delta \theta^2
\end{align*}
$$

We can write it as

$$
\delta s^2=g'_{ij}\delta x'^i\delta x'^j
$$

with $(g'_{ij})=\begin{pmatrix}1&0\\0&r^2\end{pmatrix}$. Importantly, this matrix depends on position.

Note:

$$
g'_{ij}=\frac{\partial x^k}{\partial x'^i}\delta_{kl}\frac{\partial x^l}{\partial x'^j}
$$

Interpretation:

>picture

The right-hand side picture also describes 2d space, so long as we use $\delta s^2=\delta r^2+r^2\delta\theta^2$ to define distance!

We call $\delta s^2$ the **line element** and $g_{ij}$ are the components of the **metric**.

When we change coordinates:

$$
\delta x^i=\frac{\partial x^i}{\partial x'^j}\delta x'^j
$$

and

$$
g'_{ij}=g_{kl}\frac{\partial x^k}{\partial x'^i}\frac{\partial x^l}{\partial x'^j}
$$

Vectors:

> picture

Vector transformations:

$$
v'^\mu=\frac{\partial x'^\mu}{\partial x^\nu}v^\nu
$$

If we have $v^\mu(x)$ and $v'^\mu(x')$ satysfying the formula above, then $v^\mu(x)$ is a vector field.

Other tensor fields follow the same pattern as in special relativity. For example: covector field $\omega_\mu(x)$ has the transformation rule

$$
\omega'_{\mu}(x')=\frac{\partial x^\nu}{\partial x'^\mu}\Big|_x \omega_\nu(x)
$$

With these definitions the contraction $v^\mu\omega_mu$ is invariant: $v'^\mu\omega'_{\mu}=v^\mu\omega_\mu$, it is a scalar field.

A scalar field is a function that transforms as

$$
\phi'(x')=\phi(x)
$$

Exercise: check that $v^\mu\omega_\mu$ is invariant.

Important example: given a scalar field $\phi(x)$, the derivatives $\partial_\mu \phi=\frac{\partial\phi}{\partial x^\mu}$ are a covector. Proof:

$$
\partial'_\mu\phi'=\frac{\partial\phi'}{\partial x'^\mu}=\left(\frac{\partial x^\nu}{\partial x'^\mu}\frac{\partial}{\partial x^\nu}\right)\phi=\left(\frac{\partial x^\nu}{\partial x'^{\mu}}\right)\partial_\nu\phi
$$

This means that given a vector $x^\mu$, the derivative of $\phi$ along $v^\mu$, that is $v^\mu\partial_\mu\phi$ is a scalar field.

Definition: $T^{\mu_1\ldots\mu_m}_{\nu_1\ldots\nu_n}$ is a tensor if

$$
T'^{\mu_1\ldots\mu_m}_{\nu_1\ldots\nu_n}=\left(\frac{\partial x'^{\mu_1}}{\partial x^{\lambda_1}}\ldots\frac{\partial x'^{\mu_m}}{\partial x^{\lambda_m}}\right)\left(\frac{\partial x^{\kappa_1}}{\partial x'^{\nu_1}}\ldots\frac{\partial x^{\kappa_m}}{\partial x'^{\nu_m}}\right)T^{\lambda_1\ldots\lambda_m}_{\kappa_1\ldots\kappa_n}
$$

Philosophy: only tensor quantities are *physical*. We want to describe physics in a coordinate invariant way.

>Tensor equations are true in all coordinate systems if they are true in any one.

Some tensors can have components which are invariant:

$$
\delta^\mu_\nu=\begin{cases}1,&\mu=\nu\\0,&\textnormal{otherwise}\end{cases}
$$

is invariant since

$$
\delta'^{\mu}_\nu=\frac{\partial x'^\mu}{\partial x^\lambda}\frac{\partial x^\kappa}{\partial x'^\nu}\delta^\lambda_\kappa=\frac{\partial x'^\mu}{\partial x^\lambda}\frac{\partial x^\lambda}{\partial x'^\nu}=\frac{\partial x'^\mu}{\partial x^\nu}=\delta^\mu_\nu
$$

## Metric tensor

Two properties:
- symmetric $g_{\mu\nu}=g_{\nu\mu}$
- non-degenerate $\det g_{\mu\nu}\neq0$

The metric tensor defines a line element

$$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu
$$

Invariant because $dx^\mu$ and $g_{\mu\nu}$ are tensors and you have contracted indices.
- $g$ has *signature* $(-,+,+,+)$, that is you can diagonalise $g$ to get $\begin{pmatrix}-1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1\end{pmatrix}$.

Since $\det(g)\neq 0$ then the inverse $g^{-1}$ exists. Write $(g^{-1})^{\mu\nu}=g^{\mu\nu}$. It is also a tensor.

We can raise and lower indices with $g_{\mu\nu}$ and $g^{\mu\nu}$. For example: if we have $T_{\mu\nu}$ then $T^{\mu}_{\,\,\nu}=g^{\mu\lambda}T_{\lambda\nu}$, and similarly we have for example $X_{\mu\nu\lambda}=g_{\mu\kappa}X^\kappa_{\,\,\nu\lambda}$. Because $g_{\mu\nu}$, $g^{\mu\nu}$ and $T_{\mu\nu}$ are tensors then also $T^{\mu}_{\,\,\nu}$ defines as a contraction is also a tensor.

## Finite distances/intervals

Suppose we have a (curved) path with parameter $\lambda$:

>picture

Define $ds=\sqrt{|g_{\mu\nu}(x)dx^\mu dx^\nu|}$. For a timelike path $ds^2<0$ along the path so $ds=\sqrt{-g_{\mu\nu} dx^\mu dx^\nu}=d\tau$. For a spacelike path $ds^2>0$ so $ds=\sqrt{g_{\mu\nu} dx^\mu dx^\nu}$.

>picture

The length/interval along the finite path is:

$$
S=\int ds=\int \sqrt{|g_{\mu\nu}\dot{x}^\mu \dot{x}^\nu|}d\lambda
$$

Exercise: If we choose a different parameter $\tilde\lambda$, show that we get the same answer for $S$.

Exercise: Say $y^\mu=x^\mu+\epsilon\,\zeta^\mu(x)$ such that $g_{\lambda\kappa}(y)\frac{\partial y^\lambda}{\partial x^\mu}\frac{\partial y^\kappa}{\partial x^\nu}=g_{\mu\nu}(x)$. Show that

$$
\zeta^\lambda\partial_\lambda g_{\mu\nu}+(\partial_\mu \zeta^\lambda)g_{\lambda\nu}+(\partial_\nu \zeta^\lambda)g_{\mu\lambda}=0
$$
