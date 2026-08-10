---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Internal forces in beams** are the axial force ($N$), shear force ($V$), and bending moment ($M$) that act at any cross-section of a loaded beam. They are found by making an imaginary cut at the section of interest, isolating one segment as a [[Free Body Diagram]], and applying equilibrium.

Notes:
- The cut-and-isolate method is the fundamental technique: after cutting, the internal forces and moment on the exposed face are whatever values are needed to keep the isolated segment in equilibrium ($\sum F = 0$, $\sum M = 0$).
- Sign convention (standard): $V$ is positive when the left segment tends to rotate clockwise; $M$ is positive when it causes the beam to sag (concave up). Stick to one convention per problem.
- In most beam problems the axial force $N = 0$ because loads are transverse. When $N \neq 0$ (inclined loads, frames), the cross-section carries both [[Axial Stress]] and [[Bending Stress]] simultaneously.
- $V$ and $M$ both vary along the beam length — their distributions are captured in the [[Shear Force Diagram]] and [[Bending Moment Diagram]].

## Examples and Non-Examples

- **Simply supported beam with mid-span point load.** A beam of length $L = 4\ \text{m}$ carries $P = 20\ \text{kN}$ at mid-span. [[Support Reactions]] are $A_y = B_y = 10\ \text{kN}$. Cut at $x = 1\ \text{m}$ from the left, isolate the left segment:
$$\sum F_y = 0: \quad A_y - V = 0 \implies V = +10\ \text{kN}$$
$$\sum M_{cut} = 0: \quad -A_y(1) + M = 0 \implies M = +10\ \text{kN·m}$$
The section carries 10 kN of shear and 10 kN·m of sagging moment.

- **Cut between load and support.** For the same beam, cut at $x = 3\ \text{m}$ (right of the point load). Isolate the left segment, which now includes the 20 kN applied force:
$$\sum F_y = 0: \quad 10 - 20 - V = 0 \implies V = -10\ \text{kN}$$
$$\sum M_{cut} = 0: \quad -10(3) + 20(1) + M = 0 \implies M = +10\ \text{kN·m}$$
Shear changed sign at the load; moment is still sagging.

- **Counter-example — support reactions are not internal forces.** The reaction forces at a pin or roller are *external* forces that appear on the [[Free Body Diagram]] of the whole beam. Internal forces only appear when you *cut* the beam and expose the cross-section — they are invisible until then.

## Resources

![](https://youtu.be/wzFPnf6Yzdg?si=fRk-QYrjteuiupgp)

 ![](https://youtu.be/DC-6c7whuUk?si=OuWU2m3xxFMmEXW7)
 
 ![](https://youtu.be/C-FEVzI8oe8?si=wAxoTxKwduDxDyaQ_)

## Practice
- A cantilever beam of length $L = 3\ \text{m}$ is fixed at the left end and carries a downward point load $P = 15\ \text{kN}$ at the free (right) end. Find the shear force and bending moment at $x = 1\ \text{m}$ from the fixed end.

> [!NOTE]- Answer
> Cut at $x = 1\ \text{m}$ and isolate the *right* segment (length 2 m, carrying the 15 kN load at its free end).
> $$\sum F_y = 0: \quad V - 15 = 0 \implies V = +15\ \text{kN}$$
> $$\sum M_{cut} = 0: \quad -M + 15(2) = 0 \implies M = +30\ \text{kN·m}$$
> The section carries 15 kN shear and 30 kN·m of moment (hogging at this location in the cantilever).
