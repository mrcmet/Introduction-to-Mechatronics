---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Vector addition** combines two or more vectors into a single resultant vector. **Component decomposition** is the reverse: breaking one vector into scalar multiples of [[Unit Vectors and Basis|basis vectors]] along each axis. These two operations — composing and decomposing vectors — are the arithmetic backbone of all kinematics and dynamics calculations in this section.

Notes:
- Addition is done component-wise: $\mathbf{a} + \mathbf{b} = (a_x + b_x)\hat{\imath} + (a_y + b_y)\hat{\jmath} + (a_z + b_z)\hat{k}$. You cannot add magnitudes unless the vectors point in exactly the same direction.
- **Triangle rule (geometric view).** Place the tail of $\mathbf{b}$ at the tip of $\mathbf{a}$. The resultant $\mathbf{a} + \mathbf{b}$ runs from the tail of $\mathbf{a}$ to the tip of $\mathbf{b}$.
- Addition is commutative ($\mathbf{a} + \mathbf{b} = \mathbf{b} + \mathbf{a}$) and associative.
- **Decomposing a vector at an angle.** A vector of magnitude $F$ at angle $\theta$ from the $x$-axis decomposes as $F_x = F\cos\theta$, $F_y = F\sin\theta$. This step appears constantly in [[Free Body Diagram]] setups and in [[Kinematic Diagrams]].
- Subtraction $\mathbf{a} - \mathbf{b}$ is the same as $\mathbf{a} + (-\mathbf{b})$, where $-\mathbf{b}$ reverses all components.
- Scalar multiplication: $c\mathbf{a} = ca_x\hat{\imath} + ca_y\hat{\jmath} + ca_z\hat{k}$. Positive $c$ scales magnitude; negative $c$ also reverses direction.

## Equations

> [!equation] Vector addition (component form)
> $$\mathbf{a} + \mathbf{b} = \begin{bmatrix}a_x + b_x \\ a_y + b_y \\ a_z + b_z\end{bmatrix}$$

> [!equation] Component decomposition from magnitude and angle
> $$F_x = F\cos\theta \qquad F_y = F\sin\theta$$
>
> - $F$ — vector magnitude
> - $\theta$ — angle measured from the positive $x$-axis (counter-clockwise positive)

## Examples and Non-Examples

- **Combining velocity vectors.** A drone flies north at $\mathbf{v}_{drone} = [0, 4, 0]^T\ \text{m/s}$ in a wind blowing east at $\mathbf{v}_{wind} = [2, 0, 0]^T\ \text{m/s}$. The ground velocity is $\mathbf{v}_{ground} = [2, 4, 0]^T\ \text{m/s}$, with magnitude $\sqrt{4 + 16} \approx 4.47\ \text{m/s}$.

- **Decomposing a cable force.** A cable pulls a robot cart at $F = 80\ \text{N}$ at $30°$ above horizontal. Decomposed: $F_x = 80\cos30° = 69.3\ \text{N}$ (horizontal), $F_y = 80\sin30° = 40\ \text{N}$ (upward). These components appear on the [[Free Body Diagram]] as separate entries.

- **Counter-example — adding magnitudes only.** Two forces of 30 N and 40 N act on a joint, but at right angles. Their resultant is NOT 70 N. Add as vectors: $|\mathbf{F}_{net}| = \sqrt{30^2 + 40^2} = 50\ \text{N}$. Adding scalar magnitudes is only valid when vectors point in the same direction.

## Resources

- ![](https://www.youtube.com/watch?v=wDGTcAFRSMc)
- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)**

## Practice

- A wheeled robot applies a drive force $\mathbf{F}_1 = [15, 0]^T\ \text{N}$ and receives a friction force $\mathbf{F}_2 = [-4, 0]^T\ \text{N}$ and a sideways wall contact $\mathbf{F}_3 = [0, -6]^T\ \text{N}$. What is the net force vector and its magnitude?

> [!NOTE]- Answer
> $$\mathbf{F}_{net} = \mathbf{F}_1 + \mathbf{F}_2 + \mathbf{F}_3 = \begin{bmatrix}15 - 4 + 0\\0 + 0 - 6\end{bmatrix} = \begin{bmatrix}11\\-6\end{bmatrix}\ \text{N}$$
> $$|\mathbf{F}_{net}| = \sqrt{11^2 + 6^2} = \sqrt{121 + 36} = \sqrt{157} \approx 12.5\ \text{N}$$
