# Week 3

## Tensor calculus

In Special Relativity inertial frames are related by Lorentz transformations:

$$
x'^\mu=\Lambda^\mu_{\,\,\nu}x^\nu\,.
$$

```{image} ../Week3_pictures/week3_picture1.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

Coordinate transformations induce transformations on the components of four-vectors and tensors. For example, a four-vector with components $v^\mu$ in the $x^\mu$-coordinates has components

$$
v'^\mu=\Lambda^\mu_{\,\,\nu}v^\nu\,,
$$

in the $x'^\mu$-coordinates. Similarly, a covector $\omega_\mu$ transforms via

$$
\omega'_{\mu}=(\Lambda^{-1})^\nu_{\,\,\mu}\omega_\nu\,,
$$

such that the contraction $v^\mu\omega_\nu$ is invariant, i.e. $v'^\mu\omega'_\mu=v^\mu\omega_\mu$:

$$
v'^\mu\omega'_\mu=(\Lambda^\mu_{\,\,\nu}v^\nu)((\Lambda^{-1})^\lambda_{\,\,\mu}\omega_\lambda)=(\Lambda^{-1})^\lambda_{\,\,\mu}\Lambda^\mu_{\,\,\nu} v^\mu\omega_\lambda=\delta^\lambda_\nu v^\nu\omega_\lambda=v^\lambda \omega_\lambda\,.
$$

When tensors with more indices are considered, they transform with one factor $\Lambda^\mu_{\,\,\nu}$ for each upper index and one factor $(\Lambda^{-1})^\kappa_{\,\,\nu}$ for each lower index. As a simple example, let us take a rank-2  tensor $T^\mu_{\,\,\,\nu}$. Then

$$
T'^\mu_{\,\,\,\,\nu}=\Lambda^\mu_{\,\,\lambda}(\Lambda^{-1})^\kappa_{\,\,\nu}T^\lambda_{\,\,\,\kappa}\,.
$$

This in particular implies that the combination $T^\mu_{\,\,\nu}\,v^\nu$ transforms as a vector under Lorentz transformations (if $v^\mu$ is a vector).

Importantly, in Special Relativity:
- the matrix $\Lambda^\mu_{\,\,\nu}$ does not depend on position,
- the Lorentzian metric

  $$
  \eta_{\mu\nu}=\begin{pmatrix}-1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1\end{pmatrix},$$

  is invariant under Lorentz transformations:

$$
\eta_{\mu\nu}=(\Lambda^{-1})^\lambda_{\,\,\mu}(\Lambda^{-1})^\kappa_{\,\,\nu}\eta_{\lambda\kappa}\,.
$$

These two features will no longer be true when we generalise to general coordinate trnasformations.

## General coordinate transformations

We would like to write the laws of physics in a way that makes no reference to the choice of coordinates used to parametrise space-time. This requires tensor calculus in general coordinate systems.

Let us consider a simple example of two-dimensional polar coordinates:

```{image} ../Week3_pictures/week3_picture2.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

In standard Euclidean geometry the distance $\delta s^2$ between the nearby points can be calculated as:

$$
\delta s^2=\delta x^2+\delta y^2=\begin{pmatrix}\delta x&\delta y\end{pmatrix}\begin{pmatrix} 1&0\\0&1\end{pmatrix}\begin{pmatrix}\delta x\\\delta y\end{pmatrix}.
$$

Writing $x^1=x$ and $x^2=y$ this is

$$
\delta s^2=\delta_{ij}\delta x^i\delta x^j\,.
$$

A natural question is what happens if we try to rewrite this expresions in $(r,\theta)$ polar coordinates? To do that, we can use the chain rule to find:

$$
\begin{align*}
\delta x=\frac{\partial x}{\partial r}\delta r+\frac{\partial x}{\partial \theta}\delta \theta\,,\\
\delta y=\frac{\partial y}{\partial r}\delta r+\frac{\partial y}{\partial \theta}\delta \theta\,.
\end{align*}
$$

This can be equivalently written using matrix notation as:

$$
\begin{pmatrix} \delta x\\\delta y\end{pmatrix}=\begin{pmatrix}\frac{\partial x}{\partial r}&\frac{\partial x}{\partial \theta}\\\frac{\partial y}{\partial r}&\frac{\partial y}{\partial \theta}\end{pmatrix}\begin{pmatrix} \delta r\\\delta \theta\end{pmatrix}.
$$

