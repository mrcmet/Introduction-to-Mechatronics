---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **cross product** of two vectors $\mathbf{a}$ and $\mathbf{b}$ is a vector $\mathbf{a} \times \mathbf{b}$ that is perpendicular to both $\mathbf{a}$ and $\mathbf{b}$, with magnitude equal to the area of the parallelogram they span. It captures the "rotational" relationship between two vectors and appears wherever torque, angular momentum, or rotational velocity are involved.

Notes:
- **Right-hand rule.** Point your right-hand fingers from $\mathbf{a}$ toward $\mathbf{b}$ (through the smaller angle). Your thumb points in the direction of $\mathbf{a} \times \mathbf{b}$. Getting this right matters for torque direction and angular velocity sign.
- The cross product is **anti-commutative**: $\mathbf{a} \times \mathbf{b} = -(\mathbf{b} \times \mathbf{a})$. Order matters — reversing the operands flips the result.
- If two vectors are **parallel** (or one is zero), their cross product is the zero vector — $|\mathbf{a} \times \mathbf{b}| = |\mathbf{a}||\mathbf{b}|\sin\theta = 0$ when $\theta = 0°$ or $180°$.
- The cross product is defined only in 3D. In 2D problems, treat all vectors as lying in the $xy$-plane and the result points in the $\pm\hat{k}$ direction.
- Torque is the cross product of the position vector to the point of application and the force: $\boldsymbol{\tau} = \mathbf{r} \times \mathbf{F}$. This appears on every [[Moment Equation for Rigid Bodies]] page and in every robot joint calculation.
- The standard basis vectors obey: $\hat{\imath}\times\hat{\jmath} = \hat{k}$, $\hat{\jmath}\times\hat{k} = \hat{\imath}$, $\hat{k}\times\hat{\imath} = \hat{\jmath}$ (and reversals give negatives).

## Equations

> [!equation] Cross product — geometric form
> $$|\mathbf{a} \times \mathbf{b}| = |\mathbf{a}||\mathbf{b}|\sin\theta$$
>
> - Direction given by the right-hand rule
> - $\theta$ — angle between the vectors (0° to 180°)

> [!equation] Cross product — component form (determinant expansion)
> $$\mathbf{a} \times \mathbf{b} = \begin{vmatrix}\hat{\imath} & \hat{\jmath} & \hat{k}\\ a_x & a_y & a_z\\ b_x & b_y & b_z\end{vmatrix} = \begin{bmatrix}a_y b_z - a_z b_y\\ a_z b_x - a_x b_z\\ a_x b_y - a_y b_x\end{bmatrix}$$

## Examples and Non-Examples

- **Torque on a robot joint.** A wrench arm extends $\mathbf{r} = [0.2, 0, 0]^T\ \text{m}$ and a force $\mathbf{F} = [0, 50, 0]^T\ \text{N}$ is applied at the tip. The torque about the joint:
$$\boldsymbol{\tau} = \mathbf{r} \times \mathbf{F} = \begin{bmatrix}(0)(0)-(0)(50)\\ (0)(0)-(0.2)(0)\\ (0.2)(50)-(0)(0)\end{bmatrix} = \begin{bmatrix}0\\0\\10\end{bmatrix}\ \text{N·m}$$
The torque is 10 N·m about the $z$-axis (out of the page), consistent with the right-hand rule.

- **Checking parallelism.** Two robot links point along $\mathbf{a} = [1, 2, 0]^T$ and $\mathbf{b} = [2, 4, 0]^T$. Since $\mathbf{b} = 2\mathbf{a}$, they are parallel. Indeed, $\mathbf{a}\times\mathbf{b} = \mathbf{0}$ — no torque and no perpendicular direction can be defined.

- **Counter-example — dot vs. cross.** The [[Dot Product]] gives a scalar and detects projection/alignment. The cross product gives a vector and detects rotation/perpendicularity. Using the dot product to find a torque, or the cross product to find work, will give a wrong answer.

## Resources

- ![](https://www.youtube.com/watch?v=sSEgUPMZQE4)
- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)**
- **[Wikipedia — Cross product](https://en.wikipedia.org/wiki/Cross_product)**

## Practice

- A robot link extends from the origin to point P at $\mathbf{r} = [0.3, 0.1, 0]^T\ \text{m}$. A force $\mathbf{F} = [-20, 10, 0]^T\ \text{N}$ acts at P. What is the torque about the origin?

> [!NOTE]- Answer
> $$\boldsymbol{\tau} = \mathbf{r}\times\mathbf{F} = \begin{bmatrix}(0.1)(0)-(0)(10)\\ (0)(-20)-(0.3)(0)\\ (0.3)(10)-(0.1)(-20)\end{bmatrix} = \begin{bmatrix}0\\0\\3+2\end{bmatrix} = \begin{bmatrix}0\\0\\5\end{bmatrix}\ \text{N·m}$$
> Torque is 5 N·m about the $+z$-axis (counter-clockwise out of the page).
