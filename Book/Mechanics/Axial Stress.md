---
tags:
  - mechanics
  - video
---
#mechanics

## Definition
> [!definition]
> **Axial stress** ($\sigma$) is the [[internal force]] per unit [[cross-sectional area]] that acts along the longitudinal axis of a structural member: $\sigma = F / A$. When the force pulls the member apart the stress is **tensile** ($\sigma > 0$); when it squeezes the member together it is **compressive** ($\sigma < 0$).

Axial stress is a special case of [[normal stress]] — "normal" meaning perpendicular to the face it acts on. Contrast with [[shear stress]], which acts *parallel* to the face.
Axial stress and [[strain]] are related through [[Young's modulus]]: $\sigma = E \varepsilon$. This is the one-dimensional form of [[Hooke's law]] for solids.

Notes:
- Units are pascals (Pa) or megapascals (MPa). $1\ \text{MPa} = 10^6\ \text{N/m}^2$, which is convenient for most structural materials.
-  Use a [[free body diagram]] to find the internal axial force $F$ before computing $\sigma$. The sign follows from your chosen positive direction: 
	- **Tension** = member being pulled.
	- **Compression** = member being pushed.

- This formula assumes the stress is uniformly distributed across the cross-section. That assumption holds away from points of load application — formally justified by [[Saint-Venant's principle]].


## Equations

> [!equation] Axial Stress
> $$\sigma = \frac{F}{A}$$
>
> - $\sigma$ — axial stress (Pa or MPa)
> - $F$ — internal axial force; positive = tension, negative = compression (N)
> - $A$ — cross-sectional area (m²)

## Examples and Non-Examples

- **Tensile rod.** A solid steel rod with diameter $d = 25\ \text{mm}$ carries a tensile load of $F = 12\ \text{kN}$. 
	- The cross-sectional area is $A = \pi d^2 / 4 = \pi (0.025)^2 / 4 \approx 4.91 \times 10^{-4}\ \text{m}^2$.
	- Axial stress: $\sigma = F/A = 12{,}000\ /\ 4.91 \times 10^{-4} \approx +24.4\ \text{MPa}$ (tensile, positive).

- **Compressive column.** A square concrete column, $200\ \text{mm} \times 200\ \text{mm}$, supports a compressive load of $F = 500\ \text{kN}$. 
	- Area: $A = (0.200)^2 = 0.04\ \text{m}^2$. 
	- Axial stress: $\sigma = -500{,}000\ /\ 0.04 = -12.5\ \text{MPa}$ (compressive, negative).

- **Counter-example — bending is not axial stress.** A simply supported beam loaded at midspan has tensile stress in the bottom fiber and compressive stress in the top fiber. This looks like tension and compression, but the *net internal axial force is zero* — it is [[bending stress]], not axial stress. Bending stress varies linearly across the cross-section; axial stress is uniform.

## Resources
- ![](https://www.youtube.com/watch?v=f08Y39UiC-o)
- **[Engineering Toolbox — Stress](https://www.engineeringtoolbox.com/stress-d_950.html)** — quick reference with unit conversions and material yield values.

## Interactive Explorer

<iframe
  src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/mechanics/axial-stress-explorer.html"
  width="100%"
  height="1350"
  style="border: none; border-radius: 8px;"
  loading="lazy"
  title="Axial stress interactive explorer — cross sections, tension diagram, and practice problems">
</iframe>

## Practice
- A hollow aluminum tube has an outer diameter of $40\ \text{mm}$ and a wall thickness of $3\ \text{mm}$. It carries a compressive load of $8\ \text{kN}$. What is the axial stress? Is this tensile or compressive?

> [!NOTE]- Answer
> **Step 1 — find the cross-sectional area.**
> The inner diameter is $d_i = d_o - 2t = 40 - 2(3) = 34\ \text{mm}$.
> $$A = \frac{\pi}{4}\left(d_o^2 - d_i^2\right) = \frac{\pi}{4}\left(0.040^2 - 0.034^2\right) \approx 3.49 \times 10^{-4}\ \text{m}^2$$
>
> **Step 2 — compute axial stress.**
> The load is compressive, so $F = -8\ \text{kN} = -8000\ \text{N}$.
> $$\sigma = \frac{F}{A} = \frac{-8000}{3.49 \times 10^{-4}} \approx -22.9\ \text{MPa}$$
>
> **The stress is −22.9 MPa — compressive.**