If we now write $x'^{1}=r$ and $x'^{2}=\theta$, then the infinitesimal distances along each directions can be related in the two coordinate systems:

$$
\delta x^i=\frac{\partial x^i}{\partial x'^j}\delta x'^j\,.
$$

Using the exact expressions for polar coordinates:

$$
\begin{cases}
x=r\cos\theta,\\
y=r\sin\theta,
\end{cases}
$$

this leads to the following relation:

$$
\begin{pmatrix} \delta x\\\delta y\end{pmatrix}=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}\begin{pmatrix} \delta r\\\delta \theta\end{pmatrix}.
$$

If we denote by $J=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}$, then we can write

$$
\begin{align*}
\delta s^2&=\begin{pmatrix}\delta x&\delta y\end{pmatrix}\begin{pmatrix} 1&0\\0&1\end{pmatrix}\begin{pmatrix}\delta x\\\delta y\end{pmatrix}=
\begin{pmatrix}\delta r&\delta \theta\end{pmatrix}(J)^T\begin{pmatrix} 1&0\\0&1\end{pmatrix}(J)\begin{pmatrix}\delta r\\\delta \theta\end{pmatrix}\\
&=\begin{pmatrix}\delta r&\delta \theta\end{pmatrix}\begin{pmatrix} 1&0\\0&r^2\end{pmatrix}\begin{pmatrix}\delta r\\\delta \theta\end{pmatrix}=\delta r^2+r^2 \delta \theta^2\,.
\end{align*}
$$

It is not the flat metric in $(r,\theta)$-variables because of the $r^2$ term in front of $\delta \theta^2$. Using index notation this can be written as:

$$
\delta s^2=g'_{ij}\delta x'^i\delta x'^j\,,
$$

