---
tags:
  - mechanics
  - video
---
#mechanics

## Definition
> [!definition]
> **Strain** ($\varepsilon$) is the ratio of a member's change in length to its original length: $\varepsilon = \delta / L_0$, where $\delta = L - L_0$ is the [[deformation]] and $L_0$ is the original (unloaded) length. It is a dimensionless measure of how much a body has deformed relative to its size.

This page covers *normal strain* (deformation along the axis of loading). *Shear strain* ($\gamma$) describes angular distortion and is a separate concept.

Notes:
- Strain is dimensionless (m/m), but is often reported in microstrain ($\mu\varepsilon$), where $1\ \mu\varepsilon = 10^{-6}\ \text{m/m}$. 
	- Structural materials typically fail well below $10{,}000\ \mu\varepsilon$.
- The sign convention mirrors [[axial stress]]: 
	- elongation is positive (tensile strain)
	- shortening is negative (compressive strain).
- Within the elastic range, stress and strain are proportional through [[Young's modulus]]: $\sigma = E\varepsilon$ — the one-dimensional form of [[Hooke's law]] for solids.
- Strain is what [[strain gauge\|strain gauges]] actually measure — they convert surface deformation into a change in electrical resistance, and stress is then back-calculated using the material's known $E$.

## Equations

> [!equation] Normal Strain
> $$\varepsilon = \frac{\delta}{L_0}$$
>
> - $\varepsilon$ — axial strain (dimensionless, m/m; often reported in microstrain μɛ)
> - $\delta$ — change in length: $\delta = L - L_0$ (m); positive = elongation, negative = shortening
> - $L_0$ — original (unloaded) length (m)

## Examples and Non-Examples

- **Tensile test.** A steel bar with original length $L_0 = 500\ \text{mm}$ is loaded in tension and elongates by $\delta = 0.30\ \text{mm}$. 
	- Strain: $\varepsilon = 0.30 / 500 = 6 \times 10^{-4}\ \text{m/m} = 600\ \mu\varepsilon$ (tensile, positive).

- **Back-calculating stress.** For the same steel bar, $E_{\text{steel}} = 200\ \text{GPa}$. 
	- Axial stress: $\sigma = E\varepsilon = 200 \times 10^9 \times 6 \times 10^{-4} = 120\ \text{MPa}$. 
	- This matches what you'd get directly from $\sigma = F/A$ if you knew the applied force and cross-section.

- **Counter-example — rigid body motion is not strain.** If the same 500 mm bar translates 0.30 mm sideways without stretching or compressing, $\delta = 0$ along its axis. Displacement is not deformation, and displacement is not strain. Strain requires a *change in length*, not a change in position.

## Resources
- ![](https://www.youtube.com/watch?v=aQf6Q8t1FQE)
- **[Engineering Toolbox — Strain](https://www.engineeringtoolbox.com/strain-d_948.html)** — formula reference with worked unit conversions.

## Practice
- A copper rod ($E = 110\ \text{GPa}$, $L_0 = 300\ \text{mm}$) is subjected to a compressive [[axial stress]] of $55\ \text{MPa}$. How much does the rod shorten? Express your answer in mm and in microstrain.
> [!NOTE]- Answer
> **Step 1 — find strain from stress.**
> $$\varepsilon = \frac{\sigma}{E} = \frac{-55 \times 10^{6}}{110 \times 10^{9}} = -5 \times 10^{-4}\ \text{m/m} = -500\ \mu\varepsilon$$
> The negative sign confirms compression (shortening).
>
> **Step 2 — find deformation from strain.**
> $$\delta = \varepsilon \cdot L_0 = -5 \times 10^{-4} \times 300\ \text{mm} = -0.15\ \text{mm}$$
>
> **The rod shortens by 0.15 mm (500 μɛ compressive).**

