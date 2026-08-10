---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **homogeneous transformation matrix** $T$ is a $4\times4$ matrix that simultaneously encodes a rotation $R$ and a translation $\mathbf{p}$ in a single object. It represents the [[Pose and Configuration|pose]] of one [[Coordinate Frames|coordinate frame]] relative to another — telling you both where the frame's origin is and how the frame is oriented. Packing rotation and translation into one matrix makes it possible to compose multiple frame transformations with a single matrix multiplication.

Notes:
- The structure is always:
$$T = \begin{bmatrix}R & \mathbf{p}\\\mathbf{0}^T & 1\end{bmatrix}$$
where $R \in SO(3)$ is a $3\times3$ [[3D Rotation Matrix|rotation matrix]], $\mathbf{p} \in \mathbb{R}^3$ is the position of the new frame's origin in the current frame, $\mathbf{0}^T = [0,0,0]$, and the bottom-right entry is always 1.
- $T$ belongs to the **special Euclidean group** $SE(3)$ — the set of all rigid-body poses in 3D space.
- **Homogeneous coordinates.** To transform a point $\mathbf{p}' = [x, y, z]^T$, extend it to a 4D vector $\tilde{\mathbf{p}} = [x, y, z, 1]^T$ and multiply: $\tilde{\mathbf{p}}_{new} = T\,\tilde{\mathbf{p}}_{old}$. The extra 1 is what allows translation to be handled by matrix multiplication.
- **Inverse.** The inverse of $T$ is not simply $T^T$, but has a clean closed form:
$$T^{-1} = \begin{bmatrix}R^T & -R^T\mathbf{p}\\\mathbf{0}^T & 1\end{bmatrix}$$
- Notation: $T_{AB}$ or ${}^A T_B$ means "the pose of frame $\{B\}$ described in frame $\{A\}$." To express a point ${}^B\mathbf{p}$ in frame $\{A\}$: $\tilde{{}^A\mathbf{p}} = T_{AB}\,\tilde{{}^B\mathbf{p}}$.
- A pure rotation (no translation) has $\mathbf{p} = \mathbf{0}$. A pure translation (no rotation) has $R = I$.

## Equations

> [!equation] Homogeneous transformation matrix
> $$T = \begin{bmatrix}R_{3\times3} & \mathbf{p}_{3\times1}\\\mathbf{0}_{1\times3} & 1\end{bmatrix} \in SE(3)$$
>
> - $R$ — rotation part: orientation of the new frame in the old frame
> - $\mathbf{p}$ — translation part: origin of new frame in old frame (m)

> [!equation] Inverse of a homogeneous transformation
> $$T^{-1} = \begin{bmatrix}R^T & -R^T\mathbf{p}\\\mathbf{0}^T & 1\end{bmatrix}$$

## Examples and Non-Examples

- **Robot base to shoulder frame.** Frame $\{1\}$ (shoulder) is located 0.1 m along $z$ from the base frame $\{0\}$ and is not rotated. The transformation:
$$T_{01} = \begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0.1\\0&0&0&1\end{bmatrix}$$
A point at $[0.2, 0, 0]^T$ in frame $\{1\}$ has world-frame coordinates $\tilde{\mathbf{p}}_{world} = T_{01}[0.2, 0, 0, 1]^T = [0.2, 0, 0.1, 1]^T$, i.e., $[0.2, 0, 0.1]^T$.

- **Joint frame with rotation and offset.** A joint rotates by $90°$ about $z$ and the link has length 0.3 m along the new $x$-axis. The transformation encodes both simultaneously — a single $T$ replaces what would otherwise require separate rotation and translation operations.

- **Counter-example — confusing $T_{AB}$ and $T_{BA}$.** $T_{AB}$ transforms points expressed in $\{B\}$ into $\{A\}$. Its inverse $T_{BA} = T_{AB}^{-1}$ goes the other way. Using $T_{AB}$ where $T_{BA}$ is needed is a common error in robot kinematics code.

## Resources

- ![](https://www.youtube.com/watch?v=vlb3P7arbkU)
- **[Modern Robotics — Chapter 3: Rigid-Body Motions playlist](https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc)**
- **[Wikipedia — Transformation matrix](https://en.wikipedia.org/wiki/Transformation_matrix)**

## Practice

- Frame $\{B\}$ is located at $\mathbf{p} = [1, 0, 0]^T\ \text{m}$ relative to frame $\{A\}$ and is rotated $90°$ about the $z$-axis. Write $T_{AB}$. Then find the inverse $T_{BA}$.

> [!NOTE]- Answer
> $$R_z(90°) = \begin{bmatrix}0&-1&0\\1&0&0\\0&0&1\end{bmatrix}, \qquad T_{AB} = \begin{bmatrix}0&-1&0&1\\1&0&0&0\\0&0&1&0\\0&0&0&1\end{bmatrix}$$
>
> $$T_{BA} = T_{AB}^{-1} = \begin{bmatrix}R^T & -R^T\mathbf{p}\\0&1\end{bmatrix} = \begin{bmatrix}0&1&0&0\\-1&0&0&1\\0&0&1&0\\0&0&0&1\end{bmatrix}$$
> (Verify: $T_{AB}T_{BA} = I$ ✓)
