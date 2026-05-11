---
tags:
  - mechanics
  - materials
---
#mechanics #materials

## Definition
> [!definition]
> **Yield strength** ($\sigma_y$) is the [[axial stress]] at which a material transitions from elastic to plastic deformation — the threshold above which permanent shape change accumulates. It is read from the [[stress-strain curve]] either at the material's distinct yield point or, for materials without a clear knee, using the **0.2% offset method**.

Notes:
- The 0.2% offset method draws a line parallel to the initial elastic slope (set by [[Young's modulus]]) starting at $\varepsilon = 0.002\ \text{m/m}$. Where that line intersects the stress–strain curve defines $\sigma_y$. Aluminum alloys and most non-ferrous metals require this method because they have no sharp yield point.
- [[Hooke's law]] applies only below $\sigma_y$. Above it, stress and [[strain]] are no longer proportional, and the material will not return to its original shape when unloaded.
- Yield strength is the primary safety boundary in elastic design: keeping operating stress below $\sigma_y$ ensures a component springs back when the load is removed. The margin between operating stress and $\sigma_y$ is captured in the [[factor of safety]].
- Mild steels show a distinct upper and lower yield point — a sudden load drop at first yield followed by a flat plateau. Most alloys do not exhibit this and require the offset method.
- Do not confuse $\sigma_y$ with [[ultimate tensile strength]] ($\sigma_u$): $\sigma_y$ is where plasticity begins; $\sigma_u$ is the peak of the curve, reached at much larger strain.

## Examples and Non-Examples
- **Checking a rod against yield.** A solid steel rod ($d = 20\ \text{mm}$, $\sigma_y = 250\ \text{MPa}$) carries $F = 60\ \text{kN}$ in tension.
	  - Area: $A = \pi(0.020)^2/4 \approx 3.14 \times 10^{-4}\ \text{m}^2$
	  - Stress: $\sigma = 60{,}000\ /\ 3.14 \times 10^{-4} \approx 191\ \text{MPa}$
	  - Since $191\ \text{MPa} < 250\ \text{MPa}$, the rod stays elastic and returns to its original length when unloaded.

- **0.2% offset on Al 6061-T6.** Aluminum 6061-T6 has no sharp yield point. A tensile test shows the 0.2%-offset line intersecting the curve at $\sigma \approx 276\ \text{MPa}$. That is the reported $\sigma_y$ for this alloy — above it, the part takes a permanent set.

- **Counter-example — stiffness is not strength.** Diamond has $E \approx 1{,}000\ \text{GPa}$, far stiffer than any steel, yet it fractures without yielding at all. Stiffness (Young's modulus) and yield strength are independent material properties — a material can be stiff and brittle, or soft and tough.

## Resources
- ![](https://www.youtube.com/watch?v=67fSwIjYJ-E)
- <iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/mechanics/stress-strain-curve.html" width="100%" height="560" style="border: none; border-radius: 8px;" loading="lazy" title="Interactive stress–strain curve — elastic and plastic regions, yield point"></iframe>
- **[Engineering Toolbox — Yield Strength](https://www.engineeringtoolbox.com/yield-strength-d_950.html)** — material tables with typical $\sigma_y$ values for common metals.

## Practice
- An Al 6061-T6 rod ($\sigma_y = 276\ \text{MPa}$, $d = 15\ \text{mm}$) is loaded in tension. What is the maximum force it can carry before yielding?

> [!NOTE]- Answer
> **Step 1 — find the cross-sectional area.**
> $$A = \frac{\pi d^2}{4} = \frac{\pi (0.015)^2}{4} \approx 1.77 \times 10^{-4}\ \text{m}^2$$
>
> **Step 2 — solve for force at yield.**
> $$F = \sigma_y \cdot A = 276 \times 10^6 \times 1.77 \times 10^{-4} \approx 48{,}900\ \text{N} \approx 48.9\ \text{kN}$$
>
> **The rod yields at approximately 48.9 kN.**
