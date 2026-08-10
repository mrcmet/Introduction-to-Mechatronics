---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> A **shear force diagram** (SFD) is a plot of the internal shear force $V$ as a function of position $x$ along a beam. It is constructed from the [[Support Reactions]] and applied loads using the relationship $dV/dx = -w(x)$, where $w(x)$ is the distributed load intensity at position $x$.

Notes:
- **Sign convention (standard):** 
	- $V$ is positive when the resultant of forces to the left of a cut acts upward 
	- Or equivalently, when the left segment tends to rotate clockwise about the cut.
- **Construction rules — read left to right:**
  1. Start at $x = 0$ with $V = 0$ (free end) or $V = R_A$ (reaction at the first support).
  2. **Point load or reaction:** $V$ jumps instantaneously — upward force causes a positive (upward) jump; downward force causes a negative (downward) jump.
  3. **No distributed load:** $V$ is constant — horizontal line.
  4. **Uniform distributed load ($w$):** $V$ changes linearly with slope $-w$ (downward UDL decreases $V$).
  5. **Triangular distributed load:** $V$ changes parabolically.
  6. At the far end, $V$ must return to zero — if it doesn't, the reactions are wrong.
- The SFD and [[Bending Moment Diagram]] are linked: the slope of the moment diagram at any point equals the shear force at that point ($dM/dx = V$). Equivalently, the change in moment between two points equals the area under the shear diagram between those points.
- The shear force is zero where the bending moment is at a local maximum or minimum — useful for locating the critical bending stress location.
- The SFD is the prerequisite for the [[Bending Moment Diagram]] and ultimately for computing [[Bending Stress]] and [[Transverse Shear Stress in Beams]].
![[Shear Diagram.svg]]
## Equations

> [!equation] Distributed Load — Shear Slope Relationship
> $$\frac{dV}{dx} = -w(x)$$
>
> - $V$ — internal shear force at position $x$ (N)
> - $w(x)$ — distributed load intensity, positive upward (N/m)
> - Negative sign: a downward distributed load decreases $V$ moving left to right

> [!equation] Shear–Moment Relationship
> $$\frac{dM}{dx} = V \qquad \Longleftrightarrow \qquad \Delta M = \int_{x_1}^{x_2} V\, dx$$
>
> - The change in bending moment between two points equals the **area under the SFD** between those points
> - Where $V = 0$, $M$ is at a local maximum or minimum

## Examples and Non-Examples

- **Simply supported beam, central point load.** Beam length $L = 4\ \text{m}$, load $P = 20\ \text{kN}$ at mid-span. [[Support Reactions]]: $A_y = B_y = 10\ \text{kN}$.

  | Region | $V$ |
  |--------|-----|
  | $0 < x < 2\ \text{m}$ | $+10\ \text{kN}$ (constant — no distributed load) |
  | At $x = 2\ \text{m}$ | Jumps from $+10$ to $-10\ \text{kN}$ (20 kN downward load) |
  | $2\ \text{m} < x < 4\ \text{m}$ | $-10\ \text{kN}$ (constant) |
  | At $x = 4\ \text{m}$ | Jumps from $-10$ to $0\ \text{kN}$ ($+10\ \text{kN}$ reaction at $B$) ✓ |

  The SFD is a rectangle split at mid-span — positive left half, negative right half.

- **Simply supported beam, full-span UDL.** Beam length $L = 6\ \text{m}$, $w = 4\ \text{kN/m}$. Reactions: $A_y = B_y = 12\ \text{kN}$.

  $V$ starts at $+12\ \text{kN}$ at $x = 0$, decreases linearly at $-4\ \text{kN/m}$, reaches $0$ at $x = 3\ \text{m}$ (midspan), and reaches $-12\ \text{kN}$ at $x = 6^-\ \text{m}$, then jumps back to zero at the roller. The SFD is a straight diagonal line — the zero crossing at mid-span is where $M$ is maximum.

- **Counter-example — the SFD is not the stress distribution.** A student sketches the SFD and assumes the highest shear stress in the cross-section occurs at the point of maximum $V$. The shear *force* is largest there, but the shear *stress* distribution within the cross-section is parabolic and depends on $Q$, $I$, and $t$ — see [[Transverse Shear Stress in Beams]]. Maximum $V$ does not necessarily mean maximum $\tau$ across every geometry.

## Resources
- ![](https://youtu.be/MvBqCeZllpQ?si=S85rXrCI9ee7avsC)
- ![](https://youtu.be/C-FEVzI8oe8?si=mYzCq1ja-B7ETQDW)
**[Table of Common Shear Force Diagrams](https://mechanicalc.com/reference/beam-analysis#shear-moment-diagrams)**

**[Beam Analysis Quick Reference (Formula Sheet)](https://mechanicalc.com/reference/beam-analysis-quick-reference)**

**[Beam Analysis Calculator and Plotter](https://mechanicalc.com/calculators/beam-analysis/#divResults)**
## Practice
- A simply supported beam of length $L = 5\ \text{m}$ (pin at $A$, roller at $B$) carries a UDL of $w = 6\ \text{kN/m}$ over the left 3 m only. Draw the SFD and identify where $V = 0$.

> [!NOTE]- Answer
> **Reactions** (from [[Support Reactions]] worked example on that page): $A_y = 12.6\ \text{kN}$, $B_y = 5.4\ \text{kN}$.
>
> | Region | $V$ |
> |--------|-----|
> | At $x = 0^+$ | $V = +12.6\ \text{kN}$ |
> | $0 \leq x \leq 3\ \text{m}$ | $V = 12.6 - 6x$ (linear, slope $= -6\ \text{kN/m}$) |
> | At $x = 3\ \text{m}$ | $V = 12.6 - 6(3) = -5.4\ \text{kN}$ |
> | $3\ \text{m} < x < 5\ \text{m}$ | $V = -5.4\ \text{kN}$ (constant — no load) |
> | At $x = 5\ \text{m}$ | Jumps from $-5.4$ to $0\ \text{kN}$ ✓ |
>
> **Zero crossing:** $V = 0$ when $12.6 - 6x = 0 \implies x = 2.1\ \text{m}$ — this is where the bending moment is maximum.
