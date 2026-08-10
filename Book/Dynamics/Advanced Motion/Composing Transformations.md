---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Composing transformations** means chaining multiple [[Homogeneous Transformation|homogeneous transformation matrices]] together by matrix multiplication to describe the pose of a distant frame relative to a base frame, passing through intermediate frames. For a kinematic chain with frames $\{0\} \to \{1\} \to \{2\} \to \cdots \to \{n\}$, the transformation from base to end is the ordered product $T_{0n} = T_{01}\,T_{12}\,\cdots\,T_{(n-1)n}$.

Notes:
- **Reading the chain.** $T_{0n} = T_{01}T_{12}\cdots T_{(n-1)n}$: read left-to-right, each $T_{i,i+1}$ describes frame $\{i+1\}$ in frame $\{i\}$. The subscripts chain — the "inner" indices cancel, leaving the outermost pair.
- **Order matters.** Because matrix multiplication is not commutative ([[Rotation Order Matters]]), swapping the order of any two transformations in the chain gives a different result. The matrices must be multiplied in the correct sequence.
- **Two interpretations of the same product:**
    - *Fixed-frame (extrinsic):* $T_{0n} = T_1 T_2 \cdots T_n$ applies transformations left-to-right, each relative to the *fixed world frame*. 
    - *Body-frame (intrinsic):* $T_{0n} = T_1 T_2 \cdots T_n$ applies transformations right-to-left, each relative to the *current body frame*. 
    The product is the same matrix either way — the interpretation of what each factor represents differs. Right-multiplying = moving relative to the body frame; left-multiplying = moving relative to the world frame.
- For a 6-axis arm, composing the six joint transformations $T_{01}T_{12}T_{23}T_{34}T_{45}T_{56}$ gives the end-effector pose $T_{06}$ in the base frame — this is [[Forward Kinematics]].
- Transformations compose by matrix multiplication; they decompose by inversion. To find the pose of the base in the end-effector frame: $T_{60} = T_{06}^{-1}$. Use the [[Homogeneous Transformation#Equations|closed-form inverse]] — do not use `numpy.linalg.inv` for this unless you need it for numerical reasons.

## Examples and Non-Examples

- **Two-link planar arm.** Link 1 has length $L_1 = 0.3\ \text{m}$; joint 1 rotates by $\theta_1 = 30°$. Link 2 has length $L_2 = 0.2\ \text{m}$; joint 2 rotates by $\theta_2 = -45°$ relative to link 1.

  Frame $\{1\}$ relative to $\{0\}$: rotate by $\theta_1$, translate $L_1$ along new $x$:
  $$T_{01} = \begin{bmatrix}R_z(30°) & [L_1,0,0]^T\\\mathbf{0}^T&1\end{bmatrix}$$
  Frame $\{2\}$ relative to $\{1\}$: rotate by $\theta_2$, translate $L_2$:
  $$T_{12} = \begin{bmatrix}R_z(-45°) & [L_2,0,0]^T\\\mathbf{0}^T&1\end{bmatrix}$$
  End-effector pose in world frame: $T_{02} = T_{01}\,T_{12}$ — one matrix multiplication replaces two separate rotation-then-translation steps.

- **Camera-to-robot transform.** A camera frame $\{C\}$ is known relative to the robot end-effector frame $\{6\}$ as $T_{6C}$. The robot arm gives $T_{06}$. The camera-to-world transform is $T_{0C} = T_{06}\,T_{6C}$. To express a point seen by the camera in the world frame: $\tilde{\mathbf{p}}_0 = T_{0C}\,\tilde{\mathbf{p}}_C$.

- **Counter-example — reversing the product.** $T_{01}T_{12}$ puts the end-effector pose in the base frame. $T_{12}T_{01}$ is a different matrix and has no useful physical interpretation in this chain. The subscript chaining rule ($0\to1\to2$) is the guide — intermediate indices must cancel correctly.

## Resources

- ![](https://www.youtube.com/watch?v=vlb3P7arbkU)
- **[Modern Robotics — Chapter 4: Forward Kinematics playlist](https://www.youtube.com/playlist?list=PLggLP4f-rq00efLcgMcG1m4k5CKlgRcGh)**

## Practice

- Frame $\{1\}$ is at $[1, 0, 0]^T\ \text{m}$ from frame $\{0\}$ with no rotation. Frame $\{2\}$ is at $[0, 1, 0]^T\ \text{m}$ from frame $\{1\}$ with no rotation. What is the position of frame $\{2\}$'s origin in frame $\{0\}$?

> [!NOTE]- Answer
> $$T_{01} = \begin{bmatrix}I & [1,0,0]^T\\\mathbf{0}^T&1\end{bmatrix}, \qquad T_{12} = \begin{bmatrix}I & [0,1,0]^T\\\mathbf{0}^T&1\end{bmatrix}$$
> $$T_{02} = T_{01}T_{12} = \begin{bmatrix}I & [1,0,0]^T+[0,1,0]^T\\\mathbf{0}^T&1\end{bmatrix} = \begin{bmatrix}I & [1,1,0]^T\\\mathbf{0}^T&1\end{bmatrix}$$
> Frame $\{2\}$'s origin is at $[1, 1, 0]^T\ \text{m}$ in frame $\{0\}$ — pure translations simply add when there is no rotation.
