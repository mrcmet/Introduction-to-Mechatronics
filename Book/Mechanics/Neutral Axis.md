---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> The **neutral axis** is the line within a beam cross-section where [[Bending Stress]] is exactly zero. Under a pure bending moment, fibers on one side of the neutral axis are in tension and fibers on the other side are in compression — the neutral axis is the boundary between them. For a beam made of a single homogeneous material, the neutral axis passes through the **centroid** of the cross-section.

Notes:
- The neutral axis is the reference axis for the bending stress formula $\sigma = -My/I$, where $y$ is measured from the neutral axis to the fiber in question. Locating the neutral axis correctly is the first step in any bending stress calculation.
- For **symmetric sections** (rectangle, solid circle, hollow tube, I-beam about its strong axis), the neutral axis is at the geometric midpoint — no calculation needed.
- ![](https://elementaryengineeringlibrary.com/wp-content/uploads/2026/02/som-07-05-bending-stress-in-bent-beam-segment.jpg)
- For **asymmetric sections** (T-beam, L-section, unequal flanges), the centroid must be calculated explicitly: $\bar{y} = \sum (A_i \bar{y}_i) / \sum A_i$, where each $A_i$ is a sub-area and $\bar{y}_i$ is its centroidal distance from an arbitrary reference.
- For **composite beams** (two materials bonded together, e.g. steel-reinforced concrete), the neutral axis shifts toward the stiffer material. A transformed-section method is used to handle the mismatch in [[Young's Modulus]].
- The [[Second Moment of Area]] $I$ must be computed about the neutral axis. Using any other axis gives an incorrect $I$ and therefore an incorrect bending stress.

## Equations

> [!equation] Centroid Location (single material)
> $$\bar{y} = \frac{\sum A_i\, \bar{y}_i}{\sum A_i}$$
>
> - $\bar{y}$ — distance from the reference line to the neutral axis (m)
> - $A_i$ — area of each sub-region (m²)
> - $\bar{y}_i$ — distance from the reference line to the centroid of sub-region $i$ (m)

## Examples and Non-Examples

- **Rectangular cross-section.** A 60 mm × 120 mm rectangle bending about its horizontal axis. By symmetry, the neutral axis is at $\bar{y} = 60\ \text{mm}$ from either edge — exactly mid-height. Bending stress at the top and bottom fibers ($y = \pm 60\ \text{mm}$) is equal in magnitude, opposite in sign.

- **T-section — asymmetric centroid.** A T-beam has a flange (120 mm × 20 mm) on top of a web (20 mm × 80 mm). Taking $y$ measured upward from the bottom of the web:
$$\bar{y} = \frac{A_{web}\,\bar{y}_{web} + A_{flange}\,\bar{y}_{flange}}{A_{web} + A_{flange}} = \frac{(20 \times 80)(40) + (120 \times 20)(90)}{1600 + 2400} = \frac{64{,}000 + 216{,}000}{4000} = 70\ \text{mm}$$
The neutral axis is 70 mm from the bottom — much closer to the flange because the flange has more area. The top fiber ($y = +30\ \text{mm}$ above NA) and bottom fiber ($y = -70\ \text{mm}$ below NA) see very different stress magnitudes.

- **Counter-example — the neutral axis is not always at mid-height.** A student designing a T-beam assumes the neutral axis is halfway between the top and bottom of the section (at 50 mm from the bottom in the example above). This underestimates the stress in the bottom fiber by $70/50 = 40\%$ — a significant and unsafe error. For any non-symmetric section, the centroid must be calculated, not guessed.

## Resources
[Neutral Axis - Wikipedia](https://en.wikipedia.org/wiki/Neutral_axis)

