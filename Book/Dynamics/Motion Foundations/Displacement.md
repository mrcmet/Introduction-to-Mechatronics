---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Displacement** is the change in [[Position]] of a point between two instants. In one dimension it is the signed scalar $\Delta x = x_f - x_i$; in two or three dimensions it is the vector $\Delta\mathbf{r} = \mathbf{r}_f - \mathbf{r}_i$. Displacement depends only on the starting and ending positions — not on the path taken between them.

Notes:
- Displacement is a **vector quantity**: it has both magnitude and direction. The 1D scalar form is only a shorthand that hides direction inside a sign, anchored to a chosen [[Positive Direction]].
- The sign (or vector direction) matters. A move from $x_i = 5\ \text{m}$ to $x_f = 2\ \text{m}$ gives $\Delta x = -3\ \text{m}$, not $+3\ \text{m}$ — the negative sign carries physical meaning.
- **Displacement vs. [[Distance Traveled]].** Displacement is the straight-line "as the crow flies" change in position. Distance traveled is the total path length and is always non-negative. The two agree only when motion is in a single direction along a straight line.
- Displacement is **frame-independent of the origin**: shifting the coordinate origin changes $\mathbf{r}_i$ and $\mathbf{r}_f$ by the same amount, so their difference is unchanged. This is why displacement, not position, appears directly in kinematic equations.
- Average [[Velocity]] is defined as displacement over elapsed time: $\bar{\mathbf{v}} = \Delta\mathbf{r}/\Delta t$. This is why a round trip with zero displacement also has zero average velocity, even if the object was moving the entire time.
- Displacement is the variable $\Delta x$ that appears in the [[Constant Acceleration Equations]]. Be careful: many textbooks write the symbol $x$ in those equations when they really mean $\Delta x$.

## Equations

> [!equation] Displacement in 1D
> $$\Delta x = x_f - x_i$$
>
> - $\Delta x$ — displacement (m)
> - $x_i$ — initial position along the chosen axis (m)
> - $x_f$ — final position along the same axis (m)
> - Sign is set by the chosen [[Positive Direction]]

> [!equation] Displacement as a vector
> $$\Delta\mathbf{r} = \mathbf{r}_f - \mathbf{r}_i = \begin{bmatrix} x_f - x_i \\ y_f - y_i \\ z_f - z_i \end{bmatrix}$$
>
> - $\Delta\mathbf{r}$ — displacement vector (m)
> - $\mathbf{r}_i, \mathbf{r}_f$ — initial and final [[Position]] vectors
> - $|\Delta\mathbf{r}|$ — straight-line distance between the two points

## Examples and Non-Examples

- **Gantry move.** A pick-and-place gantry head moves from $x_i = 0.20\ \text{m}$ to $x_f = 0.85\ \text{m}$ along its linear rail. The displacement is
$$\Delta x = 0.85 - 0.20 = +0.65\ \text{m}$$
The positive sign tells the motion controller the head moved in the chosen positive direction along the rail.

- **2D robot end-effector.** A SCARA arm moves its end-effector from $\mathbf{r}_i = [0.4, 0.1]^T\ \text{m}$ to $\mathbf{r}_f = [0.1, 0.5]^T\ \text{m}$. The displacement vector is
$$\Delta\mathbf{r} = \begin{bmatrix}0.1 - 0.4\\0.5 - 0.1\end{bmatrix} = \begin{bmatrix}-0.3\\0.4\end{bmatrix}\ \text{m}$$
with magnitude $|\Delta\mathbf{r}| = \sqrt{0.3^2 + 0.4^2} = 0.5\ \text{m}$. That 0.5 m is the straight-line shift — the arm itself may have swept through a curved path much longer than that.

- **Counter-example — round trip.** A delivery robot drives 8 m down a hallway, then drives 8 m back to its start. The total [[Distance Traveled]] is 16 m, but the displacement is
$$\Delta x = x_f - x_i = 0\ \text{m}$$
Zero displacement, nonzero distance — this is the cleanest way to see that the two quantities are not the same.

- **Counter-example — "position" is not displacement.** Saying a robot is "at $x = 3\ \text{m}$" reports a [[Position]], not a displacement. Displacement requires *two* positions and is what you compute from them.

## Resources

![](https://www.youtube.com/watch?v=oRKxmXwLvUU)

- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)** — engineering-mechanics treatment of position, displacement, and velocity vectors.
- **[Michel van Biezen — channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples on displacement vs. distance.
- **[Wikipedia — Displacement (geometry)](https://en.wikipedia.org/wiki/Displacement_(geometry))** — concise reference for the vector definition and contrast with distance.

## Practice

- A mobile robot starts at $\mathbf{r}_i = [2, 1]^T\ \text{m}$, drives in a straight line to $[6, 1]^T\ \text{m}$, then turns and drives to $\mathbf{r}_f = [6, 4]^T\ \text{m}$. (a) What is its displacement vector from start to finish? (b) What is the magnitude of the displacement? (c) What total distance did it travel along its path?

> [!NOTE]- Answer
> **(a) Displacement vector.**
> $$\Delta\mathbf{r} = \mathbf{r}_f - \mathbf{r}_i = \begin{bmatrix}6 - 2\\4 - 1\end{bmatrix} = \begin{bmatrix}4\\3\end{bmatrix}\ \text{m}$$
>
> **(b) Magnitude of displacement.**
> $$|\Delta\mathbf{r}| = \sqrt{4^2 + 3^2} = \sqrt{25} = 5\ \text{m}$$
>
> **(c) Distance traveled along the path.**
> The robot drove 4 m east, then 3 m north, for a total path length of $4 + 3 = 7\ \text{m}$. The path is longer than the displacement magnitude — exactly because displacement ignores the path.
