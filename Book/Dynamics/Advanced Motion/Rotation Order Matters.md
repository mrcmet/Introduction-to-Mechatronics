---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **3D rotations are not commutative**: applying rotation $R_1$ followed by $R_2$ generally produces a different result from applying $R_2$ followed by $R_1$. In matrix form, $R_1 R_2 \neq R_2 R_1$ in general. This is one of the most important and initially surprising properties of 3D rotation, and it is the root reason why specifying orientation in 3D requires more care than specifying position.

Notes:
- **2D rotations do commute.** All 2D rotations are about the same axis ($z$), so $R_z(\alpha)R_z(\beta) = R_z(\alpha+\beta) = R_z(\beta)R_z(\alpha)$. Non-commutativity is purely a 3D (and higher) phenomenon.
- When composing [[3D Rotation Matrix|rotation matrices]], the convention matters: $R = R_1 R_2$ means "first apply $R_2$, then apply $R_1$" when read as transforming vectors (right-to-left). When read as moving frames, it means "first rotate frame by $R_1$, then rotate the result by $R_2$ about the *new* axes." These interpretations are consistent but require care.
- **Practical consequence for robotics.** In a [[Composing Transformations|kinematic chain]], the order in which joint rotations are applied determines the final end-effector pose. Swapping two joint angles in the computation (not the physical motion) gives a completely different pose.
- **Euler angle ordering is a choice of convention.** [[Euler Angles]] parameterize orientation as three sequential rotations — but $R_z R_y R_x$ and $R_x R_y R_z$ are different parameterizations producing different results for the same three angles. Mixing conventions is a source of orientation bugs in robotics software.
- For small rotations $\delta R_1, \delta R_2$ (perturbations), the commutator $[\delta R_1, \delta R_2] = \delta R_1 \delta R_2 - \delta R_2 \delta R_1 \approx 0$ to first order — small rotations approximately commute. This is why linearized dynamics can treat angular perturbations like vectors.

## Examples and Non-Examples

- **Try it with a book.** Hold a book flat. (1) Rotate it 90° about the vertical axis (spine rotates forward), then 90° about the horizontal axis (front cover faces up). (2) Reverse the order: 90° horizontal first, then 90° vertical. The final orientations are different — this is non-commutativity made physical.

- **Matrix computation.** $R_x(90°)$ then $R_z(90°)$:
$$R_z(90°)R_x(90°) = \begin{bmatrix}0&-1&0\\1&0&0\\0&0&1\end{bmatrix}\begin{bmatrix}1&0&0\\0&0&-1\\0&1&0\end{bmatrix} = \begin{bmatrix}0&0&1\\1&0&0\\0&1&0\end{bmatrix}$$
Swapping the order:
$$R_x(90°)R_z(90°) = \begin{bmatrix}1&0&0\\0&0&-1\\0&1&0\end{bmatrix}\begin{bmatrix}0&-1&0\\1&0&0\\0&0&1\end{bmatrix} = \begin{bmatrix}0&-1&0\\0&0&-1\\1&0&0\end{bmatrix}$$
The results are different matrices — confirming non-commutativity.

- **Counter-example — rotations about the same axis commute.** $R_z(\alpha)R_z(\beta) = R_z(\alpha+\beta) = R_z(\beta)R_z(\alpha)$. Two rotations about the same axis always commute.

## Resources

- ![](https://www.youtube.com/watch?v=OZucG1DY_sY)
- **[Modern Robotics — Chapter 3: Rigid-Body Motions playlist](https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc)**
- **[Wikipedia — Rotation group SO(3)](https://en.wikipedia.org/wiki/3D_rotation_group)**
