---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> The **polar moment of area** ($J$) is a geometric property of a cross-section that measures its resistance to torsion. It is defined as $J = \int r^2\, dA$, where $r$ is the radial distance from the centroid to each area element $dA$. A larger $J$ means less [[Torsional Shear Stress]] and less [[Angle of Twist]] for the same [[Torque]].

Notes:
- $J$ has units of m⁴, identical to the [[Second Moment of Area]] $I$. 
	- The two are related: $J = I_x + I_y$ (perpendicular axis theorem).
	- For a circular cross-section where $I_x = I_y$, this gives $J = 2I$ — which is why the circular shaft formulas for $J$ are exactly twice the corresponding $I$ formulas.
- Unlike $I$, which depends on the axis of bending, $J$ is always computed about the centroidal axis perpendicular to the cross-section (the shaft axis). For circular sections this is always the same axis regardless of orientation.
- Material near the center of a shaft contributes little to $J$ because $r$ is small. Hollow shafts exploit this: removing the low-$J$ core reduces weight with minimal loss of torsional resistance, which is why drive shafts and structural tubes are typically hollow.
- The torsion formula $\tau = Tr/J$ and the angle of twist formula $\phi = TL/(GJ)$ both require $J$ for the correct cross-section. Using $I$ instead of $J$ is a common and dangerous error — for a solid circular shaft, $J = 2I$, so the error doubles the computed shear stress.

## Equations

> [!equation] Polar Moment of Area — Solid Circular Shaft
> $$J = \frac{\pi d^4}{32} = \frac{\pi r^4}{2}$$
>
> - $d$ — shaft diameter (m); $r$ — shaft radius (m)

> [!equation] Polar Moment of Area — Hollow Circular Shaft
> $$J = \frac{\pi (d_o^4 - d_i^4)}{32} = \frac{\pi (r_o^4 - r_i^4)}{2}$$
>
> - $d_o,\ r_o$ — outer diameter and radius (m)
> - $d_i,\ r_i$ — inner diameter and radius (m)

> [!equation] Perpendicular Axis Theorem
> $$J = I_x + I_y$$
>
> - For any cross-section, $J$ equals the sum of the two planar second moments
> - For circular sections: $J = 2I$

## Examples and Non-Examples

- **Solid vs. hollow shaft comparison.** A solid shaft ($d = 40\ \text{mm}$) and a hollow shaft ($d_o = 50\ \text{mm}$, $d_i = 38\ \text{mm}$) have roughly the same cross-sectional area.
$$J_{solid} = \frac{\pi (0.040)^4}{32} = 2.51 \times 10^{-7}\ \text{m}^4$$
$$J_{hollow} = \frac{\pi (0.050^4 - 0.038^4)}{32} \approx 4.08 \times 10^{-7}\ \text{m}^4$$
The hollow shaft has 63% more torsional resistance from the same amount of material, because the area is concentrated at larger radii.

- **Relationship to $I$.** For the solid shaft above: $I = J/2 = 1.26 \times 10^{-7}\ \text{m}^4$. Using $I$ in the torsion formula instead of $J$ would overestimate shear stress by a factor of 2 — a serious error.

- **Counter-example — $J$ does not apply to non-circular sections in simple torsion.** The formula $\tau = Tr/J$ assumes a circular cross-section where shear stress is purely tangential and varies linearly with $r$. For rectangular, I-beam, or open thin-walled sections, the stress distribution is fundamentally different. Using $J = bh^3/12 + hb^3/12$ with the torsion formula on a rectangular shaft significantly underestimates peak stress.

## Resources
- ![](https://www.youtube.com/watch?v=weYH5Xm29pY)
- **[MechaniCalc — Cross Section Properties](https://mechanicalc.com/reference/cross-sections)** — $J$ and $I$ formulas for circular, hollow, and other common cross-sections.

## Practice
- A drive shaft must transmit $T = 600\ \text{N·m}$ and is limited to $\tau_{max} = 50\ \text{MPa}$. (a) What minimum solid shaft diameter is required? (b) What is $J$ for that shaft?

> [!NOTE]- Answer
> **(a) From the torsion formula** $\tau = Tc/J = T(d/2)/(\pi d^4/32) = 16T/(\pi d^3)$:
> $$d^3 = \frac{16T}{\pi \tau_{max}} = \frac{16 \times 600}{\pi \times 50 \times 10^6} = 6.11 \times 10^{-5}\ \text{m}^3$$
> $$d = (6.11 \times 10^{-5})^{1/3} \approx 0.0394\ \text{m} = 39.4\ \text{mm}$$
> Round up to the next standard size: **40 mm**.
>
> **(b) $J$ for a 40 mm shaft:**
> $$J = \frac{\pi (0.040)^4}{32} = 2.51 \times 10^{-7}\ \text{m}^4$$
