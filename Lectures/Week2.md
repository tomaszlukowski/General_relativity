# Week 2

## Rediscovering the Forces of Nature

In the previous lecture we introduced a reparametrisation invariant action for a free particle in Special Relativity:

$$
S=-m c\int d\lambda \sqrt{-\eta_{\mu\nu}\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}}
$$

Since this action is reparametrisation invariant, we can choose how to parametrise the physical path using the time coordinate $t$ of some inertial observer: $\lambda=t$. Then we can re-write the above action as

```{math}
:label: non-rel-action
S=-mc^2\int dt \sqrt{1-\frac{\dot{\underline{x}}^2}{c^2}}=-mc^2\int dt \,\gamma
```

where $\dot{\underline{x}}=\frac{d\underline{x}}{dt}$. By doing this we lost explicit reparametrisation invariance but it will allow us to take the first step towards a reparametrisation invariant action for an interacting particle.

### Electrodynamics

So far, we considered a free relativistic particle and we would like to add some extra terms in the action that would describe a force acting on this particle. In the non-relativistic context we would just add a potential term:

$$
S_{non-rel}=\int dt\left[\frac{m}{2}\dot{\underline{x}}^2-V(\underline{x})\right]
$$

We want to write a relativistic action that depends on $x^\mu$, is Lorentz invariant, and also is reparametrisation invariant. It is clear that this restricts our options on the shape of the potential.

Let us start by modifying the action [](non-rel-action) and add a potential term, as we would do in the non-relativistic case:

$$
S=\int dt\left[ -mc^2\sqrt{1-\frac{\dot{\underline{x}}^2}{c^2}}-V(\underline{x})\right]=\int d\lambda\left[\sqrt{-\eta_{\mu\nu}\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}}-V(x^\mu)\right]
$$

and ask if this can come from an action that is reparametrisation invariant? We need to find a potential function that scales in such a way that after change of a parametrisation, the scale compensates the one coming from the $d\lambda$ term. One option would be to add a linear term in $ \frac{dx^\mu}{d\lambda}$. Then, to preserve the Lorentz invariance, we need to contract it with something. This motivates us to introduce a function $A_\mu(x)$ to write:

$$
S=\int d\lambda\left[\sqrt{-\eta_{\mu\nu}\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}}-q A_{\mu}(x)\frac{dx^\mu}{d\lambda}\right]
$$

where $q$ is a constant that determines the strength of coupling of our particle to the new term $A_\mu(x)$. It is easy to check that this action is reparametrisation invariant.

To understand the physics of this action, we again choose the parametrisation to come from an inertial observer: $\lambda=t$ in some inertial coordinate system. If we write $A_\mu=(\frac{\phi(x)}{c},\underline{A}(x))$ we can write our action as:

$$
S=\int dt\left[ -mc^2\sqrt{1-\frac{\dot{\underline{x}}^2}{c^2}}-q\,\phi(\underline{x})-q\underline{A}(\underline{x})\cdot\underline{\dot{x}}\right]
$$

This is nothing else than the action of a particle with electric charge $q$ moving in the background of an electromagnetic field described by potentials $\phi(x)$ and $\underline{A}(x)$. We therefore rediscovered the relativistic electrodynamics.

### Gravity

To discover gravity we need to make a different modification of the action and consider the following generalisation:

```{math}
:label: action-gravity-1
S= -mc^2\int dt\sqrt{1+\frac{2\phi(\underline{x})}{c^2}-\frac{\dot{\underline{x}}^2}{c^2}}
```

that is clearly reparametrisation invariant.

If we now focus on the non-relativistic limit when $\frac{|\underline{\dot{x}}|}{c}\ll 1$ and $\frac{2\phi(\underline{x})}{c^2}\ll 1$, then we can Taylor expand this action to get

$$
S=\int dt \left[-mc^2 +\frac{m}{2}\underline{\dot{x}}^2-m\phi(\underline{x})+\ldots\right]
$$

The first term is a constant giving the rest mass energy of the particle, while the remaining two terms describe a non-relativistic particle moving in the potential $m\phi(\underline{x})$. Since this potential is proportional to the mass of the particle we identify the force associate to it as gravity.