with $(g'_{ij})=\begin{pmatrix}1&0\\0&r^2\end{pmatrix}$. Importantly, components of this matrix depend on position!

Finally, let us note that:

$$
g'_{ij}=\frac{\partial x^k}{\partial x'^i}\delta_{kl}\frac{\partial x^l}{\partial x'^j}\,.
$$

We can give an interpretation to the calculations above. We are used to thinking of polar coordinates like this:

```{image} ../Week3_pictures/week3_picture3.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

But we could simply look at a plane with axes $r$ and $\theta$

```{image} ../Week3_pictures/week3_picture4.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

This plane also describes the geometry of the usual $(x,y)$ plane so long as we use $\delta s^2=\delta r^2+r^2\delta\theta^2$ to define the notion of distance (the metric)!

In any coordinates we can write $\delta s^2=g_{ij}\delta x^i\delta^j$, where we call $\delta s^2$ the **line element** and $g_{ij}$ are the components of the **metric tensor**.

If we now consider two sets of general coordinates $x^i$ and $x'^i$ then a change of coordinates can be written in general form as:

$$
\delta x^i=\frac{\partial x^i}{\partial x'^j}\delta x'^j\,,
$$

and

$$
g'_{ij}=g_{kl}\frac{\partial x^k}{\partial x'^i}\frac{\partial x^l}{\partial x'^j}\,.
$$

Another example is given by a two-sphere with radius $R$ in $\mathbb{R}^3$. We will use spherical polar coordinates $(\theta,\phi)$ (there are two coordinates as this is a two-dimensional surface).

```{image} ../Week3_pictures/week3_picture7.png
:class: bg-primary mb-1
:width: 500px
:align: center
```

Now we want to ask the question: what is the metric in the left pictures which corresponds to the usual notion of distance in the right picture?

We start from a three-dimensional Euclidean space with line element $\delta s^2=\delta x^2+\delta y^2+\delta z^2$ and use the explicit form for the transformation to spherical coordinates:

$$
\begin{cases}x=R \sin\theta\cos\phi\,,\\
y=R\sin\theta\sin\phi\,,\\
z=R\cos\theta\,.\end{cases}
$$

Then

$$
\begin{pmatrix}\delta x\\\delta y\\\delta z\end{pmatrix}=\begin{pmatrix}\frac{\partial x}{\partial \theta}&\frac{\partial x}{\partial \phi}\\
\frac{\partial y}{\partial \theta}&\frac{\partial y}{\partial \phi}\\
\frac{\partial z}{\partial \theta}&\frac{\partial z}{\partial \phi}\end{pmatrix}
\begin{pmatrix}\delta \theta\\\delta \phi\end{pmatrix}=
\begin{pmatrix}R\cos\theta\cos\phi&-R\sin\theta\sin\phi\\
R\cos\theta\sin\phi&R\sin\theta\cos\phi\\
-R\sin\theta&0\end{pmatrix}
\begin{pmatrix}\delta \theta\\\delta \phi\end{pmatrix},
$$

and

$$
\delta s^2=\begin{pmatrix}\delta x&\delta y&\delta z\end{pmatrix}\begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix}\begin{pmatrix}\delta x\\\delta y\\\delta z\end{pmatrix}=\begin{pmatrix}\delta \theta&\delta \phi\end{pmatrix}\begin{pmatrix}R^2&0\\0&R^2\sin^2\theta\end{pmatrix}\begin{pmatrix}\delta \theta\\\delta \phi\end{pmatrix}.
$$

In other words:

$$
\delta s^2=R^2(\delta \theta^2+\sin^2\theta\delta\phi^2)
$$

is the metric that we were looking for.
### Vectors

In Cartesian coordinates we have the usual basis vectors $\hat{e}_x$ and $\hat{e}_y$:

```{image} ../Week3_pictures/week3_picture5.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

If we increase the $x$-coordinate by $\delta x$ then we need to move by vector $\hat{e}_x \delta x$. Can we do the same thing in polar coordinates?

```{image} ../Week3_pictures/week3_picture6.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

As before, if we increase $r$ by $\delta r$ then we need to move along the vector $\hat{e}_r$ by $\hat{e}_r\delta r$. Similarly, if we increase the $\theta$ coordinate. The relation between the two pictures is:

$$
\begin{cases}\hat{e}_r\delta r=(\cos\theta \hat{e}_x+\sin\theta\hat{e}_y)\delta r\,,\\
\hat{e}_\theta\delta \theta=(-r\sin\theta \hat{e}_x+r\cos\theta\hat{e}_y)\delta \theta\,.\end{cases}
$$

Given a vector $\vec{v}$ at the point $(x,y)$ (or polar coordinates $(r,\theta)$) we can expand it either in terms of $\hat{e}_x$ and $\hat{e}_y$, or in terms of $\hat{e}_r$ and $\hat{e}_\theta$:

$$
\vec{v}=v_x \hat{e}_y+v_x \hat{e}_y=v_r \hat{e}_r+v_\theta \hat{e}_\theta\,,
$$

which in the matrix form is

$$
\begin{pmatrix}v_x\\v_y\end{pmatrix}=\begin{pmatrix}\cos\theta&-r\sin\theta\\\sin\theta&r\cos\theta\end{pmatrix}\begin{pmatrix}v_r\\v_\theta\end{pmatrix},
$$

or in the index notation:

```{math}
:label: eq_vector_transform
v^i=\frac{\partial x^i}{\partial x'^j}v'^j\,.
```


Importantly, the matrix $\frac{\partial x^i}{\partial x'^j}$ depends on **where** the vector is located! This is because e.g. $\hat{e}_r$ is not always pointing in the same direction (in terms of $\hat{e}_x$ and $\hat{e}_y$).

In Special Relativity, the coordinate transformation was linear:

$$
\boxed{x'^\mu=\Lambda^\mu_{\,\,\nu}x^\nu}\,\,\Rightarrow \,\, \frac{\partial x'^\mu}{\partial x^\nu}=\Lambda^\mu_{\,\,\nu}=const\,.
$$

This was why the tensor transformation matrix $\Lambda^\mu_{\,\,\nu}$ was constant. For general (non-linear) coordinate transformations $\Lambda^\mu_{\,\,\nu}$ is replaced by $\frac{\partial x'^\mu}{\partial x^\nu}$ which depends on position.

Note that

$$
\frac{\partial x'^\mu}{\partial x^\nu}\frac{\partial x^\nu}{\partial x'^\lambda}=\frac{\partial x'^\mu}{\partial x'^\lambda}=\delta^\mu_{\lambda}\,,
$$

so $\frac{\partial x^\mu}{\partial x'^\nu}$ and $\frac{\partial x'^\mu}{\partial x^\nu}$ are inverses. In other words, if we want to invert the the vector transformation formula [](eq_vector_transform) then we get

$$
v'^\mu=\frac{\partial x'^\mu}{\partial x^\nu}v^\nu\,.
$$

If we have $v^\mu(x)$ and $v'^\mu(x')$ satysfying the formula above, then $v^\mu(x)$ is a **vector field**.



### Tensors

Other tensor fields follow the same pattern as in Special Relativity. Let $x^\mu$ and $x'^\mu$ be two different sets of coordinates on (a patch of) spacetime. As they are both sets of coordinates, we can write

$$
x'^\mu=x'^\mu(x),\qquad\qquad x^\mu=x^\mu(x')\,,
$$

which means that $x'^\mu$ is some function which gives $x'^\mu$ for a given point if we know $x^\mu$ for it. Then the inverse function $x^\mu$ gives $x$ from $x'$.

As a familiar example let us take the two-dimensional Euclidean space parametrised with $(x,y)$ or $(r,\theta)$ and then these functions are:

$$
\begin{cases}x=r\cos\theta\,,\\y=r\sin\theta\,,\end{cases}\qquad\qquad \begin{cases}r=\sqrt{x^2+y^2}\,,\\\theta=\tan^{-1}\left(\frac{x}{y}\right)\,.\end{cases}
$$

We can then construct the matrices:

$$
\frac{\partial x^\mu}{\partial x'^\nu}\qquad\textnormal{and}\qquad \frac{\partial x'^\mu}{\partial x^\nu}\,.
$$

These are position dependent in general and inverse to each other.

```{admonition} Definition of a vector
A quantity which has components $v^\mu(x)$ with respect to the coordinates $x^\mu$ and components $v'^\mu(x')$ with respect to the coordinates $x'^\mu$ is called a **vector** if

$$
v'^\mu(x')=\frac{\partial x'^\mu}{\partial x^\nu}\Big|_x v^\nu(x)\,.
$$
```

```{image} ../Week3_pictures/week3_picture8.png
:class: bg-primary mb-1
:width: 500px
:align: center
```

We know $x'^\mu$ as functions of the $x^\mu$, we can therefore find $\frac{\partial x'^\mu}{\partial x^\nu}$ by differentiation. Evaluating this at the point $x_0^\mu$ gives a matrix $M^\mu_{\,\,\nu}=\frac{\partial x'^\mu}{\partial x^\nu}\Big|_{x_0}$. This matrix transforms the components of a vector at the point $x_0$ in the two coordinate systems as

$$
v'^\mu=M^\mu_{\,\,\nu}v^\nu\,.
$$

```{admonition} Definition of a vector field
If $v^\mu(x)$ are smooth functions of $x^\mu$, and $v'^\mu(x')$ are smooth functions of $x'$ such that

$$
v'^\mu(x')=\frac{\partial x'^\mu}{\partial x^\nu}\Big|_x v^\nu(x)\,,
$$

then $v$ is called a **vector field**.
```

Other tensor fields are defined similarly

```{admonition} Definition of a covector
An object with components $\omega_\mu(x)$ and $\omega'_\mu(x')$ in the same setup as above is a **covector field** (or 1-form field) if

$$
\omega'_\mu(x')=\frac{\partial x^\nu}{\partial x'^\mu}\Big|_{x'}\omega_\nu(x)
$$
```
Note that the covector field transform with the inverse of the matrix for the vectors. With these definitions, the contraction $v^\mu\omega_\mu$ is invariant: $v'^\mu\omega'_{\mu}=v^\mu\omega_\mu$, it is a scalar field.

```{admonition}
A scalar field is a well-defined function with no trnsformation, namely

$$
\phi'(x')=\phi(x)
$$

```

```{admonition} Exercise
:class: warning
Check that $v^\mu\omega_\mu$ is invariant.
```

Important example: given a scalar field $\phi(x)$, the partial derivatives $\partial_\mu \phi=\frac{\partial\phi}{\partial x^\mu}$ are a covector. Proof:

$$
\partial'_\mu\phi'=\frac{\partial\phi'}{\partial x'^\mu}=\left(\frac{\partial x^\nu}{\partial x'^\mu}\frac{\partial}{\partial x^\nu}\right)\phi=\left(\frac{\partial x^\nu}{\partial x'^{\mu}}\right)\partial_\nu\phi\,.
$$

Therefore, given a vector $v^\mu$, the derivative of $\phi$ along $v^\mu$, that is $v^\mu\partial_\mu\phi$ is a scalar field.


```{admonition} Definition of a tensor

$T^{\mu_1\ldots\mu_m}_{\nu_1\ldots\nu_n}$ is a tensor if

$$
T'^{\mu_1\ldots\mu_m}_{\nu_1\ldots\nu_n}=\left(\frac{\partial x'^{\mu_1}}{\partial x^{\lambda_1}}\ldots\frac{\partial x'^{\mu_m}}{\partial x^{\lambda_m}}\right)\left(\frac{\partial x^{\kappa_1}}{\partial x'^{\nu_1}}\ldots\frac{\partial x^{\kappa_m}}{\partial x'^{\nu_m}}\right)T^{\lambda_1\ldots\lambda_m}_{\kappa_1\ldots\kappa_n}\,.
$$

```

The general philosophy is that only tensor quantities are *physically meaningful* since we want to describe physics in a coordinate invariant way.

```{Important}
Tensor equations are true in all coordinate systems if they are true in any one.
```

Some tensors can have components which are invariant. For example

$$
\delta^\mu_\nu=\begin{cases}1,&\mu=\nu\,,\\0,&\textnormal{otherwise}\,,\end{cases}
$$

is invariant since

$$
\delta'^{\mu}_\nu=\frac{\partial x'^\mu}{\partial x^\lambda}\frac{\partial x^\kappa}{\partial x'^\nu}\delta^\lambda_\kappa=\frac{\partial x'^\mu}{\partial x^\lambda}\frac{\partial x^\lambda}{\partial x'^\nu}=\frac{\partial x'^\mu}{\partial x^\nu}=\delta^\mu_\nu\,.
$$

This is the same reason why $v^\mu \omega_\mu$ is invariant!

## Symmetry and antisymmetry

We can symmetrise or anti-symmetrise indices of tensors if they are on the same level (up or down). For example, given a tensor $T_{\mu\nu}$ we can define two new tensors:

$$
\begin{align*}
T_{[\mu\nu]}=\frac{1}{2}\left(T_{\mu\nu}-T_{\nu\mu}\right)=: A_{\mu\nu}\,,\\
T_{(\mu\nu)}=\frac{1}{2}\left(T_{\mu\nu}+T_{\nu\mu}\right)=: S_{\mu\nu}\,,
\end{align*}
$$

which are the anti-symmetric and symmetric combinations of the tensor $T_{\mu\nu}$.

We have the following simple properties of the new tensors:

$$
\begin{align*}
&A_{\mu\nu}=A_{[\mu\nu]},\qquad A_{\mu\nu}=-A_{\nu\mu}\,,\\
&S_{\mu\nu}=S_{(\mu\nu)},\qquad S_{\mu\nu}=S_{\nu\mu}\,.
\end{align*}
$$

Furthermore, any tensor can be decomposed into its symmetric and antisymmetrix part

$$
T_{\mu\nu}=T_{[\mu\nu]}+T_{(\mu\nu)}\,.
$$

We call the tensor $A_{\mu\nu}$ the antisymmetrisation of $T_{\mu\nu}$ and the tensor $S_{\mu\nu}$ the symmetrisation of $T_{\mu\nu}$.

There are more complicated examples that we can construct if we have tensors with more indices. For example:

$$
R_{[\mu\nu][\lambda\kappa]}=\frac{1}{2}\left(R_{\mu\nu[\lambda\kappa]}-R_{\nu\mu[\lambda\kappa]}\right)=\frac{1}{4}\left(R_{\mu\nu\lambda\kappa}-R_{\mu\nu\kappa\lambda}+R_{\nu\mu\kappa\lambda}-R_{\nu\mu\lambda\kappa}\right)\,.
$$

We can also define an (anti)-symmetrisation of more than two indices. For example:

$$
X_{[\mu\nu\lambda]}=\frac{1}{3!}\left(X_{\mu\nu\lambda}+X_{\nu\lambda\mu}+X_{\lambda\mu\nu}-X_{\nu\mu\lambda}-X_{\mu\lambda\nu}-X_{\lambda\nu\mu}\right)\,.
$$

If we set $A_{\mu\nu\lambda}=X_{[\mu\nu\lambda]}$ and $S_{\mu\nu\lambda}=X_{(\mu\nu\lambda)}$ then $A_{\mu\nu\lambda}=-A_{\nu\mu\lambda}$ and $S_{\mu\nu\lambda}=S_{\nu\mu\lambda}$.

```{note}
If we antisymmetrise a symmetric tensor, we get zero. Also, if we contract symmetric indices with antisymmetric indices then the answer is zero!
```

For example: if $A_{\,\,\mu\nu}^{\lambda}=A_{\,\,[\mu\nu]}^{\lambda}$ and $B^{\mu\nu\lambda}=B^{(\mu\nu\lambda)}$ then $B^{\mu\nu\lambda}A_{\,\,\nu\lambda}^\kappa=0$.

Moreover, if we antisymmetrise the indices of a tensor that is already symmetric in these indices then we also get zero. For example, of $g_{\mu\nu}=g_{(\mu\nu)}$ the $g_{\mu\nu}=\frac{1}{2}\left(g_{\mu\nu}-g_{\nu\mu}\right)=\frac{1}{2}\left(g_{\mu\nu}-g_{\mu\nu}\right)=0$.

We conclude this section with an important statement that will be used later in these lectures:

```{admonition} Important theorem

If we have $A\cdot B=C$ where $C$ is a tensor for any tensor $B$ then this implies that $A$ is a tensor.
```

## Metric tensor

A rank-two covariant tensor $g_{\mu\nu}$ can define a metric tensor if it satisfies the folllowing two properties:
- it is symmetric $g_{\mu\nu}=g_{\nu\mu}=g_{(\mu\nu)}$,
- it is non-degenerate $\det g_{\mu\nu}\neq0$.

We can then define a line element

$$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu\,,
$$

which gives a notion of distance on a coordinate system. The small coordinate shift $dx^\mu$ defines a vector as

$$
dx'^\mu=\frac{\partial x'^\mu}{\partial x^\nu}dx^\nu\,,
$$

