---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Shear stress** ($\tau$) is the [[internal force]] per unit [[cross-sectional area]] that acts *parallel* to the face it acts on: $\tau = V / A$. It is the complement of [[Normal Stress]], which acts perpendicular to the same face.

Notes:
- Units are pascals (Pa) or megapascals (MPa), identical to [[Axial Stress]].
- The formula $\tau = V/A$ gives the *average* shear stress across the section and assumes stress is uniformly distributed — a useful first approximation for bolts, pins, and rivets. The distribution is rarely uniform in practice; see [[Transverse Shear Stress in Beams]] for the parabolic profile in beam cross-sections.
- Shear stress drives shear *strain* ($\gamma$), related through the [[Shear Modulus]]: $\tau = G \gamma$. This is the shear analogue of [[Hooke's Law]].
- Shear stress appears in three important contexts: direct shear (pins, bolts), transverse shear in beams ([[Transverse Shear Stress in Beams]]), and torsion ([[Torsional Shear Stress]]). Each has its own formula, but the same unit and physical meaning.

## Equations

> [!equation] Average Shear Stress
> $$\tau = \frac{V}{A}$$
>
> - $\tau$ — average shear stress (Pa or MPa)
> - $V$ — shear force acting on the section (N)
> - $A$ — cross-sectional area resisting the shear (m²)
> - *Assumes uniform distribution — valid for pins, bolts, and rivets; see [[Transverse Shear Stress in Beams]] for non-uniform cases*

## Examples and Non-Examples

- **Single-shear bolt.** A steel bolt with diameter $d = 12\ \text{mm}$ connects two plates and carries a shear load $V = 9\ \text{kN}$.
$$A = \frac{\pi (0.012)^2}{4} \approx 1.13 \times 10^{-4}\ \text{m}^2$$
$$\tau_{avg} = \frac{V}{A} = \frac{9{,}000}{1.13 \times 10^{-4}} \approx 79.6\ \text{MPa}$$

- **Double-shear pin.** If the same 9 kN load is carried by a double-shear clevis pin (load shared across two cross-sections), the shear stress halves:
$$\tau_{avg} = \frac{V}{2A} = \frac{9{,}000}{2 \times 1.13 \times 10^{-4}} \approx 39.8\ \text{MPa}$$

- **Counter-example — axial stress is not shear stress.** A rod pulled along its axis develops stress *perpendicular* to its cross-section (normal stress). No face is being slid; that is [[Axial Stress]], not shear stress, even though both use the same $F/A$ form.

## Resources
- ![](https://www.youtube.com/watch?v=nBfqCVhUZbs)
- **[Engineering Toolbox — Shear Stress](https://www.engineeringtoolbox.com/shear-stress-d_649.html)** — quick reference and unit conversions.

## Practice
- A 16 mm diameter aluminum pin supports a double-shear load of $F = 24\ \text{kN}$. What is the average shear stress in the pin?

> [!NOTE]- Answer
> **Find the area of one shear plane.**
> $$A = \frac{\pi (0.016)^2}{4} \approx 2.01 \times 10^{-4}\ \text{m}^2$$
> **Divide load across two shear planes.**
> $$\tau = \frac{F}{2A} = \frac{24{,}000}{2 \times 2.01 \times 10^{-4}} \approx 59.7\ \text{MPa}$$
