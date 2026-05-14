---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> The **shear modulus** ($G$) is a material property that relates [[Shear Stress]] to shear strain: $\tau = G\gamma$. It is the shear analogue of [[Young's Modulus]] and describes how resistant a material is to deformation by sliding — a high $G$ means the material is stiff in shear.

Notes:
- Units are pascals (Pa) or gigapascals (GPa), identical to [[Young's Modulus]].
- $G$ is not independent of $E$ and $\nu$. For any isotropic material:

$$G = \frac{E}{2(1 + \nu)}$$

where $E$ is [[Young's Modulus]] and $\nu$ is [[Poisson's Ratio]]. Only two of the three elastic constants are independent — knowing any two determines the third.

- Typical values for common engineering materials:

| Material | $G$ (GPa) |
|---|---|
| Steel | ~80 |
| Aluminum | ~26 |
| Copper | ~45 |
| Rubber | ~0.001 |

- Shear modulus appears in the torsion formula for angle of twist: $\phi = TL/(GJ)$. A shaft with a low $G$ will twist more for the same applied [[Torque]].
- Like [[Young's Modulus]], $G$ is only valid within the elastic range of the [[Stress-Strain Curve]]. Beyond yield, the linear relationship between $\tau$ and $\gamma$ no longer holds.

## Examples and Non-Examples

- **Shear strain from shear stress.** A steel machine component ($G = 80\ \text{GPa}$) experiences a shear stress of $\tau = 100\ \text{MPa}$. The resulting shear strain is:
$$\gamma = \frac{\tau}{G} = \frac{100 \times 10^6}{80 \times 10^9} = 1.25 \times 10^{-3}\ \text{rad}$$
The element deforms by about 0.07° — imperceptible by eye, but mechanically real.

- **Consistency check via elastic constants.** For steel, $E = 200\ \text{GPa}$ and $\nu = 0.29$. Predicting $G$:
$$G = \frac{E}{2(1+\nu)} = \frac{200}{2(1.29)} \approx 77.5\ \text{GPa}$$
Close to the tabulated 80 GPa — small discrepancies reflect real material variation and measurement method.

- **Counter-example — $G$ does not describe axial stiffness.** Stretching a rod along its axis engages [[Young's Modulus]] $E$, not $G$. The shear modulus only applies when the stress acts *parallel* to the face. Rubber has both $E$ and $G$ that are very low, but they describe different deformation modes — neither tells you about the other.

## Resources
- **[Engineering Toolbox — Modulus of Rigidity](https://www.engineeringtoolbox.com/modulus-rigidity-d_946.html)** — tabulated $G$ values for common materials.

## Practice
- An aluminum component ($G = 26\ \text{GPa}$) experiences a shear stress of $\tau = 65\ \text{MPa}$. (a) What shear strain does it experience? (b) Using $E = 69\ \text{GPa}$ and $\nu = 0.33$ for aluminum, verify $G$ from the elastic constants formula.

> [!NOTE]- Answer
> **(a) Shear strain.**
> $$\gamma = \frac{\tau}{G} = \frac{65 \times 10^6}{26 \times 10^9} = 2.5 \times 10^{-3}\ \text{rad}$$
>
> **(b) Verify $G$.**
> $$G = \frac{E}{2(1+\nu)} = \frac{69}{2(1.33)} \approx 25.9\ \text{GPa} \approx 26\ \text{GPa}\ ✓$$
