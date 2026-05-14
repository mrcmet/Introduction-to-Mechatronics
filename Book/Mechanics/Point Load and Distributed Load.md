---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> A **point load** (or concentrated load) is a force applied at a single location on a beam, idealized as acting at a point. A **distributed load** is a force spread continuously over a length of beam, described by an intensity $w$ in units of force per length (N/m or kN/m). For equilibrium purposes, a distributed load can always be replaced by a single resultant force equal to the area under the load diagram, acting at its centroid.

Notes:
- A **uniform distributed load** (UDL) has constant intensity $w$. Its resultant is $F_R = wL$, acting at the midpoint of the loaded length.
- A **triangular distributed load** has intensity that varies linearly from zero to $w_{max}$. Its resultant is $F_R = \frac{1}{2}w_{max}L$, acting at $\frac{2}{3}$ of the length from the zero end (the centroid of a triangle).
- The resultant replacement is valid **only** for computing [[Support Reactions]] and checking global equilibrium. When constructing the [[Shear Force Diagram]] and [[Bending Moment Diagram]], the distributed load must be kept as a distributed load — replacing it with a point load gives the wrong diagram shape.
- Real loads are never truly "point" loads — the point load is a model that works well when the contact area is small compared to the beam length.

## Equations

> [!equation] Uniform Distributed Load — Resultant
> $$F_R = w L$$
>
> - $F_R$ — resultant force, acting at the midpoint of the loaded length (N)
> - $w$ — load intensity, constant (N/m)
> - $L$ — length over which the load is applied (m)

> [!equation] Triangular Distributed Load — Resultant
> $$F_R = \frac{1}{2} w_{\text{max}} L$$
>
> - $F_R$ — resultant force, acting at $\tfrac{2}{3}L$ from the zero end (N)
> - $w_{\text{max}}$ — peak load intensity (N/m)
> - $L$ — loaded length (m)

## Examples and Non-Examples

- **UDL on a simply supported beam.** A 6 m beam carries a UDL of $w = 5\ \text{kN/m}$ over its full length. The resultant is $F_R = 5 \times 6 = 30\ \text{kN}$, acting at mid-span. By symmetry, each [[Support Reactions|support reaction]] is $30/2 = 15\ \text{kN}$ upward.

- **Triangular load.** A 4 m beam has a triangular distributed load that starts at 0 kN/m at the left end and ramps to $w_{max} = 12\ \text{kN/m}$ at the right end. The resultant is $F_R = \frac{1}{2}(12)(4) = 24\ \text{kN}$, acting at $\frac{2}{3}(4) = 2.67\ \text{m}$ from the left (zero) end.

- **Counter-example — using the resultant on a shear diagram.** A student replaces a UDL of $w = 4\ \text{kN/m}$ over a 3 m span with a single 12 kN point load at mid-span before drawing the shear diagram. The resulting diagram shows a step at mid-span rather than the correct linearly varying shear. The resultant shortcut is for reactions only; keep the distributed load in place for diagram construction.

## Resources

![[Point Vs Distributed loads.svg]]

![](https://youtu.be/MvBqCeZllpQ?si=ONsm2MIskjxo9RoZ)

## Practice
- A 5 m simply supported beam carries a UDL of $w = 6\ \text{kN/m}$ over the left 3 m only. Find the resultant of the distributed load and its location, then compute the support reactions.

> [!NOTE]- Answer
> **Resultant:** $F_R = 6 \times 3 = 18\ \text{kN}$, acting at $1.5\ \text{m}$ from the left end.
>
> **Reactions** (taking moments about A at left):
> $$\sum M_A = 0: \quad -18(1.5) + B_y(5) = 0 \implies B_y = \frac{27}{5} = 5.4\ \text{kN}$$
> $$\sum F_y = 0: \quad A_y + 5.4 - 18 = 0 \implies A_y = 12.6\ \text{kN}$$
