# Week 9 (under construction)

## Cosmological spacetimes

We want to think about the Universe as a whole. The Universe is build out of start and galaxies, but if we zoom out then they appear as a smooth fluid (like molecules in a glass of water). At large scales the Universe has two remarkable properties:
- isotropic (looks the same independent of the direction we look)
- homogeneous (looks the same wherever we go)

```{admonition} Theorem
:class: tip

These two properties imply that

$$
ds^2=-dt^2+a(t)^2(h_{ij}(\vec{x})dxîdx^j)
$$

where $a(t)$ is a function of time, and $h_{ij}(x)$ is a particular spatial metric out of three possible cases:

$$
h_{ij}dx^idx^j=\begin{cases}\textnormal{Euclidean flat }h_{ij=\delta_{ij}}\\ \textnormal{three-sphere }S^3\\
\textnormal{hyperbolic space }\mathbb{H}^3\end{cases}
$$
```

From observations we find that $h_{ij}\approx \delta_{ij}$ (i.e. roughly flat). Therefore, we will focus on the flat case:

$$
ds^2=-dt^2+a(t)^2(dx^2+dy^2+dz^2)=-dt^2+a(t)^2(\delta_{ij}dx^idx^j)
$$

The function $a(t)$ is called the **scale factor**. The physical distance between the two events is:

$$
\Delta s=\int_{\textnormal{spacelike geodesic}}ds
$$

On $t=const$ spacelike surface $ds^2=a(t)^2(\delta_{ij}dx^idx^j)$ we have $ds^2=a(t)^2 ds^2_{\textnormal{Euclidean}}$ that implies

$$
ds=a(t)ds_{\textnormal{Euclidean}}
$$

Then integrating alond a spacelike geodesic:

$$
\Delta s=\int a(t)ds_{\textnormal{Euxlidean}}=a(t)\int ds_{\textnormal{Euclidean}}=a(t)|\vec{x}_2-\vec{x}_1|
$$

### Geodesics

Now we want to find geodesics in this geometry: we find the Lagrangian

$$
L=\frac{ds^2}{d\lambda^2}=-\left(\frac{dt}{d\lambda}\right)^2+a^2 \delta_{ij} \frac{dx^i}{d\lambda}\frac{dx^j}{d\lambda}=-\dot{t}^2+a^2\delta_{ij}\dot{x}^i\dot{x}^j
$$

- temporal equation

$$
\frac{d}{d\lambda}(2\dot{t})=2a\dot{a}(\delta_{ij}\dot{x}^i\dot{x}^j)
$$

- spatial equation

$$
\frac{d}{d\lambda}\left(\frac{\partial L}{\partial\dot{x}^i}\right)=\frac{\partial L}{\partial x^i}=0
$$

To calculate the left-hand side we find

$$
\frac{\partial L}{\partial \dot{x}^i}=\frac{\partial}{\partial \dot{x}^i}(-\dot{t}^2+a^2 \delta_{kj}\dot{x}^k\dot{x}^j)=a^2\delta_{kj}\frac{\partial}{\partial \dot{x}^i}(\dot{x}^k\dot{x}^j)=a^2\delta_{kj}(\delta^k_i \dot{x}^j+\dot{x}^k\delta^j_i)=2a^2\delta_{ij}\dot{x}^j
$$

This leads to the equation

$$
\boxed{\frac{d}{d\lambda}(2a^2\delta_{ij}\dot{x}^j)=0}\quad\Rightarrow\quad\boxed{2\delta_{ij}\frac{d}{d\lambda}(a^2\dot{x}^j)=0}\quad\Rightarrow\quad\boxed{\frac{d}{d\lambda}(a^2\dot{x}^i)=0}
$$

This is a conservation law that come from the spatial translation symmetry of the Lagrangian: $x^i\to x^i+c^i$.

We define the momentum $p^i=a^2\dot{x}^i$, and the above equation states that $p^i=const$.

For timelike geodesic $L=-1$ that implies

$$
\boxed{-\dot{t}^2+a^2\delta_{ij}\dot{x}^i\dot{x}^j=-1}\quad \Rightarrow \quad \boxed{-\dot{t}^2+a^2\left(\frac{|\vec{p}|^2}{a^4}\right)=-1}\quad\Rightarrow\quad \boxed{\dot{t}^2=1-\frac{|\vec{p}|^2}{a^2}}
$$

that is a function of $t$ only.

We can find a class of solutions to this equation: let us take $\dot{\vec{x}}=\vec{0}$ that implies that $\vec{x}=const$. Therefore $\dot{t}^2=1$ and $t=\tau$.

The physical distances between observers at fixed $\vec{x}$ is changing with time because $a(t)$ changes with time.

>picture

We call these motion the **Hubble flow**. Anything at constant $\vec{x}$ is said to be comoving with the Hubble flow.

Physical distances between points are $s=a(t)x_0$ and therefore

$$
\frac{ds}{dt}=x_0 \frac{da}{dt}
$$

where the right-hand side tells us the rate of increase of physical distance at $x_0$.

