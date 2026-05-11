---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Beam end conditions** describe how each end of a beam is supported, determining which [[Support Reactions]] (forces and moments) are present and which displacements or rotations are constrained. The three fundamental support types are the **pin**, the **roller**, and the **fixed** (encastre) support.

Notes:
- **Pin support:** prevents translation in *both* horizontal and vertical directions; allows rotation. Provides two reaction forces ($R_x$, $R_y$); no reaction moment.
- **Roller support:** prevents translation in one direction (typically vertical); allows horizontal movement and rotation. Provides one reaction force; no reaction moment.
- **Fixed support:** prevents all translation *and* rotation. Provides two reaction forces *and* one reaction moment ($M_{wall}$). A beam fixed at one end and free at the other is a **cantilever**.
- A **simply supported beam** (pin at one end, roller at the other) has three unknowns total ($A_x$, $A_y$, $B_y$) and three equilibrium equations — statically determinate. Adding supports beyond this makes the beam **statically indeterminate**, requiring compatibility equations to solve.
- End conditions set the boundary conditions for [[Beam Deflection]]: a pin or roller forces deflection to zero at that point; a fixed end forces both deflection and slope to zero.

## Examples and Non-Examples

- **Simply supported beam (pin–roller).** The most common configuration in introductory problems. The pin at the left provides $A_x$ and $A_y$; the roller at the right provides $B_y$. Three unknowns, three equations — solvable by statics alone. Moment is zero at both ends.

- **Cantilever beam (fixed–free).** A shelf bracket or diving board. The wall provides $R_x$, $R_y$, and a reaction moment $M_{wall}$. The free end can deflect and rotate freely. The [[Bending Moment Diagram]] reaches its maximum value at the fixed end.

- **Fixed–fixed beam.** Both ends are built into walls. Four unknown reactions ($R_{xA}$, $R_{yA}$, $M_A$, $R_{yB}$, $M_B$) against three equilibrium equations — statically indeterminate to the second degree. Requires compatibility of [[Beam Deflection]] to solve fully.

- **Counter-example — a free end is not a support.** A free end imposes no constraints: deflection and rotation are both unconstrained, and there are zero reaction forces or moments there. Treating a free end as providing any reaction is a common error when drawing [[Free Body Diagram]]s.

## Resources
- ![](https://www.youtube.com/watch?v=tBnB2HFk_uQ)
- **[Engineering Toolbox — Beams, Supported at Both Ends](https://www.engineeringtoolbox.com/beams-supported-both-ends-d_817.html)** — reaction and deflection formulas for common configurations.

## Practice
- A beam of length $L = 5\ \text{m}$ is fixed at the left end (cantilever) and carries a uniform distributed load of $w = 8\ \text{kN/m}$ over its full length. How many unknown reactions are there, and is this beam statically determinate?

> [!NOTE]- Answer
> A fixed support provides $R_x$, $R_y$, and $M_{wall}$ — three unknowns. There are also three equilibrium equations ($\sum F_x = 0$, $\sum F_y = 0$, $\sum M = 0$). Three unknowns, three equations — **statically determinate**. A cantilever with a free end is always determinate regardless of how it is loaded.
