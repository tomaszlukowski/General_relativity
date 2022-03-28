# Week 10

## Cosmological Horizons

Consider the cosmological metric

$$
ds^2=a^2(-d\sigma^2+d\vec{x}^2)\,.
$$

Suppose the universe begins in a *Big Bang* at $\sigma=0$ when $a(0)=0$. We now sit at a point $\vec{x}_0$ in space at a finite value of $\sigma$. The coordinates $\vec{x}=(x,y,z)$ have infinite range, i.e. $-\infty<x,y,z<\infty$. This means that the spatial slice of the universe at fixed $\sigma$ has infinite size. But how much of the universe can we actually see? To answer this question, we must consider which parts of the universe we can have received light signals from:

```{image} ../Week10_pictures/week10_picture1.png
:class: bg-primary mb-1
:width: 500px
:align: center
```

Suppose we are at $\vec{x}=\vec{0}$ and consider a light ray coming towards us from the positive $x$-direction.

```{image} ../Week10_pictures/week10_picture2.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

At $\sigma=0$ we have $x_0=\sigma_0$. Only events in the purple shaded region can possibly influence our state at $\sigma=\sigma_0$.

The surface in spacetime made by the paths of the red photons is called the **particle horizon**.

At time $\sigma_0$, the particle horizon is at $|\vec{x}|=\sigma_0$.

```{image} ../Week10_pictures/week10_picture3.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

We can calculate the physical distance to the furthest visible object:

$$
\Delta s=a(\sigma_0)\Delta x=a(\sigma_0)\sigma_0\,.
$$

In terms of the time coordinate $t$ (assuming $t=0$ when $\sigma=0$ and $t=t_0$ when $\sigma=\sigma_0$) we have:

$$
\Delta s=a(\sigma_0)\int_0^{t_0}\frac{dt}{a(t)}\,.
$$

We cannot see objects that are further away than this.

## Event horizons

Similarly, we can consider which events in spacetime will ever be able to influence us, if we follow a timelike geodesic path. In particular, it may be that light rays from some events will never reach us. The formal way to see this is to change coordinates such that the metric in the radial direction becomes:

$$
ds^2=F(T,R)^2\left[-dT^2+dR^2\right]\,,
$$

where finite ranges of $T$ and $R$ cover all of spacetime. This allows us to draw all of spacetime including *infinity* in the space and time directions. Also because $ds^2=0$ then $-dT^2+dR^2=0$. Light rays will travel along $45^\circ$ straight lines in the $(T,R)$-plane.

The picture of the Minkowski space is

```{image} ../Week10_pictures/week10_picture4.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

At any point inside the triangle, you can draw a light ray that will intersect the path of the timelike geodesic observer at some point in the future.

However, this is not generically true.

For some spacetimes, the line of *finite infinity* is spacelike. In such case, the picture becomes

```{image} ../Week10_pictures/week10_picture5.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

As signals can travel at the speed of light at most, events outside the shaded region cannot influence the observer.

The boundary (in spacetime) of the shaded region is called **future event horizon**.

Similarly, the line of *past infinity* can be spacelike.

```{image} ../Week10_pictures/week10_picture6.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

In this case the boundary of the shaded region is called a **past event horizon**.

Note that also the lifetime of the universe could be finite. In those cases $t=\pm \infty$ are replaced by the finite values of $t$ at the Big Bang and Big Crunch.

## Examples of Horizons

Consider the two spacetimes (for $t>0$):

$$
ds^2_1=-dt^2+t^2 dx^2\,,\qquad\qquad ds_2^2=-dt^2+t^4 dx^2\,.
$$

Our goal is to:
- find the equations of generic null geodesics and draw graphs of typical light rays,
- deduce what horizons are present (if any),
- calculate what values of the conformal time $\sigma$ are possible,
- deduce what the finite picture of these spacetimes should look like.

### Null geodesics

We want to solve the equation $ds^2=0$:

- for the metric $ds_1$:

$$
\boxed{-dt^2+t^2 dx^2=0}\quad\Rightarrow\quad \boxed{dt=\pm tdx}\quad\Rightarrow\quad\boxed{\pm\int dx=\int \frac{dt}{t}}\quad\Rightarrow\quad \boxed{\pm(x-x_0)=\log\frac{t}{t_0}}\quad\Rightarrow\quad \boxed{t=t_0 e^{\pm(x-x_0)}}
$$

```{image} ../Week10_pictures/week10_picture7.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

Light rays from $(t_0,x_0)$ can reach $x=\pm \infty$ as $t\to\infty$ or $t\to 0$. There are no horizons in this case.

- for the metric $ds_2$:

$$
\boxed{-dt^2+t^4 dx^2=0}\quad\Rightarrow\quad \boxed{dt=\pm t^2 dx}\quad\Rightarrow\quad \boxed{\pm \int_{x_0}^{x}dx=\int_{t_0}^t dt}\quad\Rightarrow\quad \boxed{\pm(x-x_0)=\frac{1}{t_0}-\frac{1}{t}}
$$

and finally we find

$$
t=\frac{1}{\frac{1}{t_0}\pm(x-x_0)}=\frac{t_0}{1\pm t_0(x-x_0)}\,.
$$

```{image} ../Week10_pictures/week10_picture8.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

As $x\to\pm\infty$ we have $t\to 0$. For the "+" solution, the denominator is zero at $(x-x_0)=-\frac{1}{t_0}$. For the "-" solution, the denominator is zero at $(x-x_0)=\frac{1}{t_0}$.

As $t\to 0$ the light ray can reach any value of $x$. This means that there is no past horizon. As $t\to\infty$, light rays from $(x_0,t_0)$ are bounded to the inside $x_0-\frac{1}{t_0}<x<x_0+\frac{1}{t_0}$. Signals will never reach values of $x$ outside this region. This means that there is a future event horizon.

```{image} ../Week10_pictures/week10_picture9.png
:class: bg-primary mb-1
:width: 400px
:align: center
```

### Conformal time

Recap: for cosmological geometries, the metric using conformal time is

$$
ds^2=a^2(-d\sigma^2+dx^2)\,.
$$

For null geodesics: $ds^2=0$ therefore $d\sigma=\pm dx$.

- for the metric $ds_1$:

In this case $a(t)=t$ and we find

$$
\int d\sigma=\int\frac{dt}{t}=\log\frac{t}{t_0}\,.
$$

Let us choose $\sigma_0$ when $t_0=1$. Then

$$
\sigma=\log(t) \quad\Rightarrow\quad t=e^\sigma\,.
$$

We have $0<t<\infty$ and therefore $-\infty<\sigma<\infty$. The light rays in $(\sigma,x)$ plane are

```{image} ../Week10_pictures/week10_picture10.png
:class: bg-primary mb-1
:width: 500px
:align: center
```

- for the metric $ds_2$:

In this case $a(t)=t^2$ and thefore

$$
d\sigma=\frac{dt}{t^2}\quad\Rightarrow\quad \sigma-\sigma_0=\frac{1}{t_0}-\frac{1}{t}\,.
$$

Again, choose $\sigma_0=0$ when $t_0=1$. Then

$$
\sigma=1-\frac{1}{t}\,.
$$

In this case when $0<t<\infty$, we get $-\infty <\sigma<1$.

```{image} ../Week10_pictures/week10_picture11.png
:class: bg-primary mb-1
:width: 500px
:align: center
```
