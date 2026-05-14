---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Torsional shear stress** is the [[Shear Stress]] produced in a shaft by an applied [[Torque]]. It varies linearly across the cross-section — zero at the center, maximum at the outer surface — and is calculated using the torsion formula: $\tau = Tr/J$, where $T$ is the applied torque, $r$ is the radial distance from the center, and $J$ is the [[Polar Moment of Area]] of the cross-section.

Notes:
- Units are pascals (Pa) or megapascals (MPa).
- The maximum torsional shear stress always occurs at the outermost fiber. For a shaft of outer radius $c$:
$$\tau_{max} = \frac{Tc}{J}$$
- Polar moment of area $J$ for common cross-sections:

| Cross-section | $J$ |
|---|---|
| Solid circle (radius $c$, diameter $d$) | $\dfrac{\pi c^4}{2} = \dfrac{\pi d^4}{32}$ |
| Hollow circle (outer $c_o$, inner $c_i$) | $\dfrac{\pi (c_o^4 - c_i^4)}{2}$ |

- The torsion formula assumes the shaft is prismatic (constant cross-section), the material is linearly elastic and isotropic, and plane cross-sections remain plane after twisting. These are [[Saint-Venant's Principle]] conditions — results near stress concentrations or abrupt geometry changes will differ.
- The angle of twist $\phi$ over shaft length $L$ is related to $G$ and $J$:
$$\phi = \frac{TL}{GJ}$$
where $G$ is the [[Shear Modulus]]. A stiffer material or larger $J$ reduces twist for the same torque.
- Torsional shear stress is one of three shear stress types — see [[Shear Stress]] for the family overview and formula comparison.

## Examples and Non-Examples

- **Solid steel driveshaft.** A solid circular shaft has diameter $d = 30\ \text{mm}$ and carries a torque $T = 200\ \text{N·m}$. Find the maximum shear stress.
$$J = \frac{\pi (0.030)^4}{32} \approx 7.95 \times 10^{-8}\ \text{m}^4 \qquad c = 0.015\ \text{m}$$
$$\tau_{max} = \frac{Tc}{J} = \frac{200 \times 0.015}{7.95 \times 10^{-8}} \approx 37.7\ \text{MPa}$$

- **Hollow shaft — same outer diameter.** Replace the solid shaft with a hollow shaft ($c_o = 15\ \text{mm}$, $c_i = 10\ \text{mm}$), same torque $T = 200\ \text{N·m}$.
$$J = \frac{\pi (0.015^4 - 0.010^4)}{2} \approx 6.38 \times 10^{-8}\ \text{m}^4$$
$$\tau_{max} = \frac{200 \times 0.015}{6.38 \times 10^{-8}} \approx 47.0\ \text{MPa}$$
The hollow shaft has less material but a higher stress at the surface — removing the low-stress core sacrifices more capacity than intuition suggests.

- **Counter-example — transverse load is not torsion.** A beam loaded by a vertical force bends and develops an internal shear force, which creates [[Transverse Shear Stress in Beams]] — not torsional shear stress. Both involve $\tau$, but torsion produces no net transverse force, and a transverse force produces no net twist. The mechanism, formula, and cross-sectional distribution are entirely different.

## Resources
- ![](https://www.youtube.com/watch?v=1YTKedLQOa0)

## Practice
- A solid aluminum shaft ($G = 26\ \text{GPa}$) has diameter $d = 40\ \text{mm}$ and carries torque $T = 350\ \text{N·m}$. (a) What is the maximum torsional shear stress? (b) At what radial distance from the center is the shear stress exactly half the maximum?

> [!NOTE]- Answer
> **(a) Maximum shear stress at the outer surface.**
> $$J = \frac{\pi (0.040)^4}{32} = 2.51 \times 10^{-7}\ \text{m}^4 \qquad c = 0.020\ \text{m}$$
> $$\tau_{max} = \frac{Tc}{J} = \frac{350 \times 0.020}{2.51 \times 10^{-7}} \approx 27.9\ \text{MPa}$$
>
> **(b) Half maximum stress.** Since $\tau = Tr/J$ is linear in $r$, the stress is half the maximum when $r = c/2 = 10\ \text{mm}$ from the center.
