---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **four-bar linkage** is the simplest useful closed-loop mechanism: four [[Link|links]] — ground, crank, coupler, and rocker — joined by four revolute pins, giving a [[Mobility]] of exactly one. Mechanisms are named by their total link count including ground, so "four-bar" means $n = 4$, and the [[Grübler–Kutzbach Equation]] confirms $M = 1$.

Notes:
- **The n-bar naming convention** counts *all* links, ground included:
    - **1-bar** — a single free link, $M = 3$ in the plane; not a usable mechanism.
    - **3-bar** — three links pinned in a closed triangle, $M = 0$; a rigid [[Mobility|structure]], not a mechanism.
    - **4-bar** — $M = 1$; the first closed chain that actually moves under a single input. The workhorse of linkage design.
- The four links have conventional roles: the **crank** rotates fully (driven by the motor), the **rocker** swings back and forth, the **coupler** connects them, and the **ground** is fixed. Whether a link can fully rotate is set by its length via Grashof's criterion (a later topic).
- Four-bars are everywhere because $M = 1$ is exactly what a single-motor machine wants: one input, one predictable output path. Getting more links does not automatically get more motion — joints remove [[Degrees of Freedom]] as fast as links add them.
- Analyze one by drawing its [[Linkage Diagram]] first, then counting joints for the [[Grübler–Kutzbach Equation]].

## Examples and Non-Examples
- **Windshield wiper.** Motor crank → coupler → wiper-arm rocker, with the car body as ground: $n = 4$, $j_1 = 4$, $M = 3(3) - 8 = 1$. One motor sweeps the blade through its arc.
- **Car hood hinge.** The two curved links that let a hood lift and clear its own edge form a four-bar with the body and the hood as two of the links — $M = 1$, so the hood follows one controlled path from closed to open.
- **Counter-example — the rigid triangle (3-bar).** Pin three links into a closed triangle and $M = 3(2) - 2(3) = 0$. It looks like a small linkage but cannot move; it is a structure. Adding the fourth link is exactly what buys the single degree of freedom.

## Resources
- ![](https://www.youtube.com/watch?v=nQq3iw3Sd_o)
- <iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/dynamics/four-bar-explorer.html" width="100%" height="450" style="border: none; border-radius: 8px;" loading="lazy" title="Interactive four-bar linkage explorer"></iframe>
- **[Norton, *Design of Machinery* — Ch. 2–3, The fourbar linkage](https://www.mheducation.com/)**

## Practice
- A robot gripper's finger is driven by a four-bar so the fingertip stays parallel as it closes. How many motors does it need, and which link does the motor drive?

> [!NOTE]- Answer
> A four-bar has $M = 1$, so it needs **one** motor. The motor drives the **crank**; the coupler carries the fingertip and the rocker completes the loop, so a single input closes the finger along its designed path.
