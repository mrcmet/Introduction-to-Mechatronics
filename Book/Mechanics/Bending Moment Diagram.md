---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> A **bending moment diagram** (BMD) is a plot of the internal bending moment $M(x)$ as a function of position $x$ along a beam. It is constructed after solving for [[Support Reactions]] using the [[Internal Forces in Beams|cut-and-isolate method]] at successive cross-sections, and shows where the beam bends and by how much under its applied loads.

Notes:
- The slope of the BMD equals the shear force at that location: $\frac{dM}{dx} = V$. The maximum moment therefore occurs where $V = 0$ (or at a fixed wall where a reaction moment is applied).
- Under a [[Point Load and Distributed Load|point load]] the BMD changes slope abruptly — the diagram is piecewise linear between loads.
- Under a [[Point Load and Distributed Load|uniform distributed load]] of intensity $w$, moment varies as a quadratic — the BMD curves parabolically over the loaded region.
- Sign convention (standard): positive $M$ causes the beam to **sag** (concave up, tension on the bottom fiber); negative $M$ causes **hogging** (concave down). Always state the convention you're using.
- Always draw the BMD alongside the [[Shear Force Diagram]] — together they give a complete picture of [[Internal Forces in Beams]].

## Examples and Non-Examples

- **Simply supported beam with a central point load.** Beam length $L = 6\ \text{m}$, point load $P = 30\ \text{kN}$ at mid-span. Reactions: $A_y = B_y = 15\ \text{kN}$.

  For $0 \leq x \leq 3\ \text{m}$: $\quad M(x) = 15x$

  For $3 \leq x \leq 6\ \text{m}$: $\quad M(x) = 15x - 30(x - 3) = 90 - 15x$

  The BMD is triangular, peaking at mid-span:
  $$M_{\max} = 15(3) = 45\ \text{kN·m (sagging)}$$

- **Simply supported beam with full-span UDL.** Beam length $L = 4\ \text{m}$, UDL $w = 10\ \text{kN/m}$. Reactions: $A_y = B_y = 20\ \text{kN}$.
  $$M(x) = 20x - \tfrac{1}{2}(10)x^2 = 20x - 5x^2$$
  The BMD is parabolic. Maximum at $x = 2\ \text{m}$ (where $V = 0$):
  $$M_{\max} = 20(2) - 5(4) = 20\ \text{kN·m}$$

- **Counter-example — the peak is not always at mid-span.** A simply supported beam with an off-center point load reaches maximum moment directly under the load, not at the geometric center. The rule is: the peak is wherever $V = 0$, which shifts with the load position.

## Resources
- ![](https://www.youtube.com/watch?v=REPLACE_WITH_VIDEO_ID)
- **[Engineering Toolbox — Beam Stress and Deflection](https://www.engineeringtoolbox.com/beam-stress-deflection-d_1312.html)** — moment formulas for common configurations.

## Practice
- A simply supported beam of length $L = 8\ \text{m}$ carries a UDL of $w = 5\ \text{kN/m}$ over its full length. Find the bending moment at $x = 2\ \text{m}$ and $x = 4\ \text{m}$, and identify the maximum moment and its location.

> [!NOTE]- Answer
> Reactions: $A_y = B_y = \frac{5 \times 8}{2} = 20\ \text{kN}$
>
> $M(x) = 20x - 2.5x^2$
>
> $M(2) = 40 - 10 = 30\ \text{kN·m}$
>
> $M(4) = 80 - 40 = 40\ \text{kN·m}$
>
> Maximum where $V = 0$: $20 - 5x = 0 \Rightarrow x = 4\ \text{m}$ (mid-span by symmetry). $M_{\max} = 40\ \text{kN·m}$.
