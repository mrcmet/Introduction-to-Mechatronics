---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **2D rotation matrix** $R(\theta)$ is a $2\times2$ matrix that rotates a vector in the plane by angle $\theta$ counter-clockwise about the origin. It can also be interpreted as expressing the [[Unit Vectors and Basis|basis vectors]] of a rotated frame in terms of the original frame. The set of all 2D rotation matrices forms the group $SO(2)$.

Notes:
- **Two uses of the same matrix.** Given $R(\theta)$:
    - *Rotating a vector:* $\mathbf{p}' = R(\theta)\mathbf{p}$ — rotates vector $\mathbf{p}$ by $+\theta$ in the same frame.
    - *Changing frames:* ${}^A\mathbf{p} = R(\theta){}^B\mathbf{p}$ — expresses a vector written in frame $\{B\}$ (rotated $\theta$ from $\{A\}$) into frame $\{A\}$. The columns of $R$ are the axes of $\{B\}$ expressed in $\{A\}$.
- $R(\theta)$ is **orthogonal**: $R^{-1} = R^T$. Transposing inverts the rotation — rotating by $-\theta$.
- $\det(R) = 1$ always. This means the rotation preserves vector lengths and the handedness of the coordinate system.
- $R(-\theta) = R(\theta)^T$ — to reverse a rotation, transpose the matrix.
- Stacking rotations in 2D: $R(\alpha)R(\beta) = R(\alpha+\beta)$. In 2D, rotations commute. This is *not* true in 3D — see [[Rotation Order Matters]].
- This extends naturally to 3D as the [[3D Rotation Matrix]], where a rotation about a single axis has the same 2×2 block structure embedded in a 3×3 matrix.

## Equations

> [!equation] 2D Rotation Matrix
> $$R(\theta) = \begin{bmatrix}\cos\theta & -\sin\theta \\ \sin\theta & \cos\theta\end{bmatrix}$$
>
> - $\theta$ — rotation angle, counter-clockwise positive
> - Columns: $[\cos\theta,\ \sin\theta]^T$ is the new $\hat{x}$-axis; $[-\sin\theta,\ \cos\theta]^T$ is the new $\hat{y}$-axis

## Examples and Non-Examples

- **Rotating a position vector.** A robot end-effector is at $\mathbf{p} = [1, 0]^T\ \text{m}$ in frame $\{0\}$. Joint 1 rotates the arm by $\theta = 45°$. The new position of the tip:
$$\mathbf{p}' = R(45°)\begin{bmatrix}1\\0\end{bmatrix} = \begin{bmatrix}\cos45° \\ \sin45°\end{bmatrix} = \begin{bmatrix}0.707\\0.707\end{bmatrix}\ \text{m}$$
The tip moves up and to the right, at 45° from the $x$-axis. Length is preserved: $|\mathbf{p}'| = 1\ \text{m}$ ✓.

- **Frame interpretation.** Frame $\{1\}$ is attached to a link and is rotated $30°$ from the world frame $\{0\}$. The columns of $R(30°)$ are the axes of $\{1\}$ expressed in $\{0\}$: $x_1 = [0.866, 0.5]^T$ and $y_1 = [-0.5, 0.866]^T$.

- **Inverting a rotation.** To find the coordinates of a world-frame point $\mathbf{p}$ in a frame $\{1\}$ rotated $\theta$ from world: ${}^1\mathbf{p} = R(\theta)^T\,{}^0\mathbf{p}$.

- **Counter-example — rotation in 3D is not this simple.** In 3D, a rotation about the $z$-axis extends $R(\theta)$ by adding a row/column for $z$. But a general 3D rotation about an arbitrary axis cannot be captured by this 2D structure alone — see [[3D Rotation Matrix]].

## Resources

- ![](https://www.youtube.com/watch?v=OZucG1DY_sY)
- **[Modern Robotics — Chapter 3: Rigid-Body Motions playlist](https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc)**
- **[Wikipedia — Rotation matrix](https://en.wikipedia.org/wiki/Rotation_matrix)**

## Practice

- A sensor is at $\mathbf{p} = [2, 0]^T\ \text{m}$ in a body frame. The body frame is rotated $\theta = 60°$ counter-clockwise relative to the world frame. What are the world-frame coordinates of the sensor?

> [!NOTE]- Answer
> $$\mathbf{p}_{world} = R(60°)\mathbf{p} = \begin{bmatrix}\cos60° & -\sin60°\\\sin60° & \cos60°\end{bmatrix}\begin{bmatrix}2\\0\end{bmatrix} = \begin{bmatrix}2\cos60°\\2\sin60°\end{bmatrix} = \begin{bmatrix}1.0\\1.732\end{bmatrix}\ \text{m}$$
