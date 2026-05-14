---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Support reactions** are the forces and moments that supports exert on a beam to maintain static equilibrium under applied loads. They are found by drawing a [[Free Body Diagram]] of the entire beam and applying the three equilibrium equations: $\sum F_{x} = 0$, $\sum F_{y} = 0$, $\sum F_{z} = 0$ and $\sum M_{x} = 0$, $\sum M_{y} = 0$, $\sum M_{z} = 0$.

Notes:
- The number and type of reactions depend on the [[Beam End Conditions]]: a roller gives one force, a pin gives two forces, a fixed support gives two forces and a moment.
- **Strategy:** take moments about a point where multiple unknowns act — their moment arms are zero and they drop out of the equation, leaving a single unknown to solve for directly.
- Always check your result: sum forces in both directions and confirm they equal zero with the solved values.
- Reactions are the starting point for constructing [[Internal Forces in Beams]], the [[Shear Force Diagram]], and the [[Bending Moment Diagram]]. An error here propagates through every downstream calculation.
![[Supports and reactions.svg]]
## Examples and Non-Examples

- **Simply supported beam, point load.** A 6 m beam (pin at $A$, roller at $B$) carries $P = 24\ \text{kN}$ at $x = 2\ \text{m}$ from $A$.
$$\sum M_A = 0: \quad -24(2) + B_y(6) = 0 \implies B_y = 8\ \text{kN}$$
$$\sum F_y = 0: \quad A_y + 8 - 24 = 0 \implies A_y = 16\ \text{kN}$$
$$\sum F_x = 0: \quad A_x = 0$$

- **Simply supported beam, UDL.** The same 6 m beam now carries a full-span UDL $w = 10\ \text{kN/m}$. Resultant = $60\ \text{kN}$ at $x = 3\ \text{m}$ (midspan). By symmetry: $A_y = B_y = 30\ \text{kN}$.

- **Cantilever, point load at free end.** A 4 m cantilever (fixed at $A$, free at $B$) carries $P = 10\ \text{kN}$ downward at $B$.
$$\sum F_y = 0: \quad R_{Ay} - 10 = 0 \implies R_{Ay} = 10\ \text{kN}\ \text{(upward)}$$
$$\sum M_A = 0: \quad M_{wall} - 10(4) = 0 \implies M_{wall} = 40\ \text{kN·m}\ \text{(counterclockwise)}$$

- **Counter-example — skipping the FBD.** Solving for reactions by inspection without drawing the [[Free Body Diagram]] works for symmetric cases but fails when loads are offset or when a fixed end is present. The moment reaction at a wall is easy to overlook without a systematic FBD.

## Resources

![](https://youtu.be/aHAqUWL4u9E?si=kCbnsFA0C0rFE5b_)

## Practice
- A 8 m simply supported beam (pin at $A$, roller at $B$) carries a point load $P = 30\ \text{kN}$ at $x = 3\ \text{m}$ from $A$ and a UDL of $w = 5\ \text{kN/m}$ over the full span. Find $A_y$ and $B_y$.

> [!NOTE]- Answer
> **Resultant of UDL:** $F_R = 5 \times 8 = 40\ \text{kN}$ at $x = 4\ \text{m}$.
>
> **Take moments about A:**
> $$\sum M_A = 0: \quad -30(3) - 40(4) + B_y(8) = 0$$
> $$B_y = \frac{90 + 160}{8} = \frac{250}{8} = 31.25\ \text{kN}$$
>
> **Sum vertical forces:**
> $$\sum F_y = 0: \quad A_y + 31.25 - 30 - 40 = 0 \implies A_y = 38.75\ \text{kN}$$
