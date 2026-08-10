---
tags:
  - mechanics
  - materials
---
#mechanics #materials

## Definition
> [!definition]
> A **stress-strain curve** is a graph of [[axial stress]] ($\sigma$) versus [[strain]] ($\varepsilon$) produced by pulling a standard test coupon to fracture at a controlled rate. It is the primary source of a material's mechanical properties — [[Young's modulus]], [[yield strength]], [[ultimate tensile strength]], and ductility can all be read from a single curve.

Notes:
- The initial linear slope is [[Young's modulus]]: $E = \sigma / \varepsilon$. [[Hooke's law]] holds throughout this region — remove the load and the coupon returns to its original length.
- The curve leaves the linear region at the **proportional limit**. Shortly after, at the **yield point** ($\sigma_y$), plastic (permanent) deformation begins. 
	- For materials without a sharp knee, $\sigma_y$ is found by the 0.2% offset method — see [[yield strength]].
- Beyond $\sigma_y$ the curve rises more slowly through **strain hardening** until it peaks at the [[ultimate tensile strength]] ($\sigma_u$). 
	- After the peak, **necking** begins — the cross-section constricts locally — and the engineering stress appears to fall until fracture.
- **Engineering stress** uses the original cross-sectional area throughout 
- **True stress** uses the instantaneous area. 
	- The two curves diverge significantly after necking begins. Unless stated otherwise, material property tables report *engineering values*.
- Ductile materials (low-carbon steel, aluminum alloys) show a long plastic plateau and large strain at fracture. Brittle materials (cast iron, ceramics) fracture near the proportional limit with almost no plastic region.

## Examples and Non-Examples
- **Reading $E$ from the curve.** In the linear region, a test on structural steel records $\sigma = 200\ \text{MPa}$ at $\varepsilon = 0.001\ \text{m/m}$. The slope — and therefore $E$ — is $200\ \text{MPa}\ /\ 0.001 = 200\ \text{GPa}$.

- **Locating $\sigma_y$ on mild steel.** Mild steel (A36) shows a sharp upper yield point at $\approx 290\ \text{MPa}$, a brief load drop, then a lower yield plateau near $250\ \text{MPa}$. The lower plateau value is the tabulated $\sigma_y = 250\ \text{MPa}$ because it is the conservative, repeatable figure.

- **Counter-example — a spring force–displacement curve is not a stress–strain curve.** A load vs. deflection plot for a coil spring looks similar — linear then nonlinear — but its axes are force (N) and displacement (mm), which depend on geometry. A stress–strain curve normalizes both axes by area and length, making it a *material* property rather than a *component* property.

## Resources
- ![](https://youtu.be/AkX6JqlWRqc?si=pyS7D6UAU5aJQgli)
- <iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/mechanics/stress-strain-curve.html" width="100%" height="605" style="border: none; border-radius: 8px;" loading="lazy" title="Interactive stress–strain curve — elastic and plastic regions, yield point"></iframe>


## Practice
- On a stress–strain curve for Al 6061-T6, the linear region ends at approximately $\sigma = 276\ \text{MPa}$ and $\varepsilon = 0.004\ \text{m/m}$. What is $E$? Does this match the accepted value of $69\ \text{GPa}$?

> [!NOTE]- Answer
> $$E = \frac{276 \times 10^6}{0.004} = 69\ \text{GPa}$$
> Yes — the slope of the linear region is exactly Young's modulus.