There is a subtle but important detail in the derivation above: notice that the same mass $m$ appears both in front of the kinetic term and the potential term and from the point of view of the Newtonian physics there is no reason why these two coefficients should be the same. However, since we started from a relativistic action, they come from the same coefficient sitting in front of the integral in the action. In Newtonian physics, we could call the mass in the kinetic term the inertial mass $m_I$, while the mass in front of the potential term, the gravitational mass $m_G$. The fact that in relativistic physics they are naturally equal has been confirmed in classical physics long time ago to high precision (around $10^{-13}$) and it is known as the (weak) equivalence principle.

```{admonition} Equivalence principle
:class: tip

$$
\begin{align*}
\\
m_I=m_G
\end{align*}
$$
```

Now we would like to rewrite the action [](action-gravity-1) in a manifestly relativistic and reparametrisation invariant way. First, we observe that the $1$ in [](action-gravity-1) comes from the square-root $\sqrt{1+\ldots}$ and therefore from the $\eta_{00}$ component of the Minkowski space metric. To get the term $1+\frac{2\phi(\underline{x})}{c^2}$, we can promote this component to be coordinate dependent. More generally, we can promote all entries of $\eta_{\mu\nu}$ to function on the spacetime we call $g_{\mu\nu}(x)$, and therefore we introduce a curved spacetime metric

$$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu
$$

Then a reparametrisation invariant action takes the form:

$$
S=-mc \int d\lambda \sqrt{-g_{\mu\nu}(x)\frac{dx^\mu}{d\lambda}\frac{dx^\nu}{d\lambda}}
$$

This action describes a particle moving in curved spacetime.

## Equivalence principle

A consequence of the weak equivalence principle $m_I=m_G$ is that it is not possible to tell the difference between a constant acceleration and a constant gravitational field. In particular:

  - if an observer is experiencing a constant acceleration, it is not possible to say whether the observer is at rest in a gravitational field or is undergoing a constant acceleration
  - if an observer does not experience any forces, it is not possible to distinguish the situation where the observer is in free-fall in a gravitational field or is floating in space with no sources of force acting on it

### Uniformly accelerating observer

We want to focus first on the former case and find a set of coordinates that are adapted to a uniformly accelerating observer. We will view things from the point of view of an inertial frame with coordinates $(ct,x,y,z)$. We consider an object experiencing a constant acceleration $a$ in direction $x$. We want to describe this motion from the point of view of the inertial observer.

Recall from your special relativity course that if we have two consecutive boosts, $v_1$ followed by $v_2$, then the resulting velocity is

$$
v=\frac{v_1+v_2}{1+\frac{v_1v_2}{c^2}}
$$

This can be described in a simpler way by introducing the *rapidity* $\phi$ that is related to the velocity by

$$
v=c\tanh \phi
$$

Rapidities are useful because they add linearly under successive boosts: if $v_1=c\tanh \phi_1$ and $v_2=c\tanh \phi_2$ then $\frac{v_1+v_2}{1+\frac{v_1v_2}{c^2}}=c\tanh (\phi_1+\phi_2)$. Moreover, a constant acceleration means rapidity increases linearly in time $\tau$, where $\tau$ is the accelerating observer's time. Then we have

$$
v(\tau)=\frac{dx}{dt}=c\tanh\left(\frac{a\tau}{c}\right)
$$

We now want to parametrise the motion of the accelerating observer in the inertial coordinate system. To this end we find the relation between the coordinates $t$ and $x$ and the accelerating observer's time $\tau$. We look for a trajectory that passes the origin of the inertial frame, and we synchronise clocks of two observers by choosing $t=0$ when $\tau=0$. This leads us to

$$
  \boxed{\frac{dt}{d\tau}=\gamma(v)=\sqrt{\frac{1}{1-\frac{v^2}{c^2}}}=\cosh\left(\frac{a\tau}{c}\right)}\quad\Rightarrow\quad \boxed{t=\frac{c}{a}\sinh\left(\frac{a\tau}{c}\right)}
