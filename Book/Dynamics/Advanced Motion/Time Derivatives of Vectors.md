---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **time derivative of a vector** is found by differentiating each scalar component with respect to time, provided the basis vectors themselves are fixed (constant). The derivative of a [[Position Vector]] gives velocity; the derivative of velocity gives acceleration. When the basis vectors are attached to a moving or rotating frame, extra terms appear — those are handled in [[Relative Motion]] and [[Angular Velocity Vector]].

Notes:
- In a **fixed (inertial) frame**, basis vectors $\hat{\imath}, \hat{\jmath}, \hat{k}$ are constant, so the time derivative is component-wise: $\dot{\mathbf{r}} = \dot{x}\hat{\imath} + \dot{y}\hat{\jmath} + \dot{z}\hat{k}$.
- The velocity $\mathbf{v}$ and acceleration $\mathbf{a}$ of a particle are:
$$\mathbf{v} = \dot{\mathbf{r}} = \frac{d\mathbf{r}}{dt}, \qquad \mathbf{a} = \ddot{\mathbf{r}} = \frac{d^2\mathbf{r}}{dt^2}$$
These are the vector generalizations of the [[Constant Acceleration Kinematics]] equations, which assumed constant $\mathbf{a}$.
- **Product rule applies to vectors.** For two vectors $\mathbf{a}(t)$ and $\mathbf{b}(t)$:
    - $\frac{d}{dt}(\mathbf{a}\cdot\mathbf{b}) = \dot{\mathbf{a}}\cdot\mathbf{b} + \mathbf{a}\cdot\dot{\mathbf{b}}$
    - $\frac{d}{dt}(\mathbf{a}\times\mathbf{b}) = \dot{\mathbf{a}}\times\mathbf{b} + \mathbf{a}\times\dot{\mathbf{b}}$ (order matters — cross product is not commutative)
- A unit vector $\hat{\mathbf{u}}(t)$ that rotates has a non-zero derivative perpendicular to itself: $\dot{\hat{\mathbf{u}}} \perp \hat{\mathbf{u}}$. This is the origin of centripetal acceleration in circular motion and will reappear when differentiating rotation matrices.
- **Constant magnitude does not mean zero derivative.** If $|\mathbf{r}(t)| = R = \text{const}$ (circular motion), the vector still changes direction, so $\dot{\mathbf{r}} \neq \mathbf{0}$.

## Equations

> [!equation] Velocity and acceleration of a particle (fixed frame)
> $$\mathbf{v} = \dot{\mathbf{r}} = \begin{bmatrix}\dot{x}\\\dot{y}\\\dot{z}\end{bmatrix}, \qquad \mathbf{a} = \ddot{\mathbf{r}} = \begin{bmatrix}\ddot{x}\\\ddot{y}\\\ddot{z}\end{bmatrix}$$
>
> Valid only when $\hat{\imath}, \hat{\jmath}, \hat{k}$ are constant (fixed frame).

## Examples and Non-Examples

- **Particle on a straight path.** A robot joint moves along the $x$-axis with $x(t) = 3t^2 - t^3\ \text{m}$. Then:
$$v_x = \dot{x} = 6t - 3t^2\ \text{m/s}, \qquad a_x = \ddot{x} = 6 - 6t\ \text{m/s}^2$$
At $t = 1\ \text{s}$: $v_x = 3\ \text{m/s}$, $a_x = 0$. This is the velocity peak — acceleration is zero when velocity stops changing.

- **Circular motion — direction changes, magnitude constant.** A point on a rotating wheel at radius $R$ has position $\mathbf{r}(t) = R\cos\omega t\,\hat{\imath} + R\sin\omega t\,\hat{\jmath}$. Differentiating:
$$\mathbf{v} = -R\omega\sin\omega t\,\hat{\imath} + R\omega\cos\omega t\,\hat{\jmath}$$
The speed is $|\mathbf{v}| = R\omega = \text{const}$, but $\mathbf{v}$ changes direction continuously — so $\mathbf{a} = \ddot{\mathbf{r}} \neq \mathbf{0}$, pointing inward (centripetal).

- **Counter-example — differentiating in a rotating frame.** If the basis vectors $\hat{\imath}(t), \hat{\jmath}(t)$ rotate with a body (body frame), then $\frac{d\mathbf{r}}{dt} \neq \dot{x}\hat{\imath}+\dot{y}\hat{\jmath}$ — you must account for the rotating frame using the [[Angular Velocity Vector]]. Forgetting this correction is a common source of error in robot arm velocity analysis.

## Resources

- ![](https://www.youtube.com/watch?v=ywTVrqStgkM)
- **[Modern Robotics — Angular Velocities (Chapter 3.2.2)](https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc)**

## Practice

- A drone's position is $\mathbf{r}(t) = [2t,\ 4t - t^2,\ 5]^T\ \text{m}$. Find its velocity and acceleration vectors at $t = 2\ \text{s}$.

> [!NOTE]- Answer
> **Velocity (differentiate each component):**
> $$\mathbf{v}(t) = \dot{\mathbf{r}} = \begin{bmatrix}2\\4-2t\\0\end{bmatrix}\ \text{m/s}$$
> At $t = 2$: $\mathbf{v}(2) = [2,\ 0,\ 0]^T\ \text{m/s}$ — moving only in $x$ at this instant.
>
> **Acceleration:**
> $$\mathbf{a}(t) = \ddot{\mathbf{r}} = \begin{bmatrix}0\\-2\\0\end{bmatrix}\ \text{m/s}^2$$
> Constant deceleration in $y$, regardless of time.
