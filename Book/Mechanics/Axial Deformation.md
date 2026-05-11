---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Axial deformation** ($\delta$) is the change in length of a prismatic member under an axial load, given by $\delta = \frac{FL_0}{AE}$, where $F$ is the [[internal force]], $L_0$ is the original length, $A$ is the [[cross-sectional area]], and $E$ is [[Young's modulus]]. A positive $\delta$ is elongation; negative is shortening.

Notes:
- This formula combines $\sigma = F/A$, $\varepsilon = \delta/L_0$, and $\sigma = E\varepsilon$ into a single expression. It assumes the member is **prismatic** (constant $A$ and $E$ along its length) and the load is purely axial.
- For a member made of segments with different areas, materials, or internal forces: 
	- compute $\delta_i = F_i L_i / A_i E_i$ for each segment 
	- then compute the sum: $\delta_{total} = \sum_i \delta_i$.
- Deformation is a geometry-dependent quantity; [[strain]] is the geometry-independent version. Two rods of the same material under the same stress will deform differently if they have different lengths.
- Do not confuse deformation with displacement. A rigid link can translate without deforming; $\delta = 0$ unless the member actually changes length.

## Equations

> [!equation] Axial Deformation
> $$\delta = \frac{F L_0}{A E}$$
>
> - $\delta$ — change in length (m)
> - $F$ — internal axial force (N)
> - $L_0$ — original length (m)
> - $A$ — cross-sectional area (m²)
> - $E$ — [[Young's Modulus]] (Pa)

> [!equation] Multi-Segment Deformation
> $$\delta_{\text{total}} = \sum_i \frac{F_i L_i}{A_i E_i}$$
>
> - $\delta_{\text{total}}$ — total deformation of the assembly (m)
> - $F_i,\ L_i,\ A_i,\ E_i$ — axial force, length, area, and Young's modulus of segment $i$

## Examples and Non-Examples

- **Single member.** A 600 mm steel rod ($E = 200\ \text{GPa}$, $d = 20\ \text{mm}$) carries a tensile load $F = 25\ \text{kN}$.
$$A = \frac{\pi (0.020)^2}{4} \approx 3.14 \times 10^{-4}\ \text{m}^2$$
$$\delta = \frac{FL_0}{AE} = \frac{25{,}000 \times 0.600}{3.14 \times 10^{-4} \times 200 \times 10^9} \approx 2.39 \times 10^{-4}\ \text{m} = 0.24\ \text{mm}$$

- **Two-segment bar.** A bar consists of a 300 mm steel segment ($A_1 = 4.0 \times 10^{-4}\ \text{m}^2$, $E_1 = 200\ \text{GPa}$, $F_1 = 40\ \text{kN}$ tension) connected to a 200 mm aluminum segment ($A_2 = 6.0 \times 10^{-4}\ \text{m}^2$, $E_2 = 69\ \text{GPa}$, $F_2 = 40\ \text{kN}$ tension).
$$\delta_1 = \frac{40{,}000 \times 0.300}{4.0 \times 10^{-4} \times 200 \times 10^9} = 1.50 \times 10^{-4}\ \text{m}$$
$$\delta_2 = \frac{40{,}000 \times 0.200}{6.0 \times 10^{-4} \times 69 \times 10^9} = 1.93 \times 10^{-4}\ \text{m}$$
$$\delta_{total} = 0.150 + 0.193 = 0.343\ \text{mm}$$

- **Counter-example — thermal expansion is not axial deformation.** A steel rod heated by $\Delta T = 50\ \text{°C}$ will also elongate, but the mechanism is thermal expansion ($\delta_T = \alpha \Delta T L_0$), not an applied force. The formula $\delta = FL_0/AE$ does not apply. If the rod is constrained, the thermal expansion produces a compressive [[axial stress]] — but that is a separate calculation.

## Resources
- ![](https://www.youtube.com/watch?v=3OEFCnHT2HE)
- **[Engineering Toolbox — Stress and Deformation](https://www.engineeringtoolbox.com/stress-d_950.html)** — reference values for common geometries.

## Practice
- A 900 mm aluminum rod ($E = 69\ \text{GPa}$) must not elongate more than $0.50\ \text{mm}$ under a tensile load of $F = 30\ \text{kN}$. What is the minimum required diameter?

> [!NOTE]- Answer
> **Solve for minimum area.**
> $$A = \frac{FL_0}{\delta E} = \frac{30{,}000 \times 0.900}{0.50 \times 10^{-3} \times 69 \times 10^9} \approx 7.83 \times 10^{-4}\ \text{m}^2$$
>
> **Solve for diameter.**
> $$d = \sqrt{\frac{4A}{\pi}} = \sqrt{\frac{4 \times 7.83 \times 10^{-4}}{\pi}} \approx 0.0316\ \text{m} = 31.6\ \text{mm}$$
>
> **Minimum diameter: 31.6 mm** — round up to the next standard size in practice.
