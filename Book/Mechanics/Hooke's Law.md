---
tags:
  - mechanics
  - Widget
  - video
  - materials
---
#mechanics #materials

## Definition
> [!definition]
> **Hooke's law** states that within the elastic limit, [[axial stress]] is directly proportional to [[strain]]: $\sigma = E\varepsilon$, where $E$ is [[Young's modulus]]. The relationship is linear — double the strain, double the stress — and it holds only up to the **proportional limit**, the point where the stress–strain curve first deviates from a straight line.

Notes:
- Hooke's law describes the *linear elastic* region of a material's behavior. Above the proportional limit, stress and strain are no longer proportional, even if the material is still elastic (recoverable).
- Above the [[yield strength]], the material enters plastic deformation — permanent shape change that Hooke's law cannot describe at all.
- The law applies to any linear elastic system, not just axial members. Springs obey $F = kx$, which is the same principle: force proportional to displacement. The spring constant $k$ plays the same role as $E$.
- Hooke's law is the foundation of [[axial deformation]]: 
	- combining $\sigma = E\varepsilon$ with $\sigma = F/A$ and $\varepsilon = \delta/L_0$ 
	- gives $\delta = FL_0/AE$.
- Most metals (steel, aluminum, titanium) follow Hooke's law closely up to their proportional limit. Rubber and polymers are nonlinear even at small strains and generally do not obey Hooke's law.

## Equations

> [!equation] Hooke's Law (1D)
> $$\sigma = E \varepsilon$$
>
> - $\sigma$ — axial stress (Pa)
> - $E$ — [[Young's Modulus]] (Pa); the slope of the linear elastic region of the [[Stress-Strain Curve]]
> - $\varepsilon$ — axial [[Strain]] (dimensionless, m/m)
> - *Valid only below the proportional limit*

## Examples and Non-Examples

- **Stress from strain.** A strain gauge on a steel beam ($E = 200\ \text{GPa}$) reads $\varepsilon = 1{,}200\ \mu\varepsilon = 1.2 \times 10^{-3}\ \text{m/m}$. Using Hooke's law:
$$\sigma = E\varepsilon = 200 \times 10^9 \times 1.2 \times 10^{-3} = 240\ \text{MPa}$$
This is below the proportional limit for structural steel (~250 MPa), so Hooke's law is valid here.

- **Checking if Hooke's law applies.** An aluminum rod ($E = 69\ \text{GPa}$, proportional limit $\approx 200\ \text{MPa}$) is loaded to $\sigma = 310\ \text{MPa}$. Since $310\ \text{MPa} > 200\ \text{MPa}$, the material is beyond the proportional limit — Hooke's law does not apply, and the actual strain is greater than $\sigma/E$ would predict.

- **Counter-example — rubber.** A silicone rubber gasket under compression is elastic (it recovers when unloaded), but its stress–strain relationship is highly nonlinear even at small strains. Being elastic is not the same as obeying Hooke's law. Hooke's law requires *linear* elasticity.

## Resources
- ![](https://www.youtube.com/watch?v=ZaAYOuHfA8I)
- <iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/mechanics/stress-strain-curve.html" width="100%" height="560" style="border: none; border-radius: 8px;" loading="lazy" title="Interactive stress–strain curve — Hooke's law regions for Al 6061-T6"></iframe>

## Practice
- A structural steel member ($E = 200\ \text{GPa}$, proportional limit = $250\ \text{MPa}$) is measured at $\varepsilon = 900\ \mu\varepsilon$. Is Hooke's law valid? What is the axial stress?

> [!NOTE]- Answer
> **Step 1 — apply Hooke's law.**
> $$\sigma = E\varepsilon = 200 \times 10^9 \times 900 \times 10^{-6} = 180\ \text{MPa}$$
>
> **Step 2 — check validity.**
> $180\ \text{MPa} < 250\ \text{MPa}$ (proportional limit), so yes — Hooke's law is valid at this strain level.
