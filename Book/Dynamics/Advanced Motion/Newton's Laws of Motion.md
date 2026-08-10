---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Newton's Laws of Motion** are three foundational principles that describe how forces cause changes in motion. Together they form the basis of classical mechanics and every equation of motion in this section of the book. The First Law defines when an object's velocity stays constant, the Second Law quantifies how force and acceleration are related, and the Third Law states that forces always come in equal-and-opposite pairs.

Notes:
- Newton's laws apply in **inertial reference frames** — frames that are not themselves accelerating. A camera fixed to a rotating robot arm is non-inertial; the laws must be modified there (fictitious forces appear). Most problems in this book assume an inertial frame.
- The Second Law is the working equation for dynamics: it directly produces the [[Equation of Motion]] for any particle or rigid body.
- All three laws together drive the standard dynamics problem-solving approach: draw a [[Free Body Diagram]] to identify every external force (First and Third Laws tell you what to include), then draw a [[Kinematic Diagrams|kinematic diagram]] to label the assumed direction of acceleration, then apply the Second Law $\sum \mathbf{F} = m\mathbf{a}$ to connect the two.
- Newton's laws are valid at engineering scales and speeds well below the speed of light. At relativistic speeds or quantum scales they break down, but this is never an issue in mechatronics.
- [[Units and Dimensional Analysis]]: the newton (N) is the derived SI unit of force — it is defined by the Second Law: $1\ \text{N} = 1\ \text{kg} \cdot \text{m/s}^2$.

## Equations

> [!equation] Newton's First Law (Law of Inertia)
> $$\sum \mathbf{F} = \mathbf{0} \implies \mathbf{v} = \text{const}$$
>
> An object at rest stays at rest, and an object in motion stays in motion at constant velocity, unless acted on by a net external force.

> [!equation] Newton's Second Law
> $$\sum \mathbf{F} = m\mathbf{a}$$
>
> - $\sum \mathbf{F}$ — net external force vector (N)
> - $m$ — mass (kg)
> - $\mathbf{a}$ — acceleration vector (m/s²)
> - The scalar form along one axis: $\sum F_x = ma_x$

> [!equation] Newton's Third Law (Action–Reaction)
> $$\mathbf{F}_{A \text{ on } B} = -\mathbf{F}_{B \text{ on } A}$$
>
> For every force that object A exerts on object B, object B exerts an equal and opposite force on object A. The pair acts on **different** bodies — they never cancel each other on a single free body diagram.

## Examples and Non-Examples

- **First Law — coasting robot.** A wheeled robot moving on a frictionless surface at constant velocity has zero net force on it. No drive torque and no friction — the First Law says it keeps moving at the same speed indefinitely.

- **Second Law — motor force.** A 5 kg robot cart accelerates at $3\ \text{m/s}^2$. What net force does the motor supply?
$$F = ma = (5)(3) = 15\ \text{N}$$
If friction of $4\ \text{N}$ opposes the motion, the motor must supply $15 + 4 = 19\ \text{N}$ to achieve this acceleration.

- **Third Law — gripper on a part.** A robot gripper squeezes a workpiece with $F = 50\ \text{N}$. The workpiece pushes back on the gripper fingers with exactly $50\ \text{N}$ in the opposite direction. Both forces are real; only the force on each body appears on that body's [[Free Body Diagram]].

- **Counter-example — Third Law pairs cancel.** A common mistake is to say "the reaction force cancels the action force, so nothing accelerates." This is wrong. Third-Law pairs act on *different* objects. The net force on one object is the sum of forces *acting on it* — the reaction force acts on the other object and never appears on the first object's FBD.

- **Counter-example — rotating reference frame.** An object on a spinning turntable appears to curve sideways even with no applied force. This apparent force (the Coriolis effect) is a fictitious force that arises because the turntable frame is non-inertial. Newton's Second Law in its basic form does not apply without adding fictitious-force correction terms.

## Resources

![](https://www.youtube.com/watch?v=kKKM8Y-u7ds)

![](https://www.youtube.com/watch?v=fn_r6GjAD-g)

**[Wikipedia — Newton's laws of motion](https://en.wikipedia.org/wiki/Newton%27s_laws_of_motion)**

## Practice

- A 12 kg drone hovers motionless in the air. (a) What is the net force on it? (b) What upward thrust force must its rotors produce if it weighs $W = 117.7\ \text{N}$? (c) If the rotors produce $135\ \text{N}$, what is the drone's acceleration?

> [!NOTE]- Answer
> **(a)** Hovering means $\mathbf{a} = 0$, so by the Second Law, $\sum F = 0$.
>
> **(b)** $\sum F_y = T - W = 0 \implies T = W = 117.7\ \text{N}$
>
> **(c)** $\sum F_y = 135 - 117.7 = 17.3\ \text{N}$
> $$a = \frac{\sum F}{m} = \frac{17.3}{12} \approx 1.44\ \text{m/s}^2 \text{ (upward)}$$
