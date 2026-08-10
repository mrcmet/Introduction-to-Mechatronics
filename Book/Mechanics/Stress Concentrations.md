---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> A **stress concentration** is a localised amplification of stress caused by an abrupt change in geometry — a hole, notch, fillet, groove, or keyway. The maximum local stress $\sigma_{max}$ exceeds the nominal (average) stress $\sigma_{nom}$ by a factor $K_t$: the **stress concentration factor**. This factor depends only on the geometry of the discontinuity, not on the material.

Notes:
- The nominal stress $\sigma_{nom}$ is calculated using the basic formula appropriate for the loading type ([[Axial Stress]], [[Bending Stress]], or [[Torsional Shear Stress]]), computed at the net cross-section area at the discontinuity location.
- $K_t$ values are obtained from published charts or tables for standard geometries (circular hole in a plate, U-notch, shoulder fillet, etc.). 
	- $K_t$ is typically in the range 1.5–4 for common features; a sharp re-entrant corner approaches $K_t \to \infty$ in theory.
- **In static loading**, ductile materials loaded slowly can often redistribute stress by local yielding, partially relieving the concentration. For this reason, $K_t$ is sometimes ignored for ductile materials under static loads — though this is an approximation, and it never applies near the endurance limit.
- **In fatigue loading**, stress concentrations are far more damaging: cracks initiate at stress concentration sites even when the nominal stress is well below [[Yield Strength]]. 
	- A notch sensitivity factor $q$ scales $K_t$ into a fatigue stress concentration factor $K_f = 1 + q(K_t - 1)$. See [[Fatigue]].
- [[Saint-Venant's Principle]] explains why stress concentrations are local: the stress disturbance decays within roughly one member width of the discontinuity. Away from it, the basic stress formulas are valid again.

## Equations

> [!equation] Stress Concentration — Axial or Bending
> $$\sigma_{max} = K_t \cdot \sigma_{nom}$$
>
> - $K_t$ — stress concentration factor (dimensionless, from charts/tables; depends on geometry only)
> - $\sigma_{nom}$ — nominal stress at the net section using [[Axial Stress]] or [[Bending Stress]] formula (Pa)

> [!equation] Stress Concentration — Torsion
> $$\tau_{max} = K_{ts} \cdot \tau_{nom}$$
>
> - $K_{ts}$ — stress concentration factor in shear (dimensionless; separate charts from $K_t$)
> - $\tau_{nom}$ — nominal shear stress using [[Torsional Shear Stress]] formula (Pa)

## Examples and Non-Examples

- **Central hole in a plate under axial tension.** A steel plate (width $w = 80\ \text{mm}$, thickness $t = 10\ \text{mm}$) with a central circular hole ($d = 20\ \text{mm}$) carries an axial load $F = 40\ \text{kN}$. The hole-to-width ratio is $d/w = 0.25$, giving $K_t \approx 2.4$ (from standard charts).
$$\sigma_{nom} = \frac{F}{(w - d)\, t} = \frac{40{,}000}{(0.080 - 0.020) \times 0.010} = 66.7\ \text{MPa}$$
$$\sigma_{max} = K_t \cdot \sigma_{nom} = 2.4 \times 66.7 \approx 160\ \text{MPa}$$
The peak stress at the hole edge is 2.4× higher than the average — a significant amplification that a naive $F/A$ calculation would miss entirely.

- **Shoulder fillet on a shaft.** A shaft steps from diameter $D = 40\ \text{mm}$ to $d = 30\ \text{mm}$ with a fillet radius $r = 3\ \text{mm}$. Ratios: $D/d = 1.33$, $r/d = 0.1$, giving $K_t \approx 1.7$ for bending from standard charts. Any bending moment at this section must be multiplied by 1.7 when checking stress against the fillet.

- **Counter-example — $K_t$ does not apply to cracks.** Stress concentration factors are derived for smooth geometric features where the stress field can be analysed. A pre-existing crack is not a smooth notch; it requires fracture mechanics (stress intensity factors, $K_I$) — a separate field entirely. Applying $K_t$ to a crack opening underestimates the severity of the stress field.

## Resources
+ ![](https://youtu.be/LTsVPMVdhsE?si=CylK3mVFh9_ftruR)

+ ![](https://youtu.be/kZN0xdPMQzw?si=MMG3etS535rx1RyF)
- **[MechaniCalc — Stress Concentration Calculator](https://mechanicalc.com/calculators/stress-concentration/)** — interactive charts for common geometries; returns $K_t$ for holes, notches, and fillets under axial and bending loads.

## Practice
- A flat steel bar (width $w = 60\ \text{mm}$, thickness $t = 8\ \text{mm}$) has a central circular hole of diameter $d = 15\ \text{mm}$ and carries an axial tensile load $F = 25\ \text{kN}$. The stress concentration factor for this geometry is $K_t = 2.5$. (a) What is the nominal stress at the net section? (b) What is the maximum stress at the hole edge?

> [!NOTE]- Answer
> **(a) Net section area:**
> $$A_{net} = (w - d)\, t = (0.060 - 0.015) \times 0.008 = 3.6 \times 10^{-4}\ \text{m}^2$$
> $$\sigma_{nom} = \frac{F}{A_{net}} = \frac{25{,}000}{3.6 \times 10^{-4}} \approx 69.4\ \text{MPa}$$
>
> **(b) Peak stress:**
> $$\sigma_{max} = K_t \cdot \sigma_{nom} = 2.5 \times 69.4 = 173.6\ \text{MPa}$$
