---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Transverse shear stress** is the [[Shear Stress]] produced in a beam by an internal shear force $V$. Unlike [[Direct Shear Stress]], which is assumed uniform, transverse shear stress varies continuously across the cross-section — for a rectangular beam it follows a parabolic profile, peaking at the [[Neutral Axis]] and dropping to zero at the top and bottom edges.

Notes:
- The shear stress at any point in the cross-section is given by the **shear formula**:

$$\tau = \frac{VQ}{It}$$

where:
- $V$ = internal shear force at the section (from the [[Shear Force Diagram]])
- $Q$ = first moment of area of the partial section above (or below) the point of interest, about the [[Neutral Axis]]: $Q = A'\bar{y}'$
- $I$ = [[Second Moment of Area]] of the entire cross-section about the neutral axis
- $t$ = width of the cross-section at the point where $\tau$ is evaluated

- **How to compute $Q$:** Cut the cross-section at height $y$ from the neutral axis. Take the area $A'$ on one side of the cut, find the distance $\bar{y}'$ from the neutral axis to its centroid. Then $Q = A'\bar{y}'$. $Q$ is maximum at the neutral axis ($y = 0$) and zero at the outer edges, which drives the parabolic profile.

- For a **rectangular cross-section** (width $b$, total height $h$), the maximum shear stress at the neutral axis simplifies to:
$$\tau_{max} = \frac{3V}{2A}$$
This is 1.5× the average $V/A$ that direct shear assumes — a meaningful error if you apply the wrong formula.

- The parabolic distribution means the outer fibers of a beam carry *no* transverse shear stress. This is the opposite of [[Bending Stress]], which is maximum at the outer fibers and zero at the neutral axis. Under combined loading, both exist simultaneously at every cross-section but peak at different locations.

- The shear formula assumes the shear stress is uniform across the width $t$ at any given height $y$ — a good approximation for narrow cross-sections but less accurate for wide flanges.

- Transverse shear is one of three shear stress types — see [[Shear Stress]] for the family overview and formula comparison.

## Examples and Non-Examples

- **Maximum shear stress in a rectangular beam.** A rectangular beam ($b = 50\ \text{mm}$, $h = 100\ \text{mm}$) carries an internal shear force $V = 10\ \text{kN}$.
$$A = 0.050 \times 0.100 = 5.0 \times 10^{-3}\ \text{m}^2$$
$$\tau_{max} = \frac{3V}{2A} = \frac{3 \times 10{,}000}{2 \times 5.0 \times 10^{-3}} = 3.0\ \text{MPa}$$
Verify using $VQ/It$ at the neutral axis. $Q_{max} = b(h/2)(\bar{y}') = 0.050 \times 0.050 \times 0.025 = 6.25 \times 10^{-5}\ \text{m}^3$, $I = bh^3/12 = 4.17 \times 10^{-6}\ \text{m}^4$, $t = 0.050\ \text{m}$:
$$\tau = \frac{VQ}{It} = \frac{10{,}000 \times 6.25 \times 10^{-5}}{4.17 \times 10^{-6} \times 0.050} = 3.0\ \text{MPa}\ ✓$$

- **Shear stress at a point above the neutral axis.** Same beam, evaluate $\tau$ at $y = 20\ \text{mm}$ above the neutral axis. The strip above the cut runs from $y = 20\ \text{mm}$ to $y = 50\ \text{mm}$ (the top edge).
$$A' = 0.050 \times (0.050 - 0.020) = 1.5 \times 10^{-3}\ \text{m}^2$$
$$\bar{y}' = 0.020 + \frac{0.030}{2} = 0.035\ \text{m}$$
$$Q = A'\bar{y}' = 1.5 \times 10^{-3} \times 0.035 = 5.25 \times 10^{-5}\ \text{m}^3$$
$$\tau = \frac{10{,}000 \times 5.25 \times 10^{-5}}{4.17 \times 10^{-6} \times 0.050} \approx 2.52\ \text{MPa}$$
Lower than the neutral-axis maximum, as the parabolic profile predicts.

- **Counter-example — uniform shear is not transverse shear.** Applying the direct shear formula $\tau = V/A$ to this beam gives $\tau = 2.0\ \text{MPa}$ — 33% below the true maximum of 3.0 MPa. This underestimates the peak stress and leads to unconservative designs. The uniform assumption is only valid for pins and bolts ([[Direct Shear Stress]]), not for beams.

## Resources
- ![](https://www.youtube.com/watch?v=MFxBFGEFJsY)

## Practice
- A rectangular timber beam ($b = 75\ \text{mm}$, $h = 150\ \text{mm}$) supports an internal shear force of $V = 18\ \text{kN}$. (a) What is the maximum transverse shear stress and where does it occur? (b) What is the shear stress at $y = 50\ \text{mm}$ above the neutral axis?

> [!NOTE]- Answer
> **(a) Maximum shear stress.**
> $$A = 0.075 \times 0.150 = 1.125 \times 10^{-2}\ \text{m}^2$$
> $$\tau_{max} = \frac{3V}{2A} = \frac{3 \times 18{,}000}{2 \times 1.125 \times 10^{-2}} = 2.4\ \text{MPa}$$
> Occurs at the **neutral axis** (75 mm from either edge). Zero at top and bottom.
>
> **(b) Shear stress at $y = 50\ \text{mm}$.**
> $$A' = 0.075 \times (0.075 - 0.050) = 1.875 \times 10^{-3}\ \text{m}^2$$
> $$\bar{y}' = 0.050 + \frac{0.025}{2} = 0.0625\ \text{m}$$
> $$Q = 1.875 \times 10^{-3} \times 0.0625 = 1.172 \times 10^{-4}\ \text{m}^3$$
> $$I = \frac{0.075 \times 0.150^3}{12} = 2.109 \times 10^{-5}\ \text{m}^4$$
> $$\tau = \frac{18{,}000 \times 1.172 \times 10^{-4}}{2.109 \times 10^{-5} \times 0.075} \approx 1.33\ \text{MPa}$$
