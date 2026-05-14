---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Beam end conditions** describe how each end of a beam is supported by specifying which **degrees of freedom** (DOF) are constrained and which are free. Each constrained DOF produces one reaction (a force or a moment); free DOFs produce none. The three fundamental 2D support types are the **pin**, the **roller**, and the **fixed** (encastre) support.

Notes:
- A rigid body in 2D has **3 DOF**: translation in $x$, translation in $y$, and rotation $\theta$. A rigid body in 3D has **6 DOF**: translations in $x$, $y$, $z$ and rotations $\theta_x$, $\theta_y$, $\theta_z$.
- The number of unknown [[Support Reactions]] equals the number of constrained DOF. Statics provides 3 equilibrium equations in 2D (6 in 3D), so a structure is **statically determinate** when reactions = equations, and **statically indeterminate** when reactions exceed equations.
- End conditions also set the boundary conditions for beam deflection: a pin or roller forces deflection to zero; a fixed end forces both deflection and slope to zero.

### 2D support types

| Support | DOF constrained | DOF free | Reactions |
|---------|----------------|----------|-----------|
| Free end | 0 | $x,\ y,\ \theta$ | none |
| Roller | 1 ($y$) | $x,\ \theta$ | $R_y$ |
| Pin | 2 ($x,\ y$) | $\theta$ | $R_x,\ R_y$ |
| Fixed | 3 ($x,\ y,\ \theta$) | none | $R_x,\ R_y,\ M$ |

### 3D support types

In 3D problems (frames, shafts, space structures), the same DOF logic applies across all six degrees of freedom.

| Support | DOF constrained | DOF free | Reactions |
|---------|----------------|----------|-----------|
| Roller on surface | 1 (normal to surface) | 5 | $R_n$ |
| Ball-and-socket joint | 3 ($x,\ y,\ z$) | $\theta_x,\ \theta_y,\ \theta_z$ | $R_x,\ R_y,\ R_z$ |
| Journal bearing (short) | 2 ($y,\ z$) | $x,\ \theta_x,\ \theta_y,\ \theta_z$ | $R_y,\ R_z$ |
| Journal bearing (long) | 4 ($y,\ z,\ \theta_y,\ \theta_z$) | $x,\ \theta_x$ | $R_y,\ R_z,\ M_y,\ M_z$ |
| Fixed wall | 6 (all) | none | $R_x,\ R_y,\ R_z,\ M_x,\ M_y,\ M_z$ |

- A **short journal bearing** (or a single ball bearing) constrains translation perpendicular to the shaft axis but cannot resist bending moments — modeled as a 3D roller. A **long bearing** or a closely spaced bearing pair also resists bending, adding two moment reactions.
- A **ball-and-socket joint** is the 3D analogue of a 2D pin: all translations constrained, all rotations free. Common in linkages and robotic joints.
- Shaft problems in mechatronics almost always involve journal bearings — knowing whether to model them as short (2 reactions) or long (4 reactions) is the first design decision.

## Examples and Non-Examples

- **Simply supported beam (pin–roller, 2D).** The pin constrains $x$ and $y$ (2 reactions); the roller constrains $y$ only (1 reaction). Total: 3 unknowns, 3 equations — statically determinate. Rotation is free at both ends, so the [[Bending Moment Diagram]] is zero at both supports.

- **Cantilever beam (fixed–free, 2D).** The fixed wall constrains all 3 DOF: $R_x$, $R_y$, and $M_{wall}$. Total: 3 unknowns, 3 equations — still determinate. The free end has zero reactions but can deflect and rotate.

- **Fixed–fixed beam (2D).** Each fixed end contributes 3 constrained DOF → 6 unknowns total, but only 3 equilibrium equations. Statically indeterminate to the **third degree** — compatibility equations from beam deflection are required to solve.

- **Motor shaft on two short bearings (3D).** Each short journal bearing constrains $R_y$ and $R_z$ — 2 reactions each, 4 total. The shaft is free to rotate about its own axis ($\theta_x$) and translate axially ($x$). Adding a thrust bearing at one end constrains $R_x$ as well, fixing axial position without over-constraining rotation.

- **Counter-example — a free end is not a support.** A free end imposes zero constraints and provides zero reactions. Treating a free end as providing any reaction is a common error when drawing [[Free Body Diagram]]s.

## Resources
 
 ![](https://youtu.be/Jy2lUzGO4Gg?si=EzidWeIs0db7KcQn)

![](https://youtu.be/Zrc_gB1YYS0?si=60gzUaVOyW9zXK21)

**[Perdue — Beams, Supported at Both Ends](https://www.purdue.edu/freeform/me323/animations-and-demonstrations/beams-deflections-and-boundary-conditions/?TSPD_101_R0=08993c5290ab2000ceb1dab86724812721617bb9bc3a11215ad4895cc34c4a677ce51a824035e428087c0daed81430003f94e43578c4074ceb91d43ff18b1de668aad3e4e43462e9b3e003fee25337cb5d24ceb4b2a7594b250db0473c65471c)** — reaction and deflection of common configurations.

**[MechaniCalc — Beams, Supported at Both Ends](https://mechanicalc.com/reference/beam-analysis)** — reaction and deflection of common configurations.

## Practice
- A motor shaft is supported by two short journal bearings, one at each end, and carries a transverse load at its midpoint. (a) How many unknown reactions are there? (b) Is the system statically determinate in 3D?

> [!NOTE]- Answer
> (a) Each short journal bearing constrains 2 DOF ($R_y$, $R_z$) — two bearings gives **4 unknown reactions** total.
> (b) In 3D, statics provides 6 equilibrium equations, but 2 of them ($\sum F_x = 0$ and both moment equations about the shaft axis) are trivially satisfied with no unknowns. The 4 transverse reactions are solved by the remaining 4 relevant equations ($\sum F_y = 0$, $\sum F_z = 0$, $\sum M_y = 0$, $\sum M_z = 0$) — **statically determinate**.