and therefore the contraction $ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu$ is a well-defined scalar giving an invariant notion of the length of the displacement.

To be more precise, we should also insist that $g_{\mu\nu}$ has fixed *signature*, that is the same number of positive and negative eigenvalues everywhere. For Euclidean geometries, length is always positive so all eigenvalues are positive. In relativity, we want the eigenvalues to have signs $(-,+,+,+)$.

The requirement $\det(g_{\mu\nu})\neq 0$ implies that the inverse matrix exists, which gives a tensor written as $(g^{-1})^{\mu\nu}=g^{\mu\nu}$. Since $g^{\mu\nu}g_{\nu\lambda}=\delta^\mu_{\,\,\lambda}$, then $g^{\mu\nu}$ is also a tensor.

As in Special Relativity, we can raise and lower indices with $g_{\mu\nu}$ and $g^{\mu\nu}$. For example: if we have $T_{\mu\nu}$ then $T^{\mu}_{\,\,\nu}=g^{\mu\lambda}T_{\lambda\nu}$, and similarly we have for example $X_{\mu\nu\lambda}=g_{\mu\kappa}X^\kappa_{\,\,\nu\lambda}$. Because $g_{\mu\nu}$, $g^{\mu\nu}$ and $T_{\mu\nu}$ are tensors then also $T^{\mu}_{\,\,\nu}$ defines as a contraction is also a tensor.

