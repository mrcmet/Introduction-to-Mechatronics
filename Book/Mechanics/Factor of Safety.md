---
tags:
  - mechanics
  - materials
---
#mechanics #materials

## Definition
> [!definition]
> The **factor of safety** ($n$) is the ratio of a material's strength to the actual applied [[axial stress]]: $n = \sigma_{\text{limit}} / \sigma_{\text{applied}}$. It quantifies how much margin exists between operating conditions and the failure criterion — typically [[yield strength]] for elastic design or [[ultimate tensile strength]] for fracture-based design.

Notes:
- A factor of safety of:
	- $n = 1$ means the part is operating exactly at the failure limit — no margin whatsoever. 
	- In practice, $n$ is always greater than 1.
- Typical values depend on consequence and uncertainty:
	- $n \approx 1.25$–$1.5$ for well-characterized aerospace structures.
	- $n \approx 2$–$4$ for general mechanical components.
	- $n \geq 4$ for situations involving human safety, dynamic loads, or poorly known material properties.
- The factor of safety can equivalently be expressed as a load ratio: $n = F_{\text{failure}} / F_{\text{applied}}$. Both definitions give the same number when stress scales linearly with force.
- A larger $n$ is not always better — it means more material, more weight, and higher cost. Engineering judgment about load uncertainty, material variability, and failure consequences sets the appropriate value.
- The factor of safety is applied to one failure mode at a time. A part safe against yielding ($n_y > 2$) may still need to be checked against fatigue, buckling, or fracture — each requires its own $n$.

## Equations

> [!equation] Factor of Safety
> $$n = \frac{\sigma_{\text{limit}}}{\sigma_{\text{applied}}}$$
>
> - $n$ — factor of safety (dimensionless; must be $> 1$)
> - $\sigma_{\text{limit}}$ — material strength limit: [[Yield Strength]] $\sigma_y$ for elastic design, [[Ultimate Tensile Strength]] $\sigma_u$ for fracture-based design (Pa)
> - $\sigma_{\text{applied}}$ — actual stress in service (Pa)

## Examples and Non-Examples
- **Checking a tension rod.** A steel rod ($\sigma_y = 250\ \text{MPa}$, $d = 20\ \text{mm}$) carries $F = 60\ \text{kN}$.
	  - Stress: $\sigma = F/A = 60{,}000\ /\ (\pi \times 0.010^2) \approx 191\ \text{MPa}$
	  - Factor of safety against yield: $n = 250\ /\ 191 \approx 1.31$
	  - Whether 1.31 is acceptable depends on the application — for a static, well-characterized load it may be fine; for a dynamic or safety-critical application it is likely too low.

- **Back-calculating required cross-section.** A required $n = 2$ against yield for the same steel ($\sigma_y = 250\ \text{MPa}$) carrying $F = 60\ \text{kN}$.
	- The allowable stress is $\sigma_{\text{allow}} = 250/2 = 125\ \text{MPa}$. 
	- Required area: $A = F / \sigma_{\text{allow}} = 60{,}000 / 125{,}000{,}000 = 4.80 \times 10^{-4}\ \text{m}^2$
	- Giving a minimum diameter of $d = \sqrt{4A/\pi} \approx 24.7\ \text{mm}$.

- **Counter-example — a high factor of safety does not mean safe against all failure modes.** A shaft designed with $n = 4$ against static yielding can still fail in fatigue if subjected to cyclic loading, because fatigue failure occurs at stresses well below $\sigma_y$. Factor of safety must be matched to the correct failure mode.

## Resources
- ![](https://www.youtube.com/watch?v=WIJdXMHnMvg)
- **[Engineering Toolbox — Factor of Safety](https://www.engineeringtoolbox.com/factors-safety-fos-d_1624.html)** — typical $n$ values by application and industry.

## Practice
- An aluminum bracket ($\sigma_y = 276\ \text{MPa}$) is loaded to $\sigma = 138\ \text{MPa}$ in service. What is the factor of safety against yielding? If the load doubles unexpectedly, does the part yield?

> [!NOTE]- Answer
> $n = 276 / 138 = 2.0$  
> If the load doubles, $\sigma = 276\ \text{MPa} = \sigma_y$ — the part is exactly at the yield limit. In practice, this means it would yield, since real loads and material properties both have variability.
