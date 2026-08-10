---
tags: [mechanics, pre-release]
---
#mechanics #pre-release

## Definition
> [!definition]
> A **joint reaction force** is the internal force transmitted through a [[Kinematic Pair|joint]] between two connected [[Link|links]]. You find it by isolating one link on a [[Free Body Diagram]] and applying [[Static Equilibrium]]; by [[Newton's Third Law]], the force each link exerts on the other through the pin is equal and opposite. Sizing these forces is the "force" step of the course spine — **motion → force → stress → deflection** — and sets the load a pin or bearing must survive.

Notes:
- A **revolute pin** transmits force in two components ($R_x$, $R_y$) but **no moment** — it is free to rotate, so it cannot resist twist. A **prismatic (slider)** joint transmits force *normal* to the sliding direction only, since it offers no resistance along the slot.
- **Contrast with [[Support Reactions]].** Support reactions are the *external* forces a fixed support (a wall, a bearing to ground) applies to a structure. A joint reaction is the *internal* force between two *moving* links of a mechanism. Same equilibrium math, different role in the machine.
- The pin reaction is the vector sum of everything the joint must transmit. For a [[Static Equilibrium|two-force member]] such as a coupler, the pin simply carries the member's axial force; where several forces meet at one pin, add them as vectors.
- Once you know the joint reaction, the pin is sized against [[Direct Shear Stress]] (single or double shear) and the link against [[Bending Stress]] — this is the handoff from dynamics/statics into machine design.

## Examples and Non-Examples
- **Two-force coupler into a pin.** A coupler is a two-force member carrying an axial compressive force $F = 120\ \text{N}$ inclined at $\theta = 30°$. At the pin it transmits $R_x = F\cos30° = 103.9\ \text{N}$ and $R_y = F\sin30° = 60.0\ \text{N}$, so the pin reaction is $R = \sqrt{103.9^2 + 60.0^2} = 120\ \text{N}$ — equal to the coupler force, as expected when a single axial load passes through.
- **Bottle-capping station (Lecture 3).** Isolating the capping four-bar's coupler gave a coupler force $F_c = 64\ \text{N}$; carrying that plus the follower load through the shared pin, static equilibrium sized the pin reaction at $R = 104\ \text{N}$ — the number a designer would take to pin-shear sizing.
- **Counter-example — expecting a moment at a pin.** Treating a revolute pin as if it carried a resisting moment (like a welded or fixed joint) over-stiffens the model and hides the real load path. A pin reacts forces only; if the joint truly resists moment, it is not a revolute [[Kinematic Pair]].

## Resources
- ![](https://www.youtube.com/watch?v=i2D1CxJqMpY)
- **[Hibbeler, *Engineering Mechanics: Statics* — Equilibrium of frames and machines](https://www.pearson.com/)**

## Practice
- A pin connects two links. Link 1 pushes on the pin with a force of $64\ \text{N}$ directed at $40°$ above horizontal; no other force acts at the pin. What are the horizontal and vertical components of the joint reaction, and how much force must the pin be sized for?

> [!NOTE]- Answer
> $R_x = 64\cos40° = 49.0\ \text{N}$, $R_y = 64\sin40° = 41.1\ \text{N}$. With a single load passing through, the pin reaction magnitude equals that load: $R = 64\ \text{N}$, so size the pin (in shear) for $64\ \text{N}$.
