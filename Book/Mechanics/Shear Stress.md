---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Shear stress** ($\tau$) is the component of stress that acts *parallel* to the face it acts on, as opposed to [[Normal Stress]], which acts perpendicular to the same face. On the [[Stress Tensor]], shear stresses occupy the six off-diagonal positions and are what cause a body to deform by sliding rather than by stretching or compressing.

Notes:
- Units are pascals (Pa) or megapascals (MPa) — identical to normal stress.
- Shear stress is indicated as the plane the stress is acting on, and the direction in which it's acting. This is commonly denoted in the subscript.
+ ![[Drawing 2026-05-12 15.40.48.excalidraw.svg]]
- In the 3D stress tensor, each face of an infinitesimal element carries one normal stress and two shear components. Rotational equilibrium requires that complementary shear stresses are equal ($\tau_{xy} = \tau_{yx}$, etc.), reducing nine entries to six independent values:

$$\boldsymbol{\sigma} = \begin{bmatrix} \sigma_x & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_y & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_z \end{bmatrix}$$
+ The diagonal is [[Normal Stress]]. Everything off the diagonal is shear.
+ This leads us to the fact that we have only 3 "Shear stresses"
	+ Shear stress on the X plane in the Y direction: $\tau_{xy}$ 
	+ Shear stress on the Y plane in the Z direction: $\tau_{yz}$ 
	+ Shear stress on the Z plane in the X direction: $\tau_{zx}$ 
+ In principal we can draw all 6 potential shear stresses on one stress tensor. However as stated above Rotational equilibrium requires that complementary shear stresses are equal ($\tau_{xy} = \tau_{yx}$, etc.) reducing this to 3 Shear stresses : $\tau_{xy}$ , $\tau_{zx}$ , $\tau_{yz}$
+ ![[Drawing 2026-05-12 15.40.48.excalidraw 1.svg]]
+ In the case that forces conspire to create multiple shear stresses in the same plane and direction then these stresses can be added directly.
- Shear stress drives shear *strain* ($\gamma$), related through the [[Shear Modulus]] $G$ by $\tau = G\gamma$ — the shear analogue of [[Hooke's Law]].
- Three distinct load types produce shear stress in structural members, each with its own formula and distribution across the cross-section:

| Type | What causes it | Formula | Distribution across section |
|---|---|---|---|
| [[Direct Shear Stress]] | Transverse force on a pin, bolt, or rivet | $\tau = V/A$ | Assumed uniform |
| [[Transverse Shear Stress in Beams]] | Internal shear force $V$ along a beam | $\tau = VQ/It$ | Parabolic — max at centroid, zero at outer edges |
| [[Torsional Shear Stress]] | Twisting moment $T$ on a shaft | $\tau = Tr/J$ | Linear — zero at center, max at outer surface |

- Under [[Combined Loading]], all three types can be present simultaneously in the same cross-section. Where they share the same direction, their values add directly.

## Examples and Non-Examples

- **Pin in single shear.** A clevis pin loaded transversely develops stress parallel to its cut face. One cross-section resists the entire load: $\tau = V/A$. This is the simplest shear case — see [[Direct Shear Stress]] for worked numbers.

- **Beam under a point load.** The internal shear force produces a *parabolic* shear stress profile across the cross-section. Maximum shear occurs at the neutral axis, not at the top or bottom fiber — the exact opposite of [[Bending Stress]].

- **Rotating driveshaft.** An applied torque $T$ creates shear stress that is zero at the shaft center and reaches a maximum at the outer radius: $\tau_{max} = Tr/J$. Same unit ($\tau$), completely different formula and geometry — see [[Torsional Shear Stress]].

- **Counter-example — axial load is not shear.** A rod pulled along its length develops [[Axial Stress]], which acts *perpendicular* to the cut face. Even though the formula looks the same ($\sigma = F/A$), the direction is normal, not parallel. The stress tensor for a purely axial member has only diagonal entries; all six shear components are zero.

## Resources

![](https://youtu.be/tjhFKH8fL7s?si=hudKfeYMfvlZslL_)

![](https://youtu.be/aQf6Q8t1FQE?si=ekIaWoXwrB5l9rTH)
## Practice
- A stress tensor has $\sigma_x = 80\ \text{MPa}$, $\tau_{xy} = 30\ \text{MPa}$, and all other components zero. (a) How many independent nonzero values does this tensor have? (b) What is $\tau_{yx}$?

> [!NOTE]- Answer
> (a) Two independent nonzero values: $\sigma_x = 80\ \text{MPa}$ and $\tau_{xy} = 30\ \text{MPa}$.
> (b) By the complementary shear stress condition, $\tau_{yx} = \tau_{xy} = 30\ \text{MPa}$.
