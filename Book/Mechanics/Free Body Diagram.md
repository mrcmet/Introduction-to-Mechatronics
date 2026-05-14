---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> A **free body diagram** (FBD) is an isolated sketch of a body or segment that shows every external force and moment acting on it, with all physical supports replaced by their equivalent reaction forces. It is the starting point for applying equilibrium to find unknown forces and [[Support Reactions]].

Notes:
- The word "free" means the body is mentally cut loose from its surroundings. Every physical connection — supports, cables, contacts — is removed and replaced by a force arrow representing what that connection *does* to the body.
- **Steps for constructing an FBD:**
	  1. Choose your body (whole structure, a segment, or a single member).
	  2. Draw the body in isolation — no surroundings.
	  3. Identify and draw every external force: 
		  + Applied loads ([[Point Load and Distributed Load]]).
		  + Weight of the structure.
		  + Support reactions ([[Beam End Conditions]]).
	  4. Label magnitudes, directions, and points of application.
	  5. Set up equilibrium equations ($\sum F = 0$, $\sum M = 0$) to solve for unknowns.
- Include only *external* forces on the FBD. Internal forces between parts of the body cancel in pairs and do not appear — they only become visible when you cut the body and draw a new FBD of the cut segment (this is how [[Internal Forces in Beams]] are found).
- Sign convention matters: choose positive directions before writing equilibrium equations and stick to them.

## Examples and Non-Examples

- **Axially loaded rod.** A steel rod hangs from a ceiling and supports a weight $W = 500\ \text{N}$ at its lower end. The FBD shows the rod isolated with: the weight $W$ pulling downward at the bottom, and a tensile reaction force $R = 500\ \text{N}$ pulling upward at the ceiling attachment. Equilibrium: $\sum F_y = R - W = 0$ confirms $R = 500\ \text{N}$.

- **Simply supported beam.** A 4 m beam with a 10 kN point load at its center rests on a pin at the left end and a roller at the right. The FBD replaces the pin with a vertical reaction $A_y$ and a horizontal reaction $A_x$, and the roller with a vertical reaction $B_y$. Applying $\sum M_A = 0$ gives $B_y = 5\ \text{kN}$; $\sum F_y = 0$ then gives $A_y = 5\ \text{kN}$.

- **Counter-example — showing internal forces is not an FBD.** A sketch of a beam with stress arrows drawn *inside* the cross-section is a stress distribution diagram, not a free body diagram. An FBD only ever shows external forces on the boundary of the chosen body.

## Resources
![](https://youtu.be/52R61aSWHg0?si=aJtnpHYT5V0VRXJJ)

![](https://youtu.be/KgOqTB1MIKk?si=BGBEcfkVs62RZ7e9)

![](https://youtu.be/tL8akcL5eM0?si=ntjDS2_ZURKCUGZm)

 **[Wikipedia — Free Body Diagrams](https://en.wikipedia.org/wiki/Free_body_diagram)** .
