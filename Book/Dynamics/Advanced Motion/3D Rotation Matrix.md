---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **3D rotation matrix** $R$ is a $3\times3$ matrix that represents a pure rotation in three-dimensional space. It is a member of the special orthogonal group $SO(3)$, meaning it is orthogonal ($R^{-1} = R^T$) and has determinant $+1$. The columns of $R$ are the [[Unit Vectors and Basis|basis vectors]] of the rotated frame expressed in the original frame — this is the most useful way to read a rotation matrix physically.

Notes:
- **Reading the columns.** If $R$ rotates frame $\{B\}$ relative to frame $\{A\}$, the columns of $R$ are $[{}^A\hat{x}_B \mid {}^A\hat{y}_B \mid {}^A\hat{z}_B]$ — the three axes of $\{B\}$ written in $\{A\}$'s coordinates. Column 1 tells you where $\hat{x}$ of $\{B\}$ points in $\{A\}$, and so on.
- $R^{-1} = R^T$: inverting a rotation is free — just transpose. This is exploited constantly in kinematics.
- $\det(R) = +1$: lengths and right-handedness are preserved. A matrix with $\det = -1$ includes a reflection — not a pure rotation.
- A rotation matrix has **9 entries but only 3 independent DOF** (the 3 rotation angles). The six extra equations come from the orthonormality constraints (three unit-length columns + three orthogonality conditions).
- **Elementary (principal-axis) rotations.** Any rotation can be built from rotations about the three coordinate axes:

$$R_x(\alpha) = \begin{bmatrix}1&0&0\\0&\cos\alpha&-\sin\alpha\\0&\sin\alpha&\cos\alpha\end{bmatrix}, \quad R_y(\beta) = \begin{bmatrix}\cos\beta&0&\sin\beta\\0&1&0\\-\sin\beta&0&\cos\beta\end{bmatrix}, \quad R_z(\gamma) = \begin{bmatrix}\cos\gamma&-\sin\gamma&0\\\sin\gamma&\cos\gamma&0\\0&0&1\end{bmatrix}$$

- Composing rotations is done by matrix multiplication — but **order matters**. See [[Rotation Order Matters]].
- The [[2D Rotation Matrix]] is the $z$-axis rotation matrix $R_z(\theta)$ with the third row and column dropped.

## Equations

> [!equation] Properties of a rotation matrix $R \in SO(3)$
> $$R^T R = I, \qquad \det(R) = +1, \qquad R^{-1} = R^T$$

## Examples and Non-Examples

- **Reading a rotation matrix.** The rotation matrix $R = \begin{bmatrix}0&-1&0\\1&0&0\\0&0&1\end{bmatrix}$ has columns $[0,1,0]^T$, $[-1,0,0]^T$, $[0,0,1]^T$. These say: the $x$-axis of the rotated frame points in the $+y$ direction, the $y$-axis points in the $-x$ direction, and $z$ is unchanged. This is a $90°$ rotation about $z$ — consistent with $R_z(90°)$.

- **Rotating a position vector.** A sensor at $\mathbf{p} = [1, 0, 0]^T\ \text{m}$ in the body frame of a robot link. The link is rotated by $R_z(90°)$ relative to the world frame. The sensor's world-frame position:
$$\mathbf{p}_{world} = R_z(90°)\mathbf{p} = \begin{bmatrix}0\\1\\0\end{bmatrix}\ \text{m}$$
The sensor moved from the $+x$ direction to the $+y$ direction — a quarter turn.

- **Checking a rotation matrix.** Given $R$, verify: (1) all three columns have unit length, (2) all three columns are mutually orthogonal, (3) $\det(R) = 1$. If any fails, the matrix is not a valid rotation.

- **Counter-example — not all orthogonal matrices are rotations.** A matrix with $\det = -1$ is also orthogonal but includes a reflection. Only $\det = +1$ gives a proper rotation that preserves handedness.

## Resources

- ![](https://www.youtube.com/watch?v=OZucG1DY_sY)
- **[Modern Robotics — Chapter 3: Rigid-Body Motions playlist](https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc)**
- **[Wikipedia — Rotation matrix § In three dimensions](https://en.wikipedia.org/wiki/Rotation_matrix#In_three_dimensions)**

## Practice

- Show that $R_z(90°)$ is a valid rotation matrix by checking its orthonormality and determinant.

> [!NOTE]- Answer
> $$R_z(90°) = \begin{bmatrix}0&-1&0\\1&0&0\\0&0&1\end{bmatrix}$$
>
> **Column magnitudes:** $\sqrt{0+1+0}=1$, $\sqrt{1+0+0}=1$, $\sqrt{0+0+1}=1$ ✓
>
> **Orthogonality:** $c_1\cdot c_2 = (0)(-1)+(1)(0)+(0)(0) = 0$ ✓; similarly for other pairs ✓
>
> **Determinant:** $\det = 0(0\cdot1-0\cdot0) - (-1)(1\cdot1-0\cdot0) + 0(\ldots) = 0 + 1 + 0 = 1$ ✓
