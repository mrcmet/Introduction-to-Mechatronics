---
tags:
  - mechanics
  - materials
---
#mechanics #materials

## Definition
> [!definition]
> **Ultimate tensile strength** ($\sigma_u$, also called UTS) is the maximum [[axial stress]] reached on a material's [[stress-strain curve]] — the highest load per unit original area the material can sustain before **necking** begins. Beyond $\sigma_u$, the cross-section constricts locally and the part fractures shortly after.

Notes:
- $\sigma_u$ is always greater than [[yield strength]] $\sigma_y$. The gap between them reflects how much the material strain-hardens in the plastic region. 
	- For low-ductility materials, the gap is small. 
	- For highly ductile materials (annealed copper, mild steel), $\sigma_u$ can be 50–100% above $\sigma_y$.
- UTS is an *engineering* stress value — it uses the original cross-sectional area. After necking, the true stress at the neck is actually higher than $\sigma_u$, but the load carried by the coupon has dropped.
- For *elastic* design, [[yield strength]] is the governing limit. UTS governs when you need to know the absolute load at fracture — relevant for failure analysis, safety-critical rupture limits, and some fastener ratings.
- Brittle materials (cast iron, glass, ceramics) fracture near the proportional limit with essentially no plastic region. For these, $\sigma_u \approx \sigma_y$ and the distinction is academic.

## Examples and Non-Examples
- **Steel design margin.** Structural steel A36 has $\sigma_y = 250\ \text{MPa}$ and $\sigma_u = 400\ \text{MPa}$. A design using $\sigma_y$ as the limit has a further $150\ \text{MPa}$ of reserve before fracture — useful to know, but not the design criterion in normal elastic service.

- **Bolt proof load.** A Grade 8 steel bolt is rated by its proof load (a stress near $\sigma_y$) and its UTS separately. The bolt is designed to be torqued below proof load in service; UTS tells you how far past that you can go before the bolt snaps.

- **Counter-example — UTS is not the design stress.** A designer who sizes a structural bracket to $\sigma_u$ rather than $\sigma_y$ will have a part that deforms permanently under normal load — it won't return to shape when the load is removed. UTS is a fracture limit, not a service limit.

## Resources
- ![](https://www.youtube.com/watch?v=67fSwIjYJ-E)
- **[Engineering Toolbox — Tensile Strength](https://www.engineeringtoolbox.com/tensile-strength-d_945.html)** — material tables with $\sigma_y$ and $\sigma_u$ side by side.

## Practice
- A 304 stainless steel rod has $\sigma_y = 215\ \text{MPa}$ and $\sigma_u = 505\ \text{MPa}$. A designer applies a safety factor of 2 against yielding. What is the allowable stress? How does it compare to $\sigma_u$?

> [!NOTE]- Answer
> Allowable stress $= \sigma_y / n = 215 / 2 = 107.5\ \text{MPa}$.  
> That is well below $\sigma_u = 505\ \text{MPa}$ — the part has a large margin against fracture even at the design limit.
