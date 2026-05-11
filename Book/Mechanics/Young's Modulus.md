---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Young's modulus** ($E$) is the ratio of [[axial stress]] to [[strain]] in the linear elastic region of a material's behavior: $E = \sigma / \varepsilon$. It is a material property — not a geometric one — with units of pascals (Pa) or gigapascals (GPa), and it quantifies how stiff a material is.

Notes:
- Rearranged, this gives the one-dimensional form of [[Hooke's law]] for solids: $\sigma = E\varepsilon$. Double the strain requires double the stress — but only while the material remains elastic.
- $E$ is a property of the material, not the part. A thick steel rod and a thin steel wire have the same $E = 200\ \text{GPa}$; their different stiffnesses come from geometry (cross-section and length), not from $E$ itself.
- Valid only in the **elastic region** — below the [[yield strength]]. Once a metal yields, the stress–strain relationship is no longer linear and $E$ no longer applies.
- Combining $E = \sigma/\varepsilon$ with $\sigma = F/A$ and $\varepsilon = \delta/L_0$ gives the axial deformation formula: $\delta = \frac{FL_0}{AE}$. This is the most-used form in practice.
- Lateral strains accompany axial strain and are governed by [[Poisson's ratio]] $\nu$.

## Examples and Non-Examples

- **Deformation under load.** A 500 mm aluminum rod ($E = 69\ \text{GPa}$, $A = 2.0 \times 10^{-4}\ \text{m}^2$) is pulled with $F = 18\ \text{kN}$.
$$\delta = \frac{FL_0}{AE} = \frac{18{,}000 \times 0.500}{2.0 \times 10^{-4} \times 69 \times 10^9} \approx 6.5 \times 10^{-4}\ \text{m} = 0.65\ \text{mm}$$
Replace the aluminum with steel ($E = 200\ \text{GPa}$) and the deformation drops to $0.22\ \text{mm}$ — steel is ~2.9× stiffer under the same geometry and load.

- **Back-calculating $E$ from a test.** A tensile test records $\sigma = 140\ \text{MPa}$ and $\varepsilon = 0.002\ \text{m/m}$ in the elastic region. Young's modulus: $E = \sigma/\varepsilon = 140 \times 10^6 / 0.002 = 70\ \text{GPa}$ — consistent with aluminum.

- **Counter-example — geometry is not stiffness.** A rubber pad ($E \approx 0.01\ \text{GPa}$) cut very thick can resist more total force than a thin steel sheet before reaching the same stress. Total force capacity depends on both $E$ and geometry. Young's modulus alone does not tell you how much load a part can carry — that also requires the cross-section and length.

## Resources
- ![](https://www.youtube.com/watch?v=DLE-ieOVFjI)
- <iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/mechanics/youngs-modulus-materials.html" width="100%" height="500" style="border: none; border-radius: 8px;" loading="lazy" title="Young's modulus material comparison — interactive bar chart"></iframe>
- **[Engineering Toolbox — Young's Modulus](https://www.engineeringtoolbox.com/young-modulus-d_417.html)** — extended material table with temperature dependence notes.

## Practice
- An engineer needs to limit the deflection of a 300 mm support rod under a $10\ \text{kN}$ tensile load to no more than $0.10\ \text{mm}$. The rod has a circular cross-section with $d = 12\ \text{mm}$. What minimum Young's modulus does the material need? Which of the materials in the chart above would qualify?

> [!NOTE]- Answer
> **Step 1 — find the cross-sectional area.**
> $$A = \frac{\pi d^2}{4} = \frac{\pi (0.012)^2}{4} \approx 1.131 \times 10^{-4}\ \text{m}^2$$
>
> **Step 2 — solve for minimum $E$.**
> $$\delta = \frac{FL_0}{AE} \implies E = \frac{FL_0}{A\delta} = \frac{10{,}000 \times 0.300}{1.131 \times 10^{-4} \times 0.100 \times 10^{-3}} \approx 265\ \text{GPa}$$
>
> **No common metal meets this requirement at this geometry.** Steel ($E = 200\ \text{GPa}$) falls short. The engineer must either increase the rod diameter, shorten it, or accept a larger deflection. This is a design trade-off between material selection and geometry.