## Finite distances/intervals

Suppose we have a (curved) path with parameter $\lambda$:

```{image} ../Week3_pictures/week3_picture9.png
:class: bg-primary mb-1
:width: 500px
:align: center
```

Given a metric tensor $g_{\mu\nu}$ we define the infinitesimal length of $dx^\mu$ to be $ds=\sqrt{|g_{\mu\nu}(x)dx^\mu dx^\nu|}$. For a timelike path $ds^2<0$ along the path so $ds=\sqrt{-g_{\mu\nu} dx^\mu dx^\nu}=d\tau$. For a spacelike path $ds^2>0$, so $ds=\sqrt{g_{\mu\nu} dx^\mu dx^\nu}$.

Then we define the length/interval along the paths

$$
S=\int ds=\int_{\lambda=\lambda_1}^{\lambda=\lambda_2} d\lambda \sqrt{|g_{\mu\nu}(x)\dot{x}^\mu \dot{x}^\nu|}\,,
$$

where $\dot{x}^\mu=\frac{dx^\mu}{d\lambda}$.

```{admonition} Exercise
:class: warning
Show that if we choose a different parameter $\tilde\lambda$ then we get the same answer for $S$.
```

```{admonition} Exercise
:class: warning
Say $y^\mu=x^\mu+\epsilon\,\zeta^\mu(x)$ such that $g_{\lambda\kappa}(y)\frac{\partial y^\lambda}{\partial x^\mu}\frac{\partial y^\kappa}{\partial x^\nu}=g_{\mu\nu}(x)$. Show that

$$
\zeta^\lambda\partial_\lambda g_{\mu\nu}+(\partial_\mu \zeta^\lambda)g_{\lambda\nu}+(\partial_\nu \zeta^\lambda)g_{\mu\lambda}=0
$$
```
