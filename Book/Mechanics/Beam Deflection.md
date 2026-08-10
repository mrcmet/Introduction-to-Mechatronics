---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Beam deflection** ($\delta$) is the transverse displacement of a point on a beam from its original unloaded position, caused by applied loads. It is governed by the moment-curvature relationship $EI\, d^2y/dx^2 = M(x)$, where $E$ is [[Young's Modulus]], $I$ is the [[Second Moment of Area]], and $M(x)$ is the bending moment at position $x$ from the [[Bending Moment Diagram]].

Notes:
- Deflection depends on load magnitude and position, beam length, [[Beam End Conditions]], cross-section geometry ($I$), and material stiffness ($E$). Changing any of these changes the deflection.
- The quantity $EI$ is called the **flexural rigidity**
	- a higher $EI$ means a stiffer beam. 
	- Doubling $I$ (e.g. by rotating a rectangular section to its strong axis) halves the deflection for the same load.
- For most practical problems, deflection is found using **formula tables** rather than integrating the differential equation directly. The [[Bending Moment Diagram]] shape determines which table entry applies.
- **Superposition** is valid for linear elastic beams: the deflection from multiple loads equals the sum of the deflections from each load acting alone. This allows complex loading cases to be built from simple tabulated cases.
- [[Beam End Conditions]] set the boundary conditions: a pin or roller fixes deflection to zero; a fixed end fixes both deflection and slope to zero.
- In mechatronics, deflection matters wherever positional accuracy is required — a bracket or shaft that deflects under load shifts the position of a sensor, gear, or actuator.

## Equations

> [!equation] Moment-Curvature (governing equation)
> $$EI\,\frac{d^2 y}{dx^2} = M(x)$$
>
> - $E$ — [[Young's Modulus]] (Pa)
> - $I$ — [[Second Moment of Area]] about the neutral axis (m⁴)
> - $y$ — transverse deflection at position $x$ (m)
> - $M(x)$ — bending moment at position $x$ (N·m)

> [!equation] Simply Supported Beam — Central Point Load
> $$\delta_{max} = \frac{PL^3}{48EI} \qquad \text{at midspan}$$
>
> - $P$ — point load (N); $L$ — span (m)

> [!equation] Simply Supported Beam — Full-Span UDL
> $$\delta_{max} = \frac{5wL^4}{384EI} \qquad \text{at midspan}$$
>
> - $w$ — distributed load intensity (N/m)

> [!equation] Cantilever — Point Load at Free End
> $$\delta_{max} = \frac{PL^3}{3EI} \qquad \text{at free end}$$

> [!equation] Cantilever — Full-Span UDL
> $$\delta_{max} = \frac{wL^4}{8EI} \qquad \text{at free end}$$

## Examples and Non-Examples

- **Comparing beam orientations.** A rectangular steel beam ($b = 50\ \text{mm}$, $h = 150\ \text{mm}$, $E = 200\ \text{GPa}$, $L = 3\ \text{m}$) carries a central point load $P = 5\ \text{kN}$. Strong axis: $I = bh^3/12 = 1.406 \times 10^{-5}\ \text{m}^4$.
$$\delta_{strong} = \frac{5{,}000 \times 3^3}{48 \times 200 \times 10^9 \times 1.406 \times 10^{-5}} \approx 1.6\ \text{mm}$$
Weak axis: $I = hb^3/12 = 1.563 \times 10^{-6}\ \text{m}^4$, giving $\delta_{weak} \approx 14.4\ \text{mm}$ — nine times more deflection just from rotating the beam 90°.

- **Superposition — two loads.** A simply supported beam of span $L$ carries a central point load $P$ and a full-span UDL $w$. By superposition:
$$\delta_{max} = \frac{PL^3}{48EI} + \frac{5wL^4}{384EI}$$
Each term comes from its own table entry; they add directly.

- **Counter-example — deflection is not stress.** A beam can deflect significantly while staying well below yield stress, or conversely, a stiff beam with a large moment can be close to yield with little deflection. Deflection is a serviceability check (will it sag noticeably or misalign a component?); [[Bending Stress]] is a strength check (will it yield?). Both are needed independently.

## Resources
- ![](https://www.youtube.com/watch?v=DdZc7kLa4iI)
- **[MechaniCalc — Beam Deflection Tables](https://mechanicalc.com/reference/beam-deflection-tables)** — comprehensive formula tables for common beam configurations and loading cases.

## Practice
- A cantilever steel bracket ($E = 200\ \text{GPa}$, $L = 400\ \text{mm}$, solid circular cross-section $d = 20\ \text{mm}$) supports a sensor weighing $P = 80\ \text{N}$ at its tip. How much does the tip deflect?

> [!NOTE]- Answer
> $$I = \frac{\pi (0.020)^4}{64} = 7.854 \times 10^{-9}\ \text{m}^4$$
> $$\delta = \frac{PL^3}{3EI} = \frac{80 \times (0.400)^3}{3 \times 200 \times 10^9 \times 7.854 \times 10^{-9}} \approx 1.37\ \text{mm}$$
> For a precision sensor mount, 1.37 mm of tip deflection under load would likely be unacceptable — this bracket needs a larger cross-section or shorter arm.
