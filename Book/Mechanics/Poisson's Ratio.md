---
tags:
  - mechanics
  - "#materials"
---
#mechanics #materials 

## Definition
> [!definition]
> **Poisson's ratio** ($\nu$) is the negative ratio of lateral [[Strain]] to axial [[Strain]] under a uniaxial load: $\nu = -\varepsilon_{lateral} / \varepsilon_{axial}$. It is a dimensionless material constant that quantifies how much a material contracts (or expands) sideways when stretched lengthwise.

Notes:
- For most engineering metals, $\nu$ falls between 0.25 and 0.35 (steel ≈ 0.30, aluminum ≈ 0.33). Rubber approaches 0.50, meaning it is nearly incompressible — volume barely changes under load.
- The negative sign in the definition makes $\nu$ positive for conventional materials: when $\varepsilon_{axial} > 0$ (elongation), $\varepsilon_{lateral} < 0$ (contraction), so the ratio is positive.
- Poisson's ratio links [[Young's Modulus]] ($E$) and [[Shear Modulus]] ($G$) through the relation $G = E / \left[2(1+\nu)\right]$. Knowing any two of these three constants gives you the third.
- In multi-axial stress states (not covered on this page), Poisson's ratio appears in the generalized Hooke's Law — lateral stresses contribute to axial strain and vice versa.

## Equations

> [!equation] Poisson's Ratio
> $$\nu = -\frac{\varepsilon_{\text{lateral}}}{\varepsilon_{\text{axial}}}$$
>
> - $\nu$ — Poisson's ratio (dimensionless; typically 0.25–0.35 for metals)
> - $\varepsilon_{\text{lateral}}$ — [[Strain]] perpendicular to the load axis (m/m)
> - $\varepsilon_{\text{axial}}$ — [[Strain]] along the load axis (m/m)

> [!equation] Shear Modulus from $E$ and $\nu$
> $$G = \frac{E}{2(1 + \nu)}$$
>
> - $G$ — shear modulus (Pa)
> - $E$ — [[Young's Modulus]] (Pa)
> - $\nu$ — Poisson's ratio (dimensionless)

## Examples and Non-Examples

- **Steel rod under tension.** A steel rod ($\nu = 0.30$, original diameter $d = 20\ \text{mm}$) is subjected to an axial strain of $\varepsilon_{axial} = +0.001$ (0.1% elongation).
$$\varepsilon_{lateral} = -\nu \cdot \varepsilon_{axial} = -0.30 \times 0.001 = -0.0003$$
The diameter decreases by $\Delta d = \varepsilon_{lateral} \times d = -0.0003 \times 20 = -0.006\ \text{mm}$ — barely measurable, but real.

- **Rubber seal.** A rubber gasket ($\nu \approx 0.49$) compressed axially bulges significantly outward. The high Poisson's ratio means nearly all the volume "squeezes out" laterally, which is why gaskets seal.

- **Counter-example — thermal expansion is not a Poisson effect.** When a rod is heated uniformly, it expands in all directions equally. That is isotropic thermal expansion, governed by the coefficient of thermal expansion — not Poisson's ratio, which only applies when there is a *mechanical* load causing differential axial vs. lateral strain.

## Resources
- ![](https://youtu.be/tuOlM3P7ygA?si=RHLsTPgu3CgBJYZf)
- **[Matweb - Material Search](https://www.matweb.com/search/PropertySearch.aspx)** — Use MATWEBs search feature to find values for common materials.

## Practice
- An aluminum bar ($\nu = 0.33$, square cross-section $30\ \text{mm} \times 30\ \text{mm}$) is loaded in tension with $\varepsilon_{axial} = +0.0015$. What is the new side length of the cross-section?

> [!NOTE]- Answer
> $$\varepsilon_{lateral} = -0.33 \times 0.0015 = -0.000495$$
> $$\Delta s = \varepsilon_{lateral} \times s_0 = -0.000495 \times 30 = -0.01485\ \text{mm}$$
> New side length: $30 - 0.01485 \approx 29.985\ \text{mm}$
