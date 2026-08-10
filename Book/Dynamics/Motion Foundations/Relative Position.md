---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **relative position** of point $A$ with respect to point $B$ is the [[Position Vector]] drawn from $B$ to $A$, written $\mathbf{r}_{A/B}$ and read as "position of $A$ as seen from $B$." It tells you where $A$ sits if you stand at $B$ and look outward, with both points expressed in the same [[Reference Frame]]. When $B$ is the origin of that frame, relative position collapses back to the ordinary [[Position]] of $A$.

Notes:
- **Subscript notation.** The symbol $\mathbf{r}_{A/B}$ uses an "of-over" convention: the point *of* interest is on top, the point you are measuring *from* is on the bottom. Read the slash as the word "from." This same A/B notation carries directly into [[Relative Velocity]] and relative acceleration.
- **Swap the subscripts, flip the sign.** $\mathbf{r}_{A/B} = -\mathbf{r}_{B/A}$. The arrow from $B$ to $A$ is the same length as the arrow from $A$ to $B$, just pointing the other way. Forgetting this sign is one of the most common bugs in multi-body kinematics.
- **Both endpoints must share a frame.** To compute $\mathbf{r}_A - \mathbf{r}_B$ component-by-component, $\mathbf{r}_A$ and $\mathbf{r}_B$ must be expressed in the same [[Coordinate Frames|coordinate frame]]. If $A$ is given in a world frame and $B$ in a robot-base frame, transform one into the other first.
- **Relative position is origin-independent.** Shift the origin of the shared frame and both $\mathbf{r}_A$ and $\mathbf{r}_B$ change by the same offset, so the difference $\mathbf{r}_{A/B}$ is unchanged. Only the frame's *orientation* matters for the components.
- **Frame choice matters when the frame moves.** If $B$ is the origin of a [[Moving Reference Frame]], then $\mathbf{r}_{A/B}$ describes where $A$ appears to an observer riding along with $B$. This is the foundation of [[Relative Velocity]] and of how a robot sees a workpiece from its own end-effector frame.
- **It is still a vector.** $\mathbf{r}_{A/B}$ has a magnitude $|\mathbf{r}_{A/B}|$ — the straight-line distance between the two points — and a direction. Distance alone is not enough to reconstruct relative position.

## Equations

> [!equation] Relative position from two absolute positions
> $$\mathbf{r}_{A/B} = \mathbf{r}_A - \mathbf{r}_B$$
>
> - $\mathbf{r}_A$ — position of point $A$ in the chosen [[Reference Frame]] (m)
> - $\mathbf{r}_B$ — position of point $B$ in the *same* frame (m)
> - $\mathbf{r}_{A/B}$ — position of $A$ relative to $B$ (m)

> [!equation] Subscript-swap identity
> $$\mathbf{r}_{A/B} = -\mathbf{r}_{B/A}$$
>
> - Reversing the reference point reverses the vector.

## Examples and Non-Examples

- **Two robots on a factory floor.** AGV $A$ is at $\mathbf{r}_A = [4,\,2,\,0]^T\ \text{m}$ and AGV $B$ is at $\mathbf{r}_B = [1,\,6,\,0]^T\ \text{m}$, both measured in the same shop-floor frame. The position of $A$ relative to $B$ is
$$\mathbf{r}_{A/B} = \mathbf{r}_A - \mathbf{r}_B = \begin{bmatrix} 3 \\ -4 \\ 0 \end{bmatrix}\ \text{m}$$
so an observer standing on $B$ and looking down the shop's $+x$ axis sees $A$ three meters ahead and four meters to the right. The magnitude $|\mathbf{r}_{A/B}| = 5\ \text{m}$ is the line-of-sight separation that a collision-avoidance check would use.

- **End-effector relative to a workpiece.** A 6-axis arm's tool tip is at $\mathbf{r}_{\text{tip}} = [0.85,\,0.10,\,0.40]^T\ \text{m}$ in the robot-base frame, and the part being machined is fixtured at $\mathbf{r}_{\text{part}} = [0.80,\,0.00,\,0.35]^T\ \text{m}$ in the same frame. Then $\mathbf{r}_{\text{tip}/\text{part}} = [0.05,\,0.10,\,0.05]^T\ \text{m}$ is the offset the motion controller is trying to drive to zero. Subtracting in the *workpiece* frame is what lets the same g-code run regardless of where the fixture is bolted on the table.