$$

around

$$
\boxed{v(\tau)=\frac{dx}{dt}=\frac{dx}{d\tau}\frac{d\tau}{dt}}\quad\Rightarrow \quad \boxed{\frac{dx}{dt}=c\sinh\left(\frac{a\tau}{c}\right)}\quad\Rightarrow\quad \boxed{x=\frac{c^2}{a}\cosh\left(\frac{a\tau}{c}\right)-\frac{c^2}{a}}
$$

The resulting trajectory is a hyperbola

$$
\left(x+\frac{c^2}{a}\right)^2-c^2t^2=\frac{c^4}{a^2}
$$

This trajectory is depicted in the figure below

```{image} ../Week2_pictures/week2_picture4.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

We notice that the trajectory asymptotes to the straight lines $ct=\pm (x+c^2/a)$, indicating that the velocity of the accelerating observer does not exceed speed of light.

Now we would like to introduce a natural coordinate system from the point of view of the accelerating observer. For the time coordinate, we can naturally take the proper time $\tau$ of this observer, but this is defined only on the observer's worldline and we need to extend this definition to cover all four-dimensional space.

There exists a natural set of coordinates in this case. First, if we draw straight lines from any point on the worldline labelled by the proper time $\tau$ to the point $(0,-\frac{c^2}{a})$, we can declare all the points on this line to have the same values of $\tau$. Then we can find a Lorentz transformation that maps the $x$-axis to a line of constant $\tau$ and use this Lorentz transformation to define the spatial coordinate $\rho$. The remaining two coordinates $y$ and $z$ are shared for both observers. This leads us to the following relation:

$$
\begin{align*}
&ct=\left(\rho+\frac{c^2}{a}\right)\sinh\left(\frac{a\tau}{c}\right)\\
&x=\left(\rho+\frac{c^2}{a}\right)\cosh\left(\frac{a\tau}{c}\right)-\frac{c^2}{a}
\end{align*}
$$

We illustrate this coordinate system in the figure below.

```{image} ../Week2_pictures/week2_picture5.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

This coordinates do not cover all of Minkowski space but only the quadrant in the figure. This comes from the fact that not all signals from all regions of the space-time can reach the accelerating observer. This is closely relates to the idea of a horizon in General Relativity.

Finally, we look at the metric experienced by the accelerating observer. We simply substitute the relation between coordinates $(t,x)$ and $(\tau,\rho)$ into the Minkowski space metric to find:

$$
ds^2=-c^2dt^2+dx^2+dy^2+dz^2=-\left(1+\frac{a\rho}{c^2}\right)^2c^2d\tau^2+d\rho^2+dy^2+dz^2
$$

This coordinate system is known as *Kottler-Moeller coordinates* and they are closely related to a better-known *Rindler coordinates*.

The temporal component of this metric $g_{00}$ is

$$
g_{00}=-\left(1+\frac{a\rho}{c^2}\right)^2=-\left(1+\frac{2a\rho}{c^2}+\frac{a^2\rho^2}{c^4}\right)\approx -\left(1+\frac{2a\rho}{c^2}+\ldots\right)
$$

and we see that the accelerated observer feels an effective gravitational potential

$$
\phi(\rho)=a\rho
$$

This is another manifestation of the weak equivalence principle that we discussed above: the acceleration is indistinguishable from a linearly increasing gravitational field, corresponding to a constant gravitational force.

### Local inertial frames

Let us discuss now the second case, where we have an observer in free fall in a gravitational field. If the observer is trapped in a (free-falling) rocket without windows, then they are not able to distinguish their situation from the one when they travel in empty space without any force acting on them. Now importantly, the results of all measurements done inside the rocket will be consistent with special relativity because all objects inside are experiencing exactly the same acceleration (provided that the rocket is small). Therefore, the observer inside the rocket is able to define an inertial frame. From the point of view of the external observer at infinity, this frame is clearly not inertial and it changes from one event to another. This leads us however to the definition of a local inertial frame and the strong version of the equivalence principle:


