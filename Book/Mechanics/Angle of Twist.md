---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> The **angle of twist** ($\phi$) is the rotation of one cross-section of a shaft relative to another under an applied [[Torque]]. For a prismatic shaft with constant $T$, $G$, and $J$: $\phi = TL/(GJ)$, where $L$ is the shaft length, $G$ is the [[Shear Modulus]], and $J$ is the [[Polar Moment of Area]].

Notes:
- Units are radians (dimensionless), though degrees are often used for design limits and specifications.
- The angle of twist is the torsional analogue of [[Axial Deformation]] ($\delta = FL/AE$): both are deformation = (load × length) / (material stiffness × geometric stiffness). Torque replaces force, $GJ$ replaces $AE$, and $\phi$ replaces $\delta$.
- For a **multi-segment shaft** (different $T$, $G$, or $J$ in each segment), compute $\phi_i = T_i L_i / (G_i J_i)$ for each segment, then sum algebraically, respecting sign.
- Design limits for power transmission shafts are typically **0.5° to 1° per metre** of shaft length. Exceeding this causes positional errors in gears, couplings, and driven machinery — a critical consideration for precision mechatronic systems.
- A stiffer material ($G$ higher) or a larger cross-section ($J$ higher) both reduce twist. Hollow shafts are efficient: they increase $J$ with little added weight, reducing $\phi$ for the same $T$.

## Equations

> [!equation] Angle of Twist — Prismatic Shaft
> $$\phi = \frac{TL}{GJ}$$
>
> - $\phi$ — angle of twist (radians)
> - $T$ — applied [[Torque]] (N·m)
> - $L$ — shaft length (m)
> - $G$ — [[Shear Modulus]] (Pa)
> - $J$ — [[Polar Moment of Area]] (m⁴)

> [!equation] Angle of Twist — Multi-Segment Shaft
> $$\phi_{total} = \sum_i \frac{T_i L_i}{G_i J_i}$$
>
> - Each segment $i$ contributes its own $\phi_i$; sum algebraically (sign matters)

## Examples and Non-Examples

- **Steel drive shaft.** A solid steel shaft ($G = 80\ \text{GPa}$, $d = 30\ \text{mm}$, $L = 1.2\ \text{m}$) transmits $T = 200\ \text{N·m}$.
$$J = \frac{\pi (0.030)^4}{32} = 7.95 \times 10^{-8}\ \text{m}^4$$
$$\phi = \frac{200 \times 1.2}{80 \times 10^9 \times 7.95 \times 10^{-8}} = \frac{240}{6{,}360} \approx 0.0377\ \text{rad} = 2.16°$$
At 1.2 m this is $2.16°/1.2\ \text{m} = 1.8°/\text{m}$ — exceeding the 1°/m guideline for precision drives. A larger diameter or shorter span would be needed.

- **Two-segment shaft.** A shaft has a steel segment ($G_1 = 80\ \text{GPa}$, $d_1 = 40\ \text{mm}$, $L_1 = 0.5\ \text{m}$, $T_1 = 300\ \text{N·m}$) connected to an aluminum segment ($G_2 = 26\ \text{GPa}$, $d_2 = 40\ \text{mm}$, $L_2 = 0.3\ \text{m}$, $T_2 = 300\ \text{N·m}$). $J = \pi(0.040)^4/32 = 2.51 \times 10^{-7}\ \text{m}^4$ for both:
$$\phi_1 = \frac{300 \times 0.5}{80 \times 10^9 \times 2.51 \times 10^{-7}} = 7.47 \times 10^{-3}\ \text{rad}$$
$$\phi_2 = \frac{300 \times 0.3}{26 \times 10^9 \times 2.51 \times 10^{-7}} = 1.38 \times 10^{-2}\ \text{rad}$$
$$\phi_{total} = 7.47 \times 10^{-3} + 1.38 \times 10^{-2} \approx 0.0213\ \text{rad} = 1.22°$$

- **Counter-example — twist is not deflection.** A beam loaded transversely deflects vertically (governed by $EI$); a shaft carrying torque twists rotationally (governed by $GJ$). The formulae look similar but describe fundamentally different deformations — $EI$ governs bending stiffness, $GJ$ governs torsional stiffness.

## Resources
- ![](https://www.youtube.com/watch?v=cSTDwfPn020)
- **[MechRef Illinois — Torsion](https://mechref.engr.illinois.edu/sol/torsion.html)** — rigorous treatment of the torsion formula, polar moment, angle of twist, and multi-segment shafts.

## Practice
- An aluminum shaft ($G = 26\ \text{GPa}$, $d = 25\ \text{mm}$, $L = 800\ \text{mm}$) transmits $T = 80\ \text{N·m}$. (a) What is the angle of twist in degrees? (b) Does this meet the 1°/m design guideline?

> [!NOTE]- Answer
> $$J = \frac{\pi (0.025)^4}{32} = 3.84 \times 10^{-8}\ \text{m}^4$$
> **(a):**
> $$\phi = \frac{80 \times 0.800}{26 \times 10^9 \times 3.84 \times 10^{-8}} = \frac{64}{998} \approx 0.0641\ \text{rad} = 3.67°$$
>
> **(b):** $3.67° / 0.8\ \text{m} = 4.6°/\text{m}$ — well above the 1°/m guideline. This shaft needs a larger diameter or a stiffer material.
