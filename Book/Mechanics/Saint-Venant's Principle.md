---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Saint-Venant's principle** states that the stress distribution caused by a localized load becomes indistinguishable from the distribution caused by a statically equivalent load at distances greater than roughly the largest dimension of the loaded region. In practice, this justifies using simple stress formulas (like [[Axial Stress]] and [[Bending Stress]]) everywhere *except* near load application points, supports, or geometric discontinuities.

Notes:
- "Statically equivalent" means same net force and same net moment — the exact distribution of how those forces are applied stops mattering once you move far enough away.
- The rule of thumb is that stresses "even out" within a distance roughly equal to the width or diameter of the member from the load application point. Closer than that, the real stress distribution can be highly non-uniform.
- Saint-Venant's principle is what licenses the assumption of uniform stress in $\sigma = F/A$ away from the grips of a tensile test specimen, and uniform bending stress variation in $\sigma = Mc/I$ away from the loading points of a beam.
- It does **not** apply at geometric discontinuities — holes, notches, fillets, abrupt cross-section changes. Those require [[Stress Concentrations]] analysis.

## Examples and Non-Examples

- **Tensile test specimen.** A dog-bone specimen gripped at its ends has a highly non-uniform stress distribution near the grips. At the mid-section (more than one diameter away from the grip), the stress is very nearly uniform and $\sigma = F/A$ is accurate. That is Saint-Venant's principle in action.

- **Beam with a patch load.** A beam carries load applied over a small contact patch (e.g., a wheel). Within roughly one beam depth of the contact zone, the stress field is complex. Beyond that distance, the [[Bending Moment Diagram]] and [[Bending Stress]] formula describe the field accurately.

- **Counter-example — a hole violates Saint-Venant.** Near a circular hole in a plate under tension, the stress rises sharply at the hole edges (a [[Stress Concentrations]] effect). Moving one hole-diameter away does *not* restore uniformity — the geometry itself causes a persistent perturbation that cannot be dismissed using this principle.

## Resources
- ![](https://www.youtube.com/watch?v=fM-FBEiGgLs)
- **[Encyclopaedia Britannica — Saint-Venant's Principle](https://www.britannica.com/science/Saint-Venants-principle)** — historical context and formal statement.