```{note}
Note that actually measuring the physical distance $s$ is difficult because the spacetime is neither stationary nor static.
```

## Conformal time

Introduce a new time coordinate $\sigma$ - **conformal time** such that

$$
ds^2=a^2(-d\sigma^2+\delta_{ij}dx^idx^j)
$$

which is just a rescaled Minkowski metric.

To be more precise:

$$
\boxed{-dt^2=-a^2d\sigma^2}\quad\Rightarrow\quad\boxed{\int d\sigma=\int \frac{dt}{a(t)}}\quad\Rightarrow\quad \boxed{\sigma=\int \frac{dt}{a(t)}}
$$

Null geodesics: $L=a^2(-\dot{\sigma}^2+\delta_{ij}\dot{x}^i\dot{x^j})$. Since $\frac{\partial L}{\partial x^i}=0$ then $p^i=a^2 \dot{x}^i=const$. For null geodesics we have $L=0$ that implies

$$
\boxed{a^2(-\dot{\sigma}^2+\dot{\vec{x}}^2)=0}\quad\Rightarrow\quad\boxed{\dot{\sigma}^2=\dot{\vec{x}}^2}
$$

Without loss of generality, we can rotate coordinates $\vec{x}$ such that $\vec{p}=(p,0,0)$. Then

$$
\dot{x}=\frac{p}{a^2}\,,\quad \dot{y}=0\,,\quad \dot{z}=0
$$

and from the null geodesic condition we have

$$
\boxed{\dot{\sigma}^2=\dot{x}^2}\quad\Rightarrow\quad \boxed{\left(\frac{\dot{\sigma}}{\dot{x}}\right)^2=1}\quad\Rightarrow\quad \boxed{\frac{d\sigma}{dx}=\pm 1}\quad\Rightarrow\quad\boxed{x=x_0\pm \sigma}
$$

This implies that $\vec{x}=(x_0\pm \sigma,y_0,z_0)=\vec{x}_0\pm \sigma \hat{p}$, where $\hat{p}$ is the unit vector in direction of $\vec{p}$. Using conformal time, light rays follow $45^\circ$ lines like in the Minkowski space.

### Cosmological redshift

What happens to the frequency of light rays as they propagate through an expanding spacetime?

Consider that a galaxy at $x=x_g$ sends light signals back to observer at $x=0$, as in the figure.

>picture

Say the proper time interval between the sending of two light signals according to the galaxy is $\Delta\tau_g$. Then we want to find the proper time interval $\Delta\tau_0$ between reception of the signals (according to the observer).

Proper time from observer at constant $\vec{x}$ is

$$
d\tau^2=-ds^2=-a(\sigma)^2(-d\sigma^2+d\vec{x}^2)=a(\sigma)^2 d\sigma^2
$$

for constant $\vec{x}$. We find $d\tau=a(\sigma d\sigma)$ and therefore $\Delta \tau_g=a(\sigma_g)\Delta\sigma_g$ and $\Delta \tau_0=a(\tau_0)\Delta\sigma_g$. This implies

$$
\Delta\tau_0=\frac{a(\sigma_0)}{a(\sigma_g)}\Delta\tau_g
$$

if the two null rays are two crests of a wave, so $\Delta\tau_g$ is the period of the wave, then frequency (as seen by galaxy) is $\nu_g=\frac{1}{\Delta\tau_g}$. This implies

$$
\frac{\nu_0}{\nu_g}=\frac{a(\sigma_g)}{a(\sigma_0)}
$$

In expending universe, $a(\sigma_0)>a(\sigma_g)$ so $\nu_0<\nu_g$ and we get red shift.

If we define $z=\frac{\nu_g}{\nu_0}-1=\frac{a(\sigma_0)}{a(\sigma_g)}-1=\frac{a(\sigma_0)-a(\sigma_g)}{a(\sigma_g)}$ and we suppose that $\sigma_0-\sigma_g$ is small. Let us introduce

$$
H=\frac{1}{a}\frac{da}{dt}
$$

where the derivative is with respect to the coordinate time and not conformal time. We can write

$$
H=\frac{1}{a}\frac{da}{ad\sigma}=\frac{1}{a^2}\frac{da}{d\sigma}
$$

If $a(\sigma_0)\approx a(\sigma_g)$ then

$$
a(\sigma_0)=a(\sigma_g)+(\sigma_0-\sigma_g)\frac{da}{d\sigma}\Big|_{\sigma_g}+\ldots
$$

Then we have

$$
a(\sigma_0)-a(\sigma_g)\approx (\sigma_0-\sigma_g)\frac{da}{d\sigma}\Big|_{\sigma_g}\approx (\sigma_0-\sigma_g)a^2(\sigma_g)H(\sigma_g)
$$

and finally

$$
z=\frac{a(\sigma_0)-a(\sigma_g)}{a(\sigma_g)}\approx (\sigma_0-\sigma_g)a(\sigma_g)H(\sigma_g)=D_g H(\sigma_g)
$$

where $D_g$ is the physical distance to the galaxy.

We arrive at the **Hubble's law**

$$
z\approx D_g H(\sigma_g)
$$
