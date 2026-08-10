---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **unit quaternion** is a four-element number $q = w + x\mathbf{i} + y\mathbf{j} + z\mathbf{k}$ with $\|q\| = 1$ that represents a 3D rotation. The scalar part $w$ and the vector part $\mathbf{v} = [x, y, z]^T$ together encode both the axis and angle of rotation in a form that avoids the [[Gimbal Lock|gimbal lock]] singularity, supports efficient composition, and interpolates smoothly between orientations.

Notes:
- A rotation by angle $\alpha$ about unit axis $\hat{\mathbf{n}} = [n_x, n_y, n_z]^T$ is encoded as:
$$w = \cos\!\left(\tfrac{\alpha}{2}\right), \quad \mathbf{v} = \sin\!\left(\tfrac{\alpha}{2}\right)\hat{\mathbf{n}}$$
Note the **half-angle** — this is not a typo. It is a consequence of the quaternion double-cover of $SO(3)$: both $q$ and $-q$ represent the same rotation.
- Quaternions have **4 parameters with 1 constraint** ($\|q\|=1$), giving 3 effective DOF — same as any other rotation representation, but without singularities anywhere on $SO(3)$.
- **Composing two rotations**: multiply quaternions $q_{total} = q_2 \cdot q_1$ (Hamilton product). The quaternion product is not component-wise multiplication; it follows quaternion algebra rules. Like matrix multiplication, **order matters** — see [[Rotation Order Matters]].
- **Rotating a vector** $\mathbf{p}$ by quaternion $q$: treat $\mathbf{p}$ as a pure quaternion $[0, \mathbf{p}]$, then compute $q \cdot [0, \mathbf{p}] \cdot q^*$, where $q^* = [w, -\mathbf{v}]$ is the quaternion conjugate.
- **Where you will see quaternions in practice:** ROS `geometry_msgs/Quaternion`, IMU attitude output, game engines (Unity, Unreal), SLAM systems, and any orientation filter that needs to avoid gimbal lock.
- Converting between quaternions, rotation matrices, and Euler angles is routine but error-prone due to sign conventions. Libraries like `scipy.spatial.transform`, `tf2` (ROS), and `Eigen` handle these conversions reliably — prefer them over manual formulas.

## Equations

> [!equation] Quaternion from axis–angle
> $$q = \begin{bmatrix}w\\\mathbf{v}\end{bmatrix} = \begin{bmatrix}\cos(\alpha/2)\\\sin(\alpha/2)\,\hat{\mathbf{n}}\end{bmatrix}, \qquad \|q\| = 1$$
>
> - $\alpha$ — rotation angle
> - $\hat{\mathbf{n}}$ — unit rotation axis
> - Identity (no rotation): $q = [1, 0, 0, 0]^T$

## Examples and Non-Examples

- **Encoding a 90° yaw.** A drone yaws 90° about the world $z$-axis: $\alpha = 90°$, $\hat{\mathbf{n}} = [0, 0, 1]^T$. The quaternion:
$$q = \begin{bmatrix}\cos45°\\\sin45° \cdot [0,0,1]^T\end{bmatrix} = \begin{bmatrix}0.707\\0\\0\\0.707\end{bmatrix}$$
This is the same rotation as $R_z(90°)$ — just represented differently.

- **IMU output.** An IMU reports orientation as $q = [0.924,\ 0.383,\ 0,\ 0]^T$. Decoding: $w = 0.924 = \cos(\alpha/2)$, so $\alpha = 2\cos^{-1}(0.924) \approx 45°$. The vector part $[0.383, 0, 0]^T = \sin(22.5°)[1,0,0]^T$ means the axis is $\hat{x}$. The IMU is reporting a 45° roll.

- **Counter-example — quaternion is not a rotation matrix.** You cannot multiply a regular 3D vector $\mathbf{p}$ directly by a quaternion using normal matrix multiplication. The rotation operation is the sandwich product $q\mathbf{p}q^*$. Skipping the conjugate gives the wrong result.

- **Counter-example — normalizing matters.** Due to floating-point rounding, a quaternion that starts as a unit quaternion will drift from unit magnitude over time. Periodically re-normalizing prevents the rotation representation from becoming invalid .

## Resources

- ![](https://www.youtube.com/watch?v=zjMuIxRvygQ)
- **[3Blue1Brown — Quaternions and 3D rotation (interactive)](https://eater.net/quaternions)**
- **[Wikipedia — Quaternions and spatial rotation](https://en.wikipedia.org/wiki/Quaternions_and_spatial_rotation)**
