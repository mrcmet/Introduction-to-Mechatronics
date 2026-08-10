---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **position vector** $\mathbf{r}$ describes the location of a point in space relative to a chosen origin. It is an arrow drawn from the origin to the point, and it fully captures both the distance and direction to that point. Every kinematic quantity — velocity, acceleration, trajectory — is defined as a time derivative or transformation of the position vector.

Notes:
- The position vector is always measured relative to a specific [[Coordinate Frames|coordinate frame]]. The same physical point has different components $\mathbf{r}$ depending on which frame you use — this is why tracking frames carefully matters.
- In 2D: $\mathbf{r} = x\hat{\imath} + y\hat{\jmath}$. In 3D: $\mathbf{r} = x\hat{\imath} + y\hat{\jmath} + z\hat{k}$, where $\hat{\imath}, \hat{\jmath}, \hat{k}$ are the [[Unit Vectors and Basis|basis vectors]] of the chosen frame.
- As a column vector (preferred in matrix-based robotics): $\mathbf{r} = \begin{bmatrix} x \\ y \\ z \end{bmatrix}$
- **Position vs. displacement.** Position $\mathbf{r}$ locates a point from the origin. Displacement $\Delta\mathbf{r} = \mathbf{r}_2 - \mathbf{r}_1$ measures the change in position between two instants. Displacement is independent of the origin; position is not.
- The magnitude $|\mathbf{r}| = \sqrt{x^2 + y^2 + z^2}$ gives the straight-line distance from the origin to the point.
- Subscript notation: $\mathbf{r}_{A/B}$ means "position of point A relative to point B." This becomes important in [[Relative Motion]] and multi-body kinematics.

## Equations

> [!equation] Position vector in 3D
> $$\mathbf{r} = x\hat{\imath} + y\hat{\jmath} + z\hat{k} = \begin{bmatrix} x \\ y \\ z \end{bmatrix}$$
>
> - $x, y, z$ — scalar components along each basis axis (m)
> - $\hat{\imath}, \hat{\jmath}, \hat{k}$ — unit vectors of the coordinate frame

## Examples and Non-Examples

- **Robot joint position.** A robot elbow joint is located 0.3 m to the right of and 0.15 m above the shoulder joint. Taking the shoulder as origin: $\mathbf{r}_{elbow} = 0.3\hat{\imath} + 0.15\hat{\jmath}\ \text{m}$. The magnitude is $|\mathbf{r}| = \sqrt{0.3^2 + 0.15^2} \approx 0.335\ \text{m}$ — the actual link length.

- **Displacement vs. position.** A drone flies from $\mathbf{r}_1 = [1, 2, 5]^T\ \text{m}$ to $\mathbf{r}_2 = [4, 2, 5]^T\ \text{m}$. Its displacement is $\Delta\mathbf{r} = [3, 0, 0]^T\ \text{m}$ — 3 m in the $x$-direction, regardless of where the origin is placed.

- **Counter-example — distance is not a position vector.** Saying "the sensor is 0.5 m away" specifies a magnitude but no direction. A position vector requires both. The scalar $|\mathbf{r}| = 0.5\ \text{m}$ describes a sphere of possible positions, not a unique location.

## Resources

- ![](https://www.youtube.com/watch?v=ml4NSzCQobk)
- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)**
- **[Wikipedia — Position (geometry)](https://en.wikipedia.org/wiki/Position_(geometry))**

## Practice

- Point A is at $\mathbf{r}_A = [2, -1, 4]^T\ \text{m}$ and point B is at $\mathbf{r}_B = [5, 3, 4]^T\ \text{m}$, both measured from the same origin. (a) What is the displacement vector from A to B? (b) What is its magnitude?

> [!NOTE]- Answer
> **(a) Displacement from A to B.**
> $$\Delta\mathbf{r}_{B/A} = \mathbf{r}_B - \mathbf{r}_A = \begin{bmatrix}5-2\\3-(-1)\\4-4\end{bmatrix} = \begin{bmatrix}3\\4\\0\end{bmatrix}\ \text{m}$$
>
> **(b) Magnitude.**
> $$|\Delta\mathbf{r}| = \sqrt{3^2 + 4^2 + 0^2} = \sqrt{25} = 5\ \text{m}$$
