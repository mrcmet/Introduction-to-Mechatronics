---
tags: [mechanics, pre-release]
---
#mechanics #pre-release

## Definition
> [!definition]
> A body is in **static equilibrium** when the net force and net moment acting on it are both zero, so it neither accelerates nor angularly accelerates. In the plane this is three scalar conditions — $\sum F_x = 0$, $\sum F_y = 0$, $\sum M = 0$ — applied to a [[Free Body Diagram]] to solve for unknown forces such as [[Support Reactions]] and [[Joint Reaction Force|joint reactions]].

Notes:
- **Planar problems give three equations**, so you can solve for at most three unknowns. Spatial problems give six ($\sum F_x, \sum F_y, \sum F_z, \sum M_x, \sum M_y, \sum M_z$).
- If the unknowns outnumber the available equations, the body is **statically indeterminate** and equilibrium alone cannot solve it — you also need compatibility of deflections. See [[Statically Indeterminate Systems]].
- **Strategy:** take moments about a point where an unknown force acts. Its moment arm is zero, so it drops out and you solve the remaining unknown directly — the same trick used on [[Support Reactions]].
- Equilibrium is the $\mathbf{a} = 0$ special case of [[Newton's Second Law]]. The moment a body accelerates, $\sum F = m\mathbf{a} \neq 0$ and the equilibrium equations no longer hold — that is the boundary between statics and dynamics, and where a [[Kinematic Diagrams|kinetic diagram]] enters.
- A **two-force member** (a link loaded only at two pins, no other forces) is in equilibrium only if those two forces are equal, opposite, and along the line joining the pins. This is why a coupler carries pure axial load.

## Examples and Non-Examples
- **Solving a reaction with moments.** A horizontal link is pinned at $A$, held by a vertical cable at $C$ ($0.20\ \text{m}$ from $A$), and loaded with $P = 80\ \text{N}$ downward at $B$ ($0.30\ \text{m}$ from $A$). Taking moments about $A$: $\sum M_A = T(0.20) - 80(0.30) = 0 \Rightarrow T = 120\ \text{N}$. Then $\sum F_y = 0$ gives $A_y = 80 - 120 = -40\ \text{N}$ — the pin pulls *down* with $40\ \text{N}$, the negative sign flagging that the assumed direction was reversed.
- **Two-force coupler.** A connecting rod pinned at each end with no other load is in equilibrium only when the two pin forces are collinear and opposite. That constraint is what lets you treat a coupler as carrying a single axial force when finding a [[Joint Reaction Force]].
- **Counter-example — an accelerating body.** A robot link swinging under gravity is *not* in static equilibrium: it has angular acceleration, so $\sum M \neq 0$. Writing $\sum M = 0$ for it would give the wrong pin forces. Accelerating bodies need the dynamics form, not equilibrium.

## Resources
- ![](https://www.youtube.com/watch?v=aHAqUWL4u9E)
- **[Hibbeler, *Engineering Mechanics: Statics* — Equilibrium of a Rigid Body](https://www.pearson.com/)**

## Practice
- A 0.5 m uniform bar is pinned at $A$ (left end) and carries a $60\ \text{N}$ downward load at its right end. A vertical support at the midpoint ($0.25\ \text{m}$) holds it. Find the support force and the pin reaction at $A$.

> [!NOTE]- Answer
> $\sum M_A = 0:\ S(0.25) - 60(0.50) = 0 \Rightarrow S = 120\ \text{N}$ (up). $\sum F_y = 0:\ A_y + 120 - 60 = 0 \Rightarrow A_y = -60\ \text{N}$, i.e. the pin reaction is $60\ \text{N}$ **downward**.
