---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Bending stress** ($\sigma$) is the [[Normal Stress]] that develops in a beam cross-section as a result of an applied bending moment $M$. It varies linearly across the section — zero at the [[Neutral Axis]] and maximum at the outermost fibers — and is given by the flexure formula: $\sigma = -My/I$, where $y$ is measured from the neutral axis and $I$ is the [[Second Moment of Area]].

Notes:
- The negative sign follows the convention that:
	- positive $M$ (sagging) causes compression in the top fiber ($y > 0$) and tension in the bottom fiber ($y < 0$). 
	- Some texts use $\sigma = My/I$ with the opposite sign convention — be consistent within a problem.
- Maximum bending stress occurs at the fiber farthest from the neutral axis. 
	- If $c$ is that distance, then $\sigma_{max} = Mc/I$. 
	- This is the value to compare against [[Yield Strength]] when applying a [[Factor of Safety]].
- The **section modulus** $S = I/c$ (units: m³) condenses $I$ and $c$ into a single geometric property: $\sigma_{max} = M/S$. A larger $S$ means less stress for the same moment.
	- The design goal for beams is to maximize $S$ per unit weight.
- Bending stress assumes:
	1) the beam is prismatic.
	2) the material is linearly elastic.
	3) the plane cross-sections remain plane after bending (Euler–Bernoulli assumption). 
	+ These are [[Saint-Venant's Principle]] conditions — the formula breaks down near load application points and geometric discontinuities ([[Stress Concentrations]]).
- Bending stress and [[Transverse Shear Stress in Beams]] coexist in loaded beams. At the neutral axis, bending stress is zero but shear stress is maximum; at the outer fibers, bending stress is maximum but shear stress is zero. The critical point depends on the cross-section and loading.

## Equations

> [!equation] Flexure Formula
> $$\sigma = -\frac{M y}{I}$$
>
> - $\sigma$ — bending stress at distance $y$ from the neutral axis (Pa)
> - $M$ — bending moment at the section of interest (N·m); from the [[Bending Moment Diagram]]
> - $y$ — distance from the [[Neutral Axis]] to the fiber, positive upward (m)
> - $I$ — [[Second Moment of Area]] about the neutral axis (m⁴)

> [!equation] Maximum Bending Stress
> $$\sigma_{max} = \frac{M c}{I} = \frac{M}{S}$$
>
> - $c$ — distance from neutral axis to the outermost fiber (m)
> - $S = I/c$ — section modulus (m³); a larger $S$ means a more efficient cross-section

## Examples and Non-Examples

- **Simply supported beam, mid-span load.** A simply supported steel beam (span $L = 4\ \text{m}$, rectangular cross-section $b = 50\ \text{mm}$, $h = 150\ \text{mm}$) carries a central point load $P = 12\ \text{kN}$. Maximum moment from the [[Bending Moment Diagram]]: $M_{max} = PL/4 = 12{,}000 \times 4 / 4 = 12{,}000\ \text{N·m}$.
$$I = \frac{0.050 \times 0.150^3}{12} = 1.406 \times 10^{-5}\ \text{m}^4 \qquad c = 0.075\ \text{m}$$
$$\sigma_{max} = \frac{Mc}{I} = \frac{12{,}000 \times 0.075}{1.406 \times 10^{-5}} \approx 64.0\ \text{MPa}$$
If the beam is A36 steel ($\sigma_y = 250\ \text{MPa}$), the [[Factor of Safety]] against yielding is $250/64 \approx 3.9$.

- **Asymmetric T-section — different stress at top and bottom.** In the T-beam from [[Neutral Axis]], $\bar{y} = 70\ \text{mm}$ from the bottom. The bottom fiber is $c_{bot} = 70\ \text{mm}$ from the NA; the top fiber is $c_{top} = 30\ \text{mm}$. For the same $M$ and $I$, $\sigma_{bot} = Mc_{bot}/I$ is $70/30 \approx 2.3\times$ larger than $\sigma_{top}$. The bottom fiber governs design — a deliberate feature of T-beam geometry that concentrates material near the high-stress zone.

- **Counter-example — shear stress, not bending stress, governs short beams.** A very short, deep beam with a large point load may have a shear force $V$ that produces [[Transverse Shear Stress in Beams]] exceeding the bending stress at the neutral axis. Slender beams (large span-to-depth ratio) are governed by bending; compact beams may be governed by shear. Always check both.

## Resources
- ![](https://youtu.be/f08Y39UiC-o?si=RBRcb9iRuxtMzBvs)
- **[MechaniCalc — Bending Stress in Beams](https://mechanicalc.com/reference/beam-analysis#bending-stress-in-beam)** — flexure formula with worked examples and section modulus tables.

## Practice
- A cantilever beam ($L = 2\ \text{m}$) has a solid circular cross-section with diameter $d = 40\ \text{mm}$ and carries a downward tip load $P = 500\ \text{N}$. (a) What is the maximum bending moment? (b) What is the maximum bending stress, and where does it occur?

> [!NOTE]- Answer
> **(a) Maximum moment** occurs at the fixed end (from the [[Bending Moment Diagram]] for a cantilever):
> $$M_{max} = PL = 500 \times 2 = 1{,}000\ \text{N·m}$$
>
> **(b) Cross-section properties:**
> $$I = \frac{\pi (0.040)^4}{64} \approx 1.257 \times 10^{-7}\ \text{m}^4 \qquad c = 0.020\ \text{m}$$
> $$\sigma_{max} = \frac{Mc}{I} = \frac{1{,}000 \times 0.020}{1.257 \times 10^{-7}} \approx 159\ \text{MPa}$$
> Maximum bending stress occurs at the top and bottom outer fibers at the fixed end — tension in the bottom fiber, compression in the top fiber.
