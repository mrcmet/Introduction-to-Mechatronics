---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Combined loading** occurs when a structural member simultaneously carries more than one type of load — for example, a shaft that is both bent and twisted, or a column that is both compressed and bent. The stresses from each load type are computed separately using the appropriate formula, then superimposed at the critical point where the total stress state is most severe.

Notes:
- Superposition is valid as long as the material remains linearly elastic and deformations are small. Each stress component is computed independently, then combined.
- **Normal stresses add algebraically.** [[Axial Stress]] ($\sigma_{axial} = F/A$) and [[Bending Stress]] ($\sigma_{bending} = Mc/I$) both act perpendicular to the cross-section face. If they act in the same direction they add; if opposite they partially cancel. The net normal stress is $\sigma = \sigma_{axial} + \sigma_{bending}$.
- **Shear stresses in the same direction add algebraically.** [[Torsional Shear Stress]] ($\tau_{torsion} = Tr/J$) and [[Transverse Shear Stress in Beams]] ($\tau_{transverse} = VQ/It$) both act parallel to the cross-section face. Where they share the same direction, they add directly; where they oppose, they subtract.
- Finding the **critical point** is the key step: survey several candidate points around the cross-section perimeter (top fiber, bottom fiber, neutral axis, etc.), compute the full stress state at each, then identify which carries the highest combined stress.
- Once the combined stress state ($\sigma$, $\tau$) is known at the critical point, it can be compared to [[Yield Strength]] using failure criteria. This feeds directly into [[Factor of Safety]] calculations.

## Equations

> [!equation] Axial + Bending Combined Normal Stress
> $$\sigma = \frac{F}{A} \pm \frac{Mc}{I}$$
>
> - $F/A$ — [[Axial Stress]] (positive = tension)
> - $Mc/I$ — [[Bending Stress]] at distance $c$ from [[Neutral Axis]]
> - Sign: $+$ where axial and bending stresses are both tensile; $-$ where they oppose

> [!equation] Von Mises Equivalent Stress (2D)
> $$\sigma_{VM} = \sqrt{\sigma^2 + 3\tau^2}$$
>
> - Combines normal stress $\sigma$ and shear stress $\tau$ into a single equivalent stress for yield comparison
> - Yielding occurs when $\sigma_{VM} \geq \sigma_y$

## Examples and Non-Examples

- **Eccentric axial load (axial + bending).** A short column ($A = 2{,}500\ \text{mm}^2$, $I = 5.21 \times 10^{-6}\ \text{m}^4$, $c = 50\ \text{mm}$) carries a compressive force $F = 100\ \text{kN}$ applied 20 mm off-center, creating a bending moment $M = 100{,}000 \times 0.020 = 2{,}000\ \text{N·m}$.
$$\sigma_{axial} = -\frac{100{,}000}{2{,}500 \times 10^{-6}} = -40\ \text{MPa}$$
$$\sigma_{bending} = \pm\frac{2{,}000 \times 0.050}{5.21 \times 10^{-6}} = \pm 19.2\ \text{MPa}$$
The tension side: $-40 + 19.2 = -20.8\ \text{MPa}$ (still compressive). The compression side: $-40 - 19.2 = -59.2\ \text{MPa}$ — this is the critical face.

- **Motor shaft (bending + torsion).** A solid steel shaft ($d = 30\ \text{mm}$) transmits $T = 150\ \text{N·m}$ while also carrying a transverse load that creates $M = 80\ \text{N·m}$ at the critical section.
$$\sigma_{bending} = \frac{Mc}{I} = \frac{80 \times 0.015}{1.99 \times 10^{-8}} \approx 60.3\ \text{MPa}$$
$$\tau_{torsion} = \frac{Tc}{J} = \frac{150 \times 0.015}{3.98 \times 10^{-8}} \approx 56.5\ \text{MPa}$$
$$\sigma_{VM} = \sqrt{60.3^2 + 3(56.5)^2} \approx 113\ \text{MPa}$$
For steel with $\sigma_y = 250\ \text{MPa}$, the factor of safety is $250/113 \approx 2.2$.

- **Counter-example — adding normal and shear stress directly.** $\sigma + \tau$ is dimensionally correct but physically meaningless — normal and shear stresses act on different faces and cannot be simply summed. They must be combined using a failure criterion such as von Mises, which accounts for their different physical roles.

## Resources
- ![](https://www.youtube.com/watch?v=N-PlI900hSg)
- **[MechRef — Combined Loading](https://www.mechref.org/sol/combined_loading/)** — worked examples combining axial, bending, and torsional stresses with critical point identification.

## Practice
- A solid aluminum shaft ($d = 25\ \text{mm}$, $\sigma_y = 270\ \text{MPa}$) carries a torque $T = 60\ \text{N·m}$ and a bending moment $M = 45\ \text{N·m}$ at the same section. (a) Find $\sigma_{bending}$ and $\tau_{torsion}$ at the outer surface. (b) Compute the von Mises equivalent stress. (c) What is the factor of safety?

> [!NOTE]- Answer
> $$I = \frac{\pi (0.025)^4}{64} = 1.917 \times 10^{-8}\ \text{m}^4 \qquad J = 2I = 3.835 \times 10^{-8}\ \text{m}^4 \qquad c = 0.0125\ \text{m}$$
>
> **(a):**
> $$\sigma = \frac{45 \times 0.0125}{1.917 \times 10^{-8}} \approx 29.3\ \text{MPa} \qquad \tau = \frac{60 \times 0.0125}{3.835 \times 10^{-8}} \approx 19.6\ \text{MPa}$$
>
> **(b):**
> $$\sigma_{VM} = \sqrt{29.3^2 + 3(19.6)^2} = \sqrt{858 + 1152} \approx 44.8\ \text{MPa}$$
>
> **(c):** $FOS = 270 / 44.8 \approx 6.0$
