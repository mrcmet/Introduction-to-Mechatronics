---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> The **second moment of area** ($I$), also called the area moment of inertia, is a geometric property of a cross-section that measures its resistance to bending. It is defined as $I = \int y^2\, dA$, where $y$ is the perpendicular distance from each area element $dA$ to the bending axis. A larger $I$ means a stiffer, stronger beam for the same material and load.

Notes:
- $I$ has units of m⁴ (or mm⁴ in practice). It depends entirely on the shape and orientation of the cross-section — not on the material.
- $I$ is always computed about a specific axis. For [[Bending Stress]], that axis is the [[Neutral Axis]] — the centroidal axis perpendicular to the applied moment. Using the wrong axis gives the wrong answer.
- The **parallel axis theorem** transfers $I$ from a centroidal axis to any parallel axis at distance $d$: $I = I_c + Ad^2$. This is essential for composite sections (e.g. T-beams, I-beams) where each sub-region's centroid is offset from the overall centroid.
- The **polar moment of area** $J$ (used in [[Torsional Shear Stress]]) is the sum of the two planar second moments: $J = I_x + I_y$. For a circular cross-section where $I_x = I_y$, this gives $J = 2I$, which is why the solid circle formulas for $I$ and $J$ differ by a factor of 2.
- Orientation matters: a rectangular beam is much stiffer bent about its strong axis ($I = bh^3/12$, $h$ = tall dimension) than its weak axis ($I = hb^3/12$, $b$ = wide dimension). This is why I-beams are oriented with the web vertical.

## Equations

> [!equation] Second Moment of Area — Rectangle (centroidal axis)
> $$I = \frac{b h^3}{12}$$
>
> - $b$ — width of the rectangle (m)
> - $h$ — height of the rectangle, measured parallel to the bending direction (m)
> - This is about the horizontal centroidal axis. For bending that deflects the beam vertically, $h$ is the full depth.

> [!equation] Second Moment of Area — Rectangle (base axis)
> $$I = \frac{b h^3}{3}$$
>
> - Same rectangle, axis at the bottom edge rather than the centroid
> - Equivalent to applying the parallel axis theorem: $I_{base} = I_c + A(h/2)^2 = \frac{bh^3}{12} + bh \cdot \frac{h^2}{4} = \frac{bh^3}{3}$

> [!equation] Second Moment of Area — Solid Circle
> $$I = \frac{\pi d^4}{64} = \frac{\pi r^4}{4}$$
>
> - $d$ — diameter (m); $r$ — radius (m)
> - Same value about any diameter axis (the section is axisymmetric)
> - Note: the polar moment is $J = 2I = \dfrac{\pi d^4}{32}$

> [!equation] Second Moment of Area — Hollow Circle
> $$I = \frac{\pi (d_o^4 - d_i^4)}{64} = \frac{\pi (r_o^4 - r_i^4)}{4}$$
>
> - $d_o,\ r_o$ — outer diameter and radius (m)
> - $d_i,\ r_i$ — inner diameter and radius (m)
> - Polar moment: $J = 2I = \dfrac{\pi(d_o^4 - d_i^4)}{32}$

> [!equation] Parallel Axis Theorem
> $$I = I_c + A d^2$$
>
> - $I_c$ — second moment of area about the shape's own centroidal axis (m⁴)
> - $A$ — cross-sectional area of the shape (m²)
> - $d$ — perpendicular distance between the centroidal axis and the new axis (m)

## Examples and Non-Examples

- **Rectangular beam, strong vs. weak axis.** A timber beam is 50 mm wide and 200 mm tall.
$$I_{strong} = \frac{0.050 \times 0.200^3}{12} = \frac{0.050 \times 0.008}{12} \approx 3.33 \times 10^{-5}\ \text{m}^4$$
$$I_{weak} = \frac{0.200 \times 0.050^3}{12} = \frac{0.200 \times 0.000125}{12} \approx 5.21 \times 10^{-8}\ \text{m}^4$$
The beam is $3.33 \times 10^{-5} / 5.21 \times 10^{-8} \approx 640$ times stiffer in bending about the strong axis — orienting the beam correctly is one of the highest-leverage decisions in structural design.

- **Composite T-section using parallel axis theorem.** A T-section has a flange (100 mm × 20 mm) on top of a web (20 mm × 80 mm). The overall centroid is found first, then each rectangle's $I_c + Ad^2$ is summed. This is the standard method for I-beams and any non-symmetric built-up section.

- **Hollow tube vs. solid rod.** A hollow steel tube ($d_o = 60\ \text{mm}$, $d_i = 50\ \text{mm}$) and a solid rod ($d = 60\ \text{mm}$) have the same outer diameter.
$$I_{hollow} = \frac{\pi (0.060^4 - 0.050^4)}{64} \approx 3.30 \times 10^{-7}\ \text{m}^4$$
$$I_{solid} = \frac{\pi (0.060)^4}{64} \approx 6.36 \times 10^{-7}\ \text{m}^4$$
The hollow tube has about half the $I$ of the solid rod but uses far less material — the removed core contributes little to bending resistance since it sits near the neutral axis.

- **Counter-example — $I$ is not the polar moment $J$.** A student computing torsional shear stress uses $\tau = Tc/I$ instead of $\tau = Tc/J$. For a solid circular shaft, $J = 2I$, so the error gives a shear stress twice the correct value. Always use $I$ for bending and $J$ for torsion — they are both "moments of area" but about different axes.

## Resources
- ![](https://youtu.be/Bls5KnQOWkY?si=bGb7V3lswIsE9H-B)
- **[Structural Basics — Polar Moment of Inertia Formulas](https://www.structuralbasics.com/polar-moment-of-inertia-formulas/)** — tabulated $I$ and $J$ values for common cross-sections including channels, angles, and I-beams.

## Practice
- A solid circular steel shaft has diameter $d = 50\ \text{mm}$. (a) What is $I$? (b) What is the polar moment $J$? (c) If the same amount of material is formed into a hollow tube with $d_o = 60\ \text{mm}$, what is the new $I$?

> [!NOTE]- Answer
> **(a) Solid shaft $I$:**
> $$I = \frac{\pi (0.050)^4}{64} \approx 3.07 \times 10^{-7}\ \text{m}^4$$
>
> **(b) Polar moment $J = 2I$:**
> $$J = 2 \times 3.07 \times 10^{-7} = 6.14 \times 10^{-7}\ \text{m}^4$$
>
> **(c) Same area, hollow tube.** Area of solid: $A = \pi(0.025)^2 \approx 1.963 \times 10^{-3}\ \text{m}^2$. With $d_o = 60\ \text{mm}$:
> $$A = \frac{\pi}{4}(d_o^2 - d_i^2) \implies d_i = \sqrt{d_o^2 - \frac{4A}{\pi}} = \sqrt{0.060^2 - \frac{4 \times 1.963 \times 10^{-3}}{\pi}} \approx 0.0436\ \text{m}$$
> $$I_{hollow} = \frac{\pi(0.060^4 - 0.0436^4)}{64} \approx 4.57 \times 10^{-7}\ \text{m}^4$$
> The hollow tube has ~49% more bending stiffness from the same mass of material.
