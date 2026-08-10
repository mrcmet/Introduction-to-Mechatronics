---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Mass** is a scalar measure of how much matter an object contains and how strongly it resists a change in velocity (inertia). **Weight** is the gravitational force acting on that mass. The two are related by $W = mg$, where $g$ is the local gravitational acceleration. Mass is an intrinsic property of the object; weight depends on where the object is.

Notes:
- Mass is measured in kilograms (kg). Weight is a force, measured in newtons (N). Saying something "weighs 5 kg" is informal — the physically correct statement is "has a mass of 5 kg" or "weighs 49.1 N."
- On Earth's surface, $g \approx 9.81\ \text{m/s}^2$. This varies slightly with latitude and altitude but is treated as constant for all problems in this book unless stated otherwise.
- Weight is a vector — it points toward the center of the Earth (downward in most coordinate systems). Mass is a scalar — it has no direction.
- The distinction matters in dynamics: $\sum \mathbf{F} = m\mathbf{a}$ uses mass on the right-hand side, not weight. Weight is one of the forces that appears on the left-hand side in a [[Free Body Diagram]].
- In space (orbital free fall), an astronaut's **mass** is unchanged but they are **weightless** — the gravitational force is being used entirely to sustain the orbital trajectory, so no contact force is felt.
- [[Units and Dimensional Analysis]]: $W = mg$ is dimensionally consistent — $[\text{kg}][\text{m/s}^2] = [\text{N}]$.
- Every time you write a [[Newton's Laws of Motion|Newton's Second Law]] equation that includes gravity, you are implicitly using $W = mg$ as the gravitational force term.

## Equations

> [!equation] Weight
> $$W = mg$$
>
> - $W$ — weight force (N), directed downward
> - $m$ — mass (kg)
> - $g$ — gravitational acceleration = $9.81\ \text{m/s}^2$ (Earth surface, standard)

## Examples and Non-Examples

- **Converting mass to weight.** A mechatronic assembly has a mass of $m = 3.2\ \text{kg}$. Its weight on Earth:
$$W = mg = (3.2)(9.81) = 31.4\ \text{N}$$
This is the downward force that its mounting brackets must support in a static system, and the force that appears on the [[Free Body Diagram]] when analyzing vertical motion.

- **Self-balancing robot — why mass matters.** The two-wheeled balancer used throughout this section has a body mass of $m_b$ and wheel masses $m_w$. The gravitational force on the body ($m_b g$ downward through the center of mass) is the destabilizing load that the control system must counteract. Using weight instead of mass here would produce incorrect equations of motion.

- **Weight on the Moon.** An object with $m = 10\ \text{kg}$ weighs $W = 10 \times 9.81 = 98.1\ \text{N}$ on Earth. On the Moon, $g \approx 1.62\ \text{m/s}^2$, so $W = 10 \times 1.62 = 16.2\ \text{N}$. The mass stays at 10 kg — only the weight changes.

- **Counter-example — "add the weights."** When combining two objects into a system, add their **masses** to get total mass: $m_{total} = m_1 + m_2$. Adding their weights gives the total gravitational force, which is numerically the same only because $g$ is common to both. Always track mass in dynamics equations; convert to weight only when writing the force terms.

## Resources

![](https://www.youtube.com/watch?v=nRTADi9LhyA)

![](https://www.youtube.com/watch?v=xnUKGLiZ1MA)

**[Wikipedia — Mass versus weight](https://en.wikipedia.org/wiki/Mass_versus_weight)**

## Practice

- A robot arm carries a payload of $m = 4.5\ \text{kg}$. (a) What is the gravitational force the arm must support when stationary? (b) If the arm accelerates the payload upward at $a = 3\ \text{m/s}^2$, what net upward force is required?

> [!NOTE]- Answer
> **(a) Gravitational force (weight).**
> $$W = mg = (4.5)(9.81) = 44.1\ \text{N (downward)}$$
>
> **(b) Net force for upward acceleration.**
> Let $F$ be the upward contact force from the arm.
> $$\sum F_y = F - W = ma$$
> $$F = m(a + g) = 4.5(3 + 9.81) = 4.5 \times 12.81 = 57.6\ \text{N}$$
