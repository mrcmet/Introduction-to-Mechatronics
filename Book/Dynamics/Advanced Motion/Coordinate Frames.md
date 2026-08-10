---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **coordinate frame** (or reference frame) is a combination of an origin point and an orthonormal set of [[Unit Vectors and Basis|basis vectors]] that defines a coordinate system for describing positions, velocities, and orientations. Every vector quantity in dynamics must be expressed *in a specific frame*. Changing which frame you use changes the numerical components of a vector, even though the physical vector itself does not change.

Notes:
- A frame is written with a label: frame $\{A\}$, frame $\{B\}$, or shorthand $\{0\}, \{1\}, \{2\},\ldots$ for a numbered chain. The **world frame** (also called **space frame** or **inertial frame**) is the fixed reference, typically labeled $\{s\}$ or $\{0\}$.
- A **body frame** is attached to and moves with a rigid body. The robot base, each joint, and the end-effector each have their own body frame. As the robot moves, the body frames move with it.
- To describe a vector in frame $\{B\}$ that is expressed in frame $\{A\}$, you need the rotation from $\{A\}$ to $\{B\}$ — captured by a [[2D Rotation Matrix|rotation matrix]] — and the position of $\{B\}$'s origin in $\{A\}$ — captured by a [[Position Vector]]. Together, these form a [[Homogeneous Transformation]].
- Notation convention used in this book: ${}^A\mathbf{r}$ means the vector $\mathbf{r}$ expressed in frame $\{A\}$. A superscript identifies the frame; no superscript implies the world frame.
- **Right-handed frames** are the standard in engineering. In a right-handed frame, $\hat{x}\times\hat{y} = \hat{z}$. Always check handedness when importing data from sensors, especially cameras and IMUs, which sometimes use left-handed or non-standard conventions.
- Every time you add vectors or write equations of motion, all terms must be expressed in the same frame. Frame mismatches are one of the most common sources of bugs in robotics code.

## Examples and Non-Examples

- **Robot arm frames.** A 2-DOF planar arm has three frames: $\{0\}$ at the fixed base, $\{1\}$ attached to link 1 (rotating with joint 1), and $\{2\}$ attached to link 2 (rotating with joint 2). The end-effector position *in the world frame* $\{0\}$ requires tracking how each frame relates to the previous one — this is [[Composing Transformations]].

- **Camera and robot frame.** A vision sensor detects an object at position ${}^C\mathbf{r}_{obj} = [0.1, -0.05, 0.3]^T\ \text{m}$ in the camera frame $\{C\}$. To command the robot arm to grasp the object, you need ${}^0\mathbf{r}_{obj}$ — the same position in the world frame. This requires the known transform from camera frame to world frame.

- **Counter-example — adding vectors in different frames.** A sensor reports a velocity in its own body frame; the robot's control algorithm expects velocity in the world frame. Adding the two directly is physically meaningless — like adding miles to kilometers without converting. Always transform into a common frame first.

## Resources

- ![](https://www.youtube.com/watch?v=29LhXWjn7Pc)
- **[Modern Robotics — Chapter 3: Rigid-Body Motions playlist](https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc)**

## Practice

- Frame $\{B\}$ has its origin at $(2, 1)$ relative to frame $\{A\}$, and its $x$-axis points along $[1, 0]^T$ in $\{A\}$ (aligned, no rotation). A point P is at $[3, 2]^T$ in frame $\{A\}$. What are the coordinates of P in frame $\{B\}$?

> [!NOTE]- Answer
> Since the frames are aligned (no rotation), the conversion is a pure translation. Subtract the origin of $\{B\}$ from the point's coordinates in $\{A\}$:
> $${}^B\mathbf{r}_P = {}^A\mathbf{r}_P - {}^A\mathbf{r}_{B_{origin}} = \begin{bmatrix}3\\2\end{bmatrix} - \begin{bmatrix}2\\1\end{bmatrix} = \begin{bmatrix}1\\1\end{bmatrix}$$
> In frame $\{B\}$, the point is at $(1, 1)$.
