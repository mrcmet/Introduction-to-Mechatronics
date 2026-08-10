---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **unit vector** is a vector with magnitude exactly equal to 1. It carries direction only — no physical units, no scale. A **basis** is a set of linearly independent vectors that spans a space, meaning any vector in that space can be expressed as a linear combination of basis vectors. In engineering dynamics, the standard choice is an **orthonormal basis**: three mutually perpendicular unit vectors, typically written $\hat{\imath}, \hat{\jmath}, \hat{k}$ (or $\hat{e}_1, \hat{e}_2, \hat{e}_3$).

Notes:
- A unit vector in the direction of $\mathbf{v}$ is $\hat{\mathbf{v}} = \mathbf{v}/|\mathbf{v}|$. The hat notation ($\hat{\phantom{v}}$) always means unit vector throughout this book.
- The standard 3D orthonormal basis: $\hat{\imath} = [1,0,0]^T$, $\hat{\jmath} = [0,1,0]^T$, $\hat{k} = [0,0,1]^T$. These form the axes of any Cartesian coordinate frame.
- **Orthonormal** means orthogonal (all pairwise [[Dot Product]]s are zero) plus normal (each has magnitude 1). Orthonormal bases make computing components easy: the component of $\mathbf{v}$ along $\hat{\mathbf{e}}_i$ is simply $\mathbf{v}\cdot\hat{\mathbf{e}}_i$.
- Every [[Coordinate Frames|coordinate frame]] defines its own orthonormal basis. Switching between frames is essentially a change of basis.
- The columns of a [[3D Rotation Matrix]] are the basis vectors of the rotated frame expressed in the original frame. Recognizing this makes rotation matrices much more intuitive.
- Non-orthonormal bases are valid but make coordinate extraction harder. For this book, assume orthonormal unless stated otherwise.

## Equations

> [!equation] Unit vector from any vector
> $$\hat{\mathbf{v}} = \frac{\mathbf{v}}{|\mathbf{v}|}$$
>
> - $|\mathbf{v}| = \sqrt{v_x^2 + v_y^2 + v_z^2}$ — magnitude of $\mathbf{v}$

> [!equation] Orthonormality conditions
> $$\hat{\mathbf{e}}_i \cdot \hat{\mathbf{e}}_j = \delta_{ij} = \begin{cases}1 & i=j\\0 & i\neq j\end{cases}$$
>
> - $\delta_{ij}$ — Kronecker delta (1 if same index, 0 if different)

## Examples and Non-Examples

- **Direction of a velocity vector.** A robot cart has velocity $\mathbf{v} = [3, 4, 0]^T\ \text{m/s}$. The unit vector in the direction of motion:
$$\hat{\mathbf{v}} = \frac{[3,4,0]^T}{\sqrt{9+16}} = \frac{[3,4,0]^T}{5} = [0.6,\ 0.8,\ 0]^T$$
This direction vector is useful for computing the component of any force along the velocity direction via the [[Dot Product]].

- **Extracting frame axes.** The $x$-axis of a rotated coordinate frame points along $[0.707, 0.707, 0]^T$. Check: magnitude = $\sqrt{0.5 + 0.5} = 1$ ✓. It is a unit vector, so it can serve as a basis vector for that frame.

- **Counter-example — forgetting to normalize.** When computing the unit normal to a surface or the axis of rotation, a common mistake is to use the raw cross product vector without dividing by its magnitude. A cross product has a direction but not (in general) unit magnitude. Always normalize before using as a direction reference.

## Resources

- ![](https://www.youtube.com/watch?v=k7RM-ot2NWY)
- **[Wikipedia — Unit vector](https://en.wikipedia.org/wiki/Unit_vector)**

## Practice

- A force is applied along the line from point A at $(1, 2, 0)$ to point B at $(4, 6, 0)$, with magnitude $F = 26\ \text{N}$. Express the force as a vector $\mathbf{F}$.

> [!NOTE]- Answer
> **Direction vector from A to B:**
> $$\mathbf{d} = [4-1,\ 6-2,\ 0] = [3,\ 4,\ 0]^T, \quad |\mathbf{d}| = \sqrt{9+16} = 5$$
>
> **Unit vector:**
> $$\hat{\mathbf{d}} = \frac{[3,4,0]^T}{5} = [0.6,\ 0.8,\ 0]^T$$
>
> **Force vector:**
> $$\mathbf{F} = F\hat{\mathbf{d}} = 26[0.6,\ 0.8,\ 0]^T = [15.6,\ 20.8,\ 0]^T\ \text{N}$$