- **AGV approaching a waypoint.** An AGV's pose in a warehouse map is $\mathbf{r}_{\text{AGV}} = [12.4,\,7.1]^T\ \text{m}$ and its next waypoint sits at $\mathbf{r}_{\text{wp}} = [12.0,\,9.6]^T\ \text{m}$. The waypoint as seen from the AGV is $\mathbf{r}_{\text{wp}/\text{AGV}} = [-0.4,\,2.5]^T\ \text{m}$ — mostly "north," slightly "west." Heading control steers to drive this vector's magnitude toward zero, and the swap identity lets the same code report "AGV is $[0.4,\,-2.5]^T$ from waypoint" to a dispatcher dashboard.

- **Counter-example — absolute position is not relative position.** Saying "the gripper is at $\mathbf{r} = [0.85,\,0.10,\,0.40]^T\ \text{m}$" only locates the gripper in *one specific* frame — usually the robot base. It does not tell you where the gripper is with respect to the part, the camera, or another robot. Without a "/" in the subscript, you have an [[Position|absolute position]], not a relative one.

- **Counter-example — distance is not relative position.** "Robot $A$ is 5 m from robot $B$" gives only $|\mathbf{r}_{A/B}|$. The two robots could lie anywhere on a sphere of radius 5 m around each other; the direction is missing. Relative position is a vector and needs both magnitude and direction.

## Resources

- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-style dynamics videos; search for "relative motion" for two-point and two-frame worked examples.
- **[Wikipedia — Relative position](https://en.wikipedia.org/wiki/Relative_velocity#Relative_position)** — concise reference for the $\mathbf{r}_{A/B} = \mathbf{r}_A - \mathbf{r}_B$ identity and its role in relative-motion kinematics.

## Practice

- A pick-and-place cell has a camera mounted on the gantry at $\mathbf{r}_{\text{cam}} = [0.50,\,0.20,\,0.90]^T\ \text{m}$ and a part on the conveyor at $\mathbf{r}_{\text{part}} = [0.65,\,-0.10,\,0.10]^T\ \text{m}$, both expressed in the cell's base frame. (a) Find $\mathbf{r}_{\text{part}/\text{cam}}$, the position of the part as seen from the camera. (b) Find $\mathbf{r}_{\text{cam}/\text{part}}$ without redoing the subtraction. (c) What is the straight-line distance from the camera to the part?

> [!NOTE]- Answer
> **(a) Part relative to camera.**
> $$\mathbf{r}_{\text{part}/\text{cam}} = \mathbf{r}_{\text{part}} - \mathbf{r}_{\text{cam}} = \begin{bmatrix} 0.65 - 0.50 \\ -0.10 - 0.20 \\ 0.10 - 0.90 \end{bmatrix} = \begin{bmatrix} 0.15 \\ -0.30 \\ -0.80 \end{bmatrix}\ \text{m}$$
> The part sits 0.15 m forward, 0.30 m to the right, and 0.80 m below the camera.
>
> **(b) Camera relative to part.**
> Swap subscripts, flip sign — no new subtraction needed:
> $$\mathbf{r}_{\text{cam}/\text{part}} = -\mathbf{r}_{\text{part}/\text{cam}} = \begin{bmatrix} -0.15 \\ 0.30 \\ 0.80 \end{bmatrix}\ \text{m}$$
>
> **(c) Distance.**
> $$|\mathbf{r}_{\text{part}/\text{cam}}| = \sqrt{0.15^2 + 0.30^2 + 0.80^2} = \sqrt{0.0225 + 0.09 + 0.64} \approx 0.867\ \text{m}$$
> The magnitude is the same whether you compute it from $\mathbf{r}_{\text{part}/\text{cam}}$ or $\mathbf{r}_{\text{cam}/\text{part}}$ — the sign flip cancels under the square.
