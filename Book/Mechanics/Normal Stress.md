---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Normal stress** ($\sigma$) is the component of stress that acts *perpendicular* to the face it acts on, as opposed to [[Shear Stress]], which acts parallel to the same face. On the [[Stress Tensor]], normal stresses occupy the three diagonal positions and are responsible for a body stretching, compressing, or bending rather than sliding.

Notes:
- "Normal" is a geometry term meaning *perpendicular* — it has nothing to do with ordinary or typical. A normal stress always points straight into or away from the face it acts on.
- Units are pascals (Pa) or megapascals (MPa).
- In the 3D stress tensor, each face carries exactly one normal stress — the three diagonal entries:

$$\boldsymbol{\sigma} = \begin{bmatrix} \sigma_x & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_y & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_z \end{bmatrix}$$

The diagonal ($\sigma_x$, $\sigma_y$, $\sigma_z$) is normal stress. Everything off the diagonal is [[Shear Stress]].

- The subscript denotes which face the stress acts on: $\sigma_x$ is the normal stress on the face whose outward normal points in the $x$-direction. Positive values are tensile (pulling away); negative values are compressive (pushing in).
- Normal stress drives normal *strain* ($\varepsilon$), related through [[Young's Modulus]] $E$ by $\sigma = E\varepsilon$ — this is [[Hooke's Law]].
- Two distinct load types produce normal stress in structural members, each with its own formula and distribution across the cross-section:

| Type | What causes it | Formula | Distribution across section |
|---|---|---|---|
| [[Axial Stress]] | Force along a member's long axis | $\sigma = F/A$ | Uniform across entire cross-section |
| [[Bending Stress]] | Bending moment $M$ in a beam | $\sigma = -My/I$ | Linear — max at outer fibers, zero at [[Neutral Axis]] |

- Positive normal stress is tensile by convention; compressive is negative. This sign matters when combining stresses — see [[Combined Loading]].

## Examples and Non-Examples

- **Axial tension.** A 20 mm diameter steel rod carries a tensile load of $F = 15\ \text{kN}$. The normal stress is uniform across the cross-section:
$$A = \frac{\pi (0.020)^2}{4} \approx 3.14 \times 10^{-4}\ \text{m}^2 \qquad \sigma = \frac{F}{A} = \frac{15{,}000}{3.14 \times 10^{-4}} \approx 47.8\ \text{MPa}$$
The stress vector points perpendicular to the cut face and away from it — textbook [[Axial Stress]].

- **Bending fiber stress.** The bottom fiber of a simply supported beam loaded at mid-span is in tension; the top fiber is in compression. Both stresses point perpendicular to the cross-section face, making them normal stresses — but the value varies linearly from $+\sigma_{max}$ to $-\sigma_{max}$ across the depth. This is [[Bending Stress]], the second member of the normal stress family.

- **Counter-example — shear stress is not normal stress.** A bolt loaded transversely has stress *parallel* to its cross-section face. That is [[Shear Stress]], not normal stress — even though the bolt looks like an axially loaded rod from the outside. The direction relative to the face is what defines the type, not the shape of the member.

## Resources

![[Drawing 2026-05-12 15.40.48.excalidraw 1 1 1.svg]]

![](https://youtu.be/aQf6Q8t1FQE?si=oqTczpKPt0XLAxJ-)

![](https://youtu.be/oAzwClT1GRQ?si=TbDGGbixSm3G8Yoe)

## Practice
- A solid circular rod has a diameter of $d = 25\ \text{mm}$ and carries an axial compressive load of $F = 40\ \text{kN}$. (a) What is the normal stress? (b) Is it tensile or compressive?

> [!NOTE]- Answer
> **(a) Find the cross-sectional area.**
> $$A = \frac{\pi (0.025)^2}{4} \approx 4.91 \times 10^{-4}\ \text{m}^2$$
> **(b) Compute the stress — compressive load means negative sign.**
> $$\sigma = -\frac{F}{A} = -\frac{40{,}000}{4.91 \times 10^{-4}} \approx -81.5\ \text{MPa}$$
> The negative value confirms **compressive** normal stress.
