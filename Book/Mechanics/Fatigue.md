---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Fatigue** is the progressive, localised damage that accumulates in a material under repeated cyclic loading, eventually causing fracture at stress levels well below the [[Ultimate Tensile Strength]] — and sometimes below [[Yield Strength]]. Unlike static failure, fatigue failure initiates at a microscopic crack, usually at a [[Stress Concentrations|stress concentration]] site, and propagates incrementally with each load cycle until the remaining cross-section can no longer carry the load.

Notes:
- Fatigue failure is responsible for the majority of mechanical failures in service. It is particularly critical wherever loads reverse or fluctuate: rotating shafts, motor mounts, vibrating frames, connecting rods, and fasteners.
- **S-N curves** (stress amplitude $S$ vs. cycles to failure $N$, also called Wöhler curves) characterise fatigue life experimentally. A specimen is subjected to fully reversed cyclic stress and the number of cycles to fracture is recorded for various stress levels.
- **Endurance limit ($S_e$):** For steels, the S-N curve flattens at high cycle counts — below a certain stress amplitude the material can theoretically survive infinite cycles. A rough approximation: $S_e \approx 0.5 \times S_{ut}$ for steel (where $S_{ut}$ is [[Ultimate Tensile Strength]]), valid for $S_{ut} \leq 1400\ \text{MPa}$.
- **Aluminium and many non-ferrous metals have no endurance limit** — the S-N curve continues to slope downward. For these materials, fatigue life is quoted at a specified number of cycles (e.g. $10^7$ or $10^8$).
- **Stress concentrations** ([[Stress Concentrations]]) are far more damaging in fatigue than in static loading. The fatigue stress concentration factor $K_f = 1 + q(K_t - 1)$, where $q$ is the notch sensitivity factor (0 = material insensitive to notches, 1 = fully sensitive). For most steels and high-cycle applications, $q$ approaches 1.
- **Mean stress matters.** A component cycled about a tensile mean stress fails sooner than one cycled about zero mean stress. The **Goodman criterion** accounts for this: $\sigma_a/S_e + \sigma_m/S_{ut} = 1$, where $\sigma_a$ is the alternating stress amplitude and $\sigma_m$ is the mean stress.
- Surface finish, temperature, residual stresses, and corrosion all reduce the effective endurance limit. Published $S_e$ values apply to polished laboratory specimens; real components need correction factors.

## Equations

> [!equation] Endurance Limit Estimate (steel)
> $$S_e \approx 0.5\, S_{ut} \qquad \text{for}\ S_{ut} \leq 1400\ \text{MPa}$$
>
> - $S_e$ — endurance limit of a polished specimen (MPa)
> - $S_{ut}$ — [[Ultimate Tensile Strength]] (MPa)
> - Apply correction factors for surface finish, size, load type, and reliability to get the effective $S_e'$ for a real component

> [!equation] Fatigue Stress Concentration Factor
> $$K_f = 1 + q(K_t - 1)$$
>
> - $K_f$ — fatigue stress concentration factor (dimensionless)
> - $q$ — notch sensitivity factor (0–1; from material charts)
> - $K_t$ — geometric [[Stress Concentrations|stress concentration factor]]

> [!equation] Goodman Criterion
> $$\frac{\sigma_a}{S_e} + \frac{\sigma_m}{S_{ut}} = 1$$
>
> - $\sigma_a$ — alternating stress amplitude (Pa)
> - $\sigma_m$ — mean stress (Pa; positive = tensile)
> - Operating points below this line are predicted to have infinite fatigue life

## Examples and Non-Examples

- **Rotating shaft — fully reversed bending.** A steel shaft ($S_{ut} = 600\ \text{MPa}$, $S_e \approx 300\ \text{MPa}$) has a shoulder fillet with $K_t = 1.8$ and notch sensitivity $q = 0.9$.
$$K_f = 1 + 0.9(1.8 - 1) = 1.72$$
If the bending stress amplitude is $120\ \text{MPa}$, the effective alternating stress is $1.72 \times 120 = 206\ \text{MPa}$ — below $S_e = 300\ \text{MPa}$, so infinite life is predicted. Without the stress concentration, $120\ \text{MPa}$ looked very safe; with it, the safety margin is much smaller.

- **Goodman diagram — combined mean and alternating stress.** A component has $\sigma_m = 80\ \text{MPa}$ (from a preload) and $\sigma_a = 150\ \text{MPa}$ (from cyclic loading). Material: $S_e = 280\ \text{MPa}$, $S_{ut} = 560\ \text{MPa}$.
$$\frac{150}{280} + \frac{80}{560} = 0.536 + 0.143 = 0.679$$
Since $0.679 < 1$, the component is predicted to survive. The safety factor against fatigue failure is $1/0.679 \approx 1.47$.

- **Aluminium connecting rod.** An aluminium alloy rod ($S_{ut} = 310\ \text{MPa}$) has no endurance limit. At $10^7$ cycles the allowable stress amplitude (from the material's S-N curve) is approximately $90\ \text{MPa}$. Operating above this, even briefly, reduces the total fatigue life.

- **Counter-example — static safety factor is not fatigue safety factor.** A steel bracket with [[Factor of Safety]] = 3.5 against yielding ($\sigma_{max} = 70\ \text{MPa}$, $\sigma_y = 245\ \text{MPa}$) is assumed to be safe for cyclic loading. But if the bracket has a sharp notch ($K_t = 3.0$, $q = 0.85$, $K_f = 2.55$), the effective fatigue stress is $2.55 \times 70 = 178.5\ \text{MPa}$. If $S_e = 200\ \text{MPa}$, the fatigue safety factor is only $200/178.5 = 1.12$ — dangerously low, despite the generous static safety factor.

## Resources
- ![](https://www.youtube.com/watch?v=o-6V_JoRX1g)
- **[MechRef — Fatigue](https://www.mechref.org/mf/Fatigue/)** — S-N curves, endurance limits, correction factors, and Goodman criterion with worked examples for rotating shafts.

## Practice
- A steel shaft ($S_{ut} = 800\ \text{MPa}$) rotates under a fully reversed bending stress amplitude of $\sigma_a = 180\ \text{MPa}$. It has a shoulder fillet with $K_t = 2.0$ and notch sensitivity $q = 0.95$. (a) What is $K_f$? (b) What is the effective fatigue stress? (c) Does the shaft have infinite fatigue life?

> [!NOTE]- Answer
> **(a):**
> $$K_f = 1 + 0.95(2.0 - 1) = 1.95$$
>
> **(b):**
> $$\sigma_{eff} = K_f \cdot \sigma_a = 1.95 \times 180 = 351\ \text{MPa}$$
>
> **(c) Endurance limit estimate:**
> $$S_e \approx 0.5 \times 800 = 400\ \text{MPa}$$
> Since $351\ \text{MPa} < 400\ \text{MPa}$, infinite fatigue life **is predicted** — but the margin is narrow ($400/351 \approx 1.14$). In practice, surface finish and size corrections would reduce $S_e$ and likely eliminate the safety margin. A larger fillet radius (lower $K_t$) or larger shaft diameter would be the right design fix.
