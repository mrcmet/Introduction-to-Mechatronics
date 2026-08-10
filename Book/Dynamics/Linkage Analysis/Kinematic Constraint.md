---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **kinematic constraint** is a restriction that a [[Kinematic Pair|joint]] or contact places on the relative motion of two [[Link|links]], removing one or more [[Degrees of Freedom]]. Constraints are exactly what the [[Grübler–Kutzbach Equation]] subtracts to arrive at a mechanism's [[Mobility]]: every constraint you add is a freedom you take away.

Notes:
- In the plane, a [[Full Joint and Half Joint|full joint]] (revolute or prismatic) imposes 2 constraints, removing 2 of a link's 3 DOF; a half joint (cam, gear) imposes 1 constraint, removing 1. Adding up constraints and subtracting from the free-body total is the whole logic of mobility counting.
- A **holonomic** constraint restricts position directly (a pin fixes two points together). A **nonholonomic** constraint restricts only velocities and cannot be integrated back to a position rule — rolling without slipping is the classic case. See [[Holonomic and Nonholonomic Constraints]].
- **Redundant constraints** repeat a restriction another constraint already provides. They do not reduce mobility further in the ideal count, but they make the mechanism over-constrained ($M < 0$) and prone to binding unless the geometry is exact.
- A constraint removes freedom; it does not by itself create motion. Motion comes from an input (a driven [[Link|link]]) acting on whatever freedom the constraints leave behind.

## Examples and Non-Examples
- **Pin constraint.** A revolute pin ties the coupler and rocker of a [[Four-Bar Linkage]] so their pinned points move together. That is 2 constraints in the plane, which is why each pin contributes $-2$ in the [[Grübler–Kutzbach Equation]].
- **Rolling-without-slipping (nonholonomic).** A mobile robot's wheel rolling on the floor constrains its velocity (no sideways slip) without fixing its position — the robot can still reach any point, just not by moving sideways. The constraint links translational and rotational motion but never reduces reachable positions.
- **Counter-example — a redundant brace.** Adding a second link between two points a pin already holds together imposes a constraint that duplicates the pin's. It removes no *useful* freedom; instead it drives [[Mobility]] negative and can lock or bind the mechanism — the same failure the bottle-capper's anti-chatter brace produced.

## Resources
- ![](https://www.youtube.com/watch?v=hBrHcHpMXmY)
- **[Norton, *Design of Machinery* — Ch. 2, Constraints and mobility](https://www.mheducation.com/)**

## Practice
- A designer adds a slotted guide (a prismatic constraint) to a four-bar that already has $M = 1$. What happens to the mobility, and what does that mean physically?

> [!NOTE]- Answer
> A prismatic [[Full Joint and Half Joint|full joint]] adds 2 constraints, so $M$ drops from 1 to $3(n-1) - 2(j_1+1) = 1 - 2 = -1$. Mobility $-1$ means the mechanism is now **over-constrained** — it will generally bind and cannot move as intended unless the slot's geometry exactly matches the existing motion.
