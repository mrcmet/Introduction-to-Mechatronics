---
tags:
  - mechanics
  - video
  - Widget
  - materials
---
#mechanics #materials 

## Definition
> [!definition]
> **Young's modulus** ($E$) is the ratio of [[axial stress]] to [[strain]] in the linear elastic region of a material's behavior: $E = \sigma / \varepsilon$. It is a material property — not a geometric one — with units of pascals (Pa) or gigapascals (GPa), and it quantifies how stiff a material is.

Notes:
- Rearranged, this gives the one-dimensional form of [[Hooke's law]] for solids: $\sigma = E\varepsilon$. Double the strain requires double the stress — but only while the material remains elastic.
- $E$ is a property of the material, not the part. A thick steel rod and a thin steel wire have the same $E = 200\ \text{GPa}$; their different stiffnesses come from geometry (cross-section and length), not from $E$ itself.
- Valid only in the **elastic region** — below the [[yield strength]]. Once a metal yields, the stress–strain relationship is no longer linear and $E$ no longer applies.
- Combining $E = \sigma/\varepsilon$ with $\sigma = F/A$ and $\varepsilon = \delta/L_0$ gives the [[axial deformation]] formula: $\delta = \frac{FL_0}{AE}$. This is the most-used form in practice.
- Lateral strains accompany axial strain and are governed by [[Poisson's ratio]] $\nu$.

## Equations

> [!equation] Young's Modulus
> $$E = \frac{\sigma}{\varepsilon}$$
>
> - $E$ — Young's modulus; stiffness of the material (Pa or GPa)
> - $\sigma$ — [[Axial Stress]] in the linear elastic region (Pa)
> - $\varepsilon$ — [[Strain]] in the linear elastic region (dimensionless, m/m)
> - *Valid only below the [[Yield Strength]]*

## Examples and Non-Examples

- **Finding $E$ from a tensile test.** A test coupon records $\sigma = 140\ \text{MPa}$ and $\varepsilon = 2{,}030\ \mu\varepsilon = 0.00203\ \text{m/m}$ in the elastic region.
$$E = \frac{\sigma}{\varepsilon} = \frac{140 \times 10^6}{0.00203} \approx 69\ \text{GPa}$$
That's consistent with aluminum — the slope of the stress–strain curve in the elastic region is the material's Young's modulus.

- **Finding stress from $E$ and strain.** A steel bridge cable ($E = 200\ \text{GPa}$) is measured to be under $\varepsilon = 800\ \mu\varepsilon$ of tensile strain by a [[strain gauge]]. The [[axial stress]] is:
$$\sigma = E\varepsilon = 200 \times 10^9 \times 800 \times 10^{-6} = 160\ \text{MPa}$$
No load cell needed — strain gauge data plus a known $E$ gives stress directly.

- **Counter-example — geometry is not stiffness.** A rubber pad ($E \approx 0.01\ \text{GPa}$) cut very thick can resist more total force than a thin steel sheet before reaching the same stress. Young's modulus is a material constant; how much a part deflects under load also depends on its length and cross-section. For the full deformation calculation, see [[axial deformation]].

## Resources

![](https://www.youtube.com/watch?v=DLE-ieOVFjI)
<iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/mechanics/youngs-modulus-materials.html" width="100%" height="680" style="border: none; border-radius: 8px;" loading="lazy" title="Young's modulus material comparison — interactive bar chart"></iframe>

**[Engineering Toolbox — Young's Modulus](https://www.engineeringtoolbox.com/young-modulus-d_417.html)** — extended material table with temperature dependence notes.

## Practice
- A tensile test on an unknown alloy records $\sigma = 330\ \text{MPa}$ at $\varepsilon = 2{,}870\ \mu\varepsilon$ while still in the elastic region. What is $E$? Use the material chart above to identify the most likely material family.

> [!NOTE]- Answer
> $$E = \frac{\sigma}{\varepsilon} = \frac{330 \times 10^6}{2{,}870 \times 10^{-6}} \approx 115\ \text{GPa}$$
> That puts this material in the titanium family — consistent with Ti-6Al-4V ($E \approx 114\ \text{GPa}$). Steels cluster near 200 GPa, aluminum alloys near 69 GPa.