```{admonition} Strong equivalence principle
:class: tip

Freely-falling  (not-rotating) frames are *locally* inertial, i.e. all physical laws locally agree with Special Relativity. Such frames are called **local inertial frames**.
```

#### Curved spacetime

The notion of local inertial frame can be intuitively understood in the following example: imagine the curved surface of a sphere and a tangent plane to it at some point.

```{image} ../Week2_pictures/week2_picture6.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

 In a small neighbourhood of the point where the plane touches the sphere, the sphere *looks flat*. But as you move away from tha point, the effects of curvature become important. In General Relativity, a local inertial frame can be thought of as the tangent space (locally) to some curved spacetime.

## Tidal forces

In the previous section we said that constant gravitational force cannot be distinguished from a constant acceleration. However, if we have a changing, non-uniform gravitational field with potential $\phi(\underline{x})$, then there will be tidal forces and we will be able to distinguish the two scenarios if we perform a non-local experinment. The following discussion allows us to quantify what we mean by the word 'local' when we define local inertial frames.

For example: consider the field due to a point mass (e.g. a planet) at two nearby points $\underline{x}_1$ and $\underline{x}_2$:

```{image} ../Week2_pictures/week2_picture1.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

The  force vectors are not parallel and objects will have a relative acceleration (towards each other). In a freely falling frame, the free particles will seem to accelerate towards each other.

More generally: if we have two nearby objects at $\underline{x}_1=\underline{x}(t)$ and $\underline{x}_2=\underline{x}(t)+\underline{y}(t)$, then both satisfy $\ddot{\underline{x}}=-\underline{\nabla}\phi$, namely $\ddot{\underline{x}}_1=-\underline{\nabla}\phi\Big|_{\underline{x}_1}$ and $\ddot{\underline{x}}_2=-\underline{\nabla}\phi\Big|_{\underline{x}_2}$. This implies that

$$
\underline{y}=\underline{x}_2-\underline{x}_1 \Rightarrow \ddot{\underline{y}}=-\left(\underline{\nabla}\phi\Big|_{\underline{x}+\underline{y}}-\underline{\nabla}\phi\Big|_{\underline{x}}\right)\Rightarrow \ddot{y}_i=-\left(\partial_i\phi\Big|_{\underline{x}+\underline{y}}-\partial_i\phi\Big|_{\underline{x}}\right)\sim -\left(y^j\partial_j\partial_i\phi\Big|_{\underline{x}}+\mathcal{O}(y^2)\right)
$$

This means that roughly $\ddot{y}_i=-(\partial_j\partial_i\phi)y^j$, so $\ddot{y}_i$, the relative acceleration, is small if $y$ is small. But as the separation $\underline{y}$ grows, the relative acceleration becomes more significant (if $\partial_i\partial_j\phi\neq 0$). In General Relativity, we think of gravity as beeing *locally* indistinguishable from accelerating frame:

```{important}
 Locally = ignoring tidal forces
```

## Consequences of the equivalence principle

### Static rigid lattices

Let us first introduce a particular set of observers that will allow us to talk about events in presence of gravity.

Let us imagine that we have a lattice of rods with clocks attached to them.

```{image} ../Week2_pictures/week2_picture7.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

Say that clocks can send light signals back and forth between rods and record when they are sent and when they arrive. Consider a round trip where a signal is sent from clock A to clock B and then back to clock A.

- if round trip times do not depend on when the signals are sent then the spacetime is called **stationary**.
- if round trip times around closed loops also do not depend on the direction around the loop then the spacetime is **static** and the lattice of rods is called **rigid**.

The rigid lattice in a static spacetime defines a non-inertial frame in which the lattice is not moving (for example, a set of chairs on the surface of the Earth forms a rigid lattice).

Spacetimes that are stationary but not static can arise around for example rotating objects. If say a planet is rotating with constant velocity then the round trip measurements will not depend on the initial time of our measurement, but it might depend on the direction in which we send the signal (aligned or anti-aligned with the rotation of the planet).

### Light is deflected by gravity

Consider  shining light  along a freely-falling tube. In the local inertial frame attached to the tube, light passes through the tube as in an inertial frame in Special Relativity. But in the rigid lattice frame, the tube falls downward and therefore also the light needs to follow its trajectory. This means that the light ray must be deflected downwards by gravity!

```{image} ../Week2_pictures/week2_picture8.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

