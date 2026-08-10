---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **kinematic diagram** is a simplified sketch of a body or system that labels the kinematic quantities assumed or expected during motion — typically the direction of acceleration $\mathbf{a}$, velocity $\mathbf{v}$, or displacement $\Delta \mathbf{x}$. It is drawn *in addition to* a [[Free Body Diagram]], not instead of it. The FBD captures all external forces; the kinematic diagram captures how the body is moving or is assumed to move.

Notes:
- The two diagrams serve two different sides of Newton's Second Law: the [[Free Body Diagram]] organizes the $\sum \mathbf{F}$ side; the kinematic diagram labels the $m\mathbf{a}$ side. Together they make it easier to write correct equations of motion without sign errors.
- **What goes on a kinematic diagram:**
    - The acceleration vector $\mathbf{a}$ (or components $a_x$, $a_y$) with an assumed positive direction
    - Velocity direction arrows if the kinematics of the problem require them
    - Displacement direction or path of motion
    - Angular acceleration $\alpha$ for rotating bodies (Phase 6 onward)
- **What does NOT go on a kinematic diagram:** forces. The moment a force arrow appears, you are drawing a free body diagram.
- Sign convention is set on the kinematic diagram first. Once you pick a positive direction for $\mathbf{a}$, that same direction is positive on the FBD. Keeping the two diagrams consistent is what makes equations of motion come out with the right signs.
- If you work through the math and get a negative value for a quantity you assumed positive on the kinematic diagram, the result is still correct — the negative sign means the actual direction is opposite to your assumption. This is normal and does not indicate an error.
- For problems involving connected bodies (Atwood machines, robot links, multi-body chains), each body gets its own FBD and its own kinematic diagram. The kinematic diagrams for connected bodies must be consistent: if body A accelerates right, the kinematic constraint determines how body B must accelerate.
- In 2D rigid-body problems (Phase 6–7), the kinematic diagram will show both translational acceleration of the center of mass and angular acceleration $\alpha$ of the body, alongside the corresponding forces and moments on the FBD.

## Examples and Non-Examples

- **Particle on an incline.** A block slides down a frictionless incline at angle $\theta$. The FBD shows two forces: normal force $N$ perpendicular to the surface, and weight $W = mg$ straight down. The kinematic diagram shows a single acceleration arrow $a$ pointing down the slope (the assumed direction of motion). Setting up $\sum F_{\parallel} = ma$ along the slope gives $mg\sin\theta = ma$, so $a = g\sin\theta$.

- **Robot cart with cable.** A 3 kg cart is pulled along a horizontal track by a cable. The FBD has: tension $T$ to the right, friction $f$ to the left, normal force $N$ up, weight $W$ down. The kinematic diagram has: acceleration $a$ pointing to the right (assumed direction). $\sum F_x = T - f = ma$ immediately follows from aligning the two diagrams.

- **Drone accelerating upward.** The FBD shows thrust $F_T$ upward and weight $W = mg$ downward. The kinematic diagram shows $a$ pointing upward. Writing $\sum F_y = F_T - W = ma$ and solving gives $F_T = m(a + g)$ — identical to the [[Weight and Mass]] practice problem. Separating the two diagrams makes the sign structure obvious.

- **Counter-example — putting $ma$ on the FBD.** Some older textbooks draw an "$ma$ force" arrow directly on the free body diagram as if it were a real force. This is D'Alembert's principle, a valid alternative formulation, but it blurs the line between forces and kinematics and is not the approach used in this book. Here, $ma$ always lives on the kinematic diagram side; the FBD shows real forces only.

- **Counter-example — acceleration arrow on a static FBD.** If a structure is in static equilibrium ($\mathbf{a} = 0$), there is no kinematic diagram — just the FBD. Adding a zero-acceleration arrow is harmless but unnecessary. Kinematic diagrams are for dynamics problems where acceleration is non-zero and its direction must be tracked.

## Resources

![](https://www.youtube.com/watch?v=i2D1CxJqMpY)

**[Engineering Mechanics: Dynamics — Hibbeler, *Free Body and Kinetic Diagrams* section](https://www.pearson.com/en-us/subject-catalog/p/engineering-mechanics-dynamics/P200000003485)**

## Practice

- A 2 kg block is pushed along a horizontal surface by a horizontal force $F = 20\ \text{N}$. Kinetic friction opposes motion with $f_k = 6\ \text{N}$. (a) Draw and describe the FBD. (b) Draw and describe the kinematic diagram. (c) Write the equation of motion and find the acceleration.

> [!NOTE]- Answer
> **(a) FBD** — Four forces on the block: applied force $F = 20\ \text{N}$ to the right, friction $f_k = 6\ \text{N}$ to the left, normal force $N$ upward, weight $W = mg = 19.6\ \text{N}$ downward. No acceleration arrows appear here.
>
> **(b) Kinematic diagram** — One arrow: acceleration $a$ pointing to the right (assumed positive direction, consistent with the net force direction). No force arrows here.
>
> **(c) Equation of motion** — Align the FBD and kinematic diagram along the horizontal axis:
> $$\sum F_x = F - f_k = ma$$
> $$20 - 6 = 2a$$
> $$a = 7\ \text{m/s}^2 \text{ (to the right)}$$
