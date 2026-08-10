---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **dot product** (also called the scalar product) of two vectors $\mathbf{a}$ and $\mathbf{b}$ is a scalar equal to the product of their magnitudes and the cosine of the angle between them. It measures how much two vectors "point in the same direction." The result is always a scalar — no direction, just a number.

Notes:
- Two vectors are **orthogonal** (perpendicular) if and only if their dot product is zero, since $\cos90° = 0$. This is the quickest test for perpendicularity.
- The dot product of a vector with itself gives the square of its magnitude: $\mathbf{a} \cdot \mathbf{a} = |\mathbf{a}|^2$.
- **Projection.** The scalar projection of $\mathbf{b}$ onto $\mathbf{a}$ is $\mathbf{b} \cdot \hat{\mathbf{a}} = |\mathbf{b}|\cos\theta$. This gives the component of $\mathbf{b}$ in the direction of $\mathbf{a}$. Decomposing a vector into components along each [[Unit Vectors and Basis|basis vector]] uses this idea repeatedly.
- Work done by a force uses the dot product: $W = \mathbf{F} \cdot \Delta\mathbf{r}$. Only the component of force along the displacement does work — the perpendicular component contributes nothing.
- The dot product is commutative ($\mathbf{a}\cdot\mathbf{b} = \mathbf{b}\cdot\mathbf{a}$) and distributive over addition.
- The dot product is used to check whether two [[Coordinate Frames|frame axes]] are perpendicular when constructing an orthonormal basis.

## Equations

> [!equation] Dot product — geometric form
> $$\mathbf{a} \cdot \mathbf{b} = |\mathbf{a}||\mathbf{b}|\cos\theta$$
>
> - $\theta$ — angle between the two vectors (0° to 180°)

> [!equation] Dot product — component form
> $$\mathbf{a} \cdot \mathbf{b} = a_x b_x + a_y b_y + a_z b_z$$

> [!equation] Angle between two vectors
> $$\cos\theta = \frac{\mathbf{a} \cdot \mathbf{b}}{|\mathbf{a}||\mathbf{b}|}$$

## Examples and Non-Examples

- **Work done by a cable.** A robot arm pulls a load through displacement $\Delta\mathbf{r} = [3, 0, 0]^T\ \text{m}$ with force $\mathbf{F} = [10, 5, 0]^T\ \text{N}$. The work done is:
$$W = \mathbf{F} \cdot \Delta\mathbf{r} = (10)(3) + (5)(0) + (0)(0) = 30\ \text{J}$$
The $y$-component of force (perpendicular to displacement) contributes nothing.

- **Finding the angle between two links.** Link A points along $\hat{\mathbf{a}} = [1, 0, 0]^T$ and link B points along $\hat{\mathbf{b}} = [0.707, 0.707, 0]^T$. The angle between them: $\cos\theta = \hat{\mathbf{a}} \cdot \hat{\mathbf{b}} = 0.707$, so $\theta = 45°$.

- **Checking axis orthogonality.** The standard basis vectors satisfy $\hat{\imath}\cdot\hat{\jmath} = 0$, $\hat{\jmath}\cdot\hat{k} = 0$, and $\hat{\imath}\cdot\hat{k} = 0$ — confirming they are mutually perpendicular. This orthogonality is what makes component decomposition independent along each axis.

- **Counter-example — dot product gives direction.** The dot product produces a scalar. If you need a vector result from two vectors, you want the [[Cross Product]].

## Resources

- ![](https://www.youtube.com/watch?v=WNuIhXo39_k)
- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)**
- **[Wikipedia — Dot product](https://en.wikipedia.org/wiki/Dot_product)**

## Practice

- A motor exerts force $\mathbf{F} = [8, 6, 0]^T\ \text{N}$ while the point of application moves through displacement $\Delta\mathbf{r} = [2, -1, 0]^T\ \text{m}$. How much work is done? What angle does $\mathbf{F}$ make with $\Delta\mathbf{r}$?

> [!NOTE]- Answer
> **Work:**
> $$W = \mathbf{F}\cdot\Delta\mathbf{r} = (8)(2) + (6)(-1) + (0)(0) = 16 - 6 = 10\ \text{J}$$
>
> **Angle:**
> $$|\mathbf{F}| = \sqrt{64+36} = 10\ \text{N}, \quad |\Delta\mathbf{r}| = \sqrt{4+1} = \sqrt{5}\ \text{m}$$
> $$\cos\theta = \frac{10}{10\sqrt{5}} = \frac{1}{\sqrt{5}} \approx 0.447 \implies \theta \approx 63.4°$$