### Gravitational time dilation

We have already observed that a weak gravitational field changes the temporal component of the metric to be:

$$
g_{00}(x)=1+\frac{2\phi(x)}{c^2}
$$

Let us assume that $\phi(x)$ is such that $\phi(x)=\phi(|\underline{x}|)=\phi(r)<0$ and $\phi(r)\to 0$ when $r\to \infty$. This means that the observer sitting at a fixed distance $r$ from the gravity source will measure a time intervals

$$
d\tau^2=g_{00}dt^2=\left(1+\frac{2\phi(r)}{c^2}\right)
$$

Therefore, if an asymptotic observer at $r\to \infty$ measures time $t$ then the observer at distance $r$ will measure time

$$
T(r)=t\sqrt{1+\frac{2\phi(x)}{c^2}}
$$

which means that time goes slower in the presence of a massive, gravitational object.

### Gravitational red-shift

Consider a photon moving down towards Earth. At a particular instance, the photon passes  through the roof of a freely falling cabin (i.e. local inertial frame) which is stationary with respect to the rigid lattice at that instant. Say that this is the time $t=0$ according to the local inertial frame observer.

```{image} ../Week2_pictures/week2_picture2.png
:class: bg-primary mb-1
:width: 300px
:align: center
```

We assume that the cabin has the height $\Delta h$ and the photon has frequency $\nu$ in the local inertial frame. Local inertial observer just sees Special Relativity.

```{image} ../Week2_pictures/week2_picture3.png
:class: bg-primary mb-1
:width: 600px
:align: center
```

 This event is also observed by an observer attached to the rigid lattice. At $t=0$, the cabin is at rest with respect to lattice, which implies that observer also sees photon frequency $\nu$. At event B, the cabin has velocity downwards:

$$
v\approx gt\approx \frac{g\Delta h}{c}
$$

In the local inertial frame, the lattice observer at B is moving upwards towards the photon with velocity $v$. Then the lattice observer sees a Doppler-shifted frequency:

$$
\boxed{\nu_{\textnormal{obs}}=\left(1+\frac{v}{c}\right)\nu}\quad \Rightarrow\quad \boxed{\Delta\nu=\nu_{\textnormal{obs}}-\nu=\frac{v}{c}\nu=\frac{g\Delta h}{c^2}\nu}\quad \Rightarrow \quad \boxed{\frac{\Delta\nu}{\nu}=\frac{g\Delta h}{c^2}}
$$

Since we have $g=\frac{d\phi}{dx}$, then $\Delta \phi=g\Delta h$, and finally

$$
\boxed{\Delta \log\nu=\frac{1}{c^2}\Delta\phi}\quad \Rightarrow\quad \boxed{\nu_{\textnormal{obs}}=\nu_0 e^{(\phi-\phi_0)/c^2}}
$$

where $\nu_0$ is the frequency at potential $\phi_0$.

```{admonition} Important point
:class: warning

 The frequency shift is not due to anything happening to the photon as it *falls*. It is due to the clocks of the observer running at different speeds. The fixed observer at B is moving with respect to the local inertial frame of the cabin, so their clock appears to run slow in the local inertial frame (standard special relativity Doppler shift).
```

As an example, let us take $\phi(r)=-\frac{GM}{r}$. Then

$$
\nu_{\textnormal{obs}}=\nu_0 \exp\left(\frac{GM}{c^2 r_0}-\frac{GM}{c^2 r}\right)\approx \nu_0\left(1+\frac{GM}{c^2 r_0}-\frac{GM}{c^2 r}\right)=\nu_0\left(1+\frac{GM}{c^2 r_0 r}\Delta h\right)
$$

This means that the observed frequency is higher than the frequency in the local inertial frame. If we reverted the situation and send a light ray upwards then the frequency observed by an observer far away from the gravity source would measure a lower frequency than the one sent. This is a red-shift associated to gravitational fields.
