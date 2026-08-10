---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Mobility** ($M$) is the number of independent inputs a mechanism needs to have all of its motion defined — the [[Degrees of Freedom]] of the whole [[Link|linkage]] taken together. It is the number the [[Grübler–Kutzbach Equation]] returns, and reading its value tells you at a glance whether a machine moves, how many motors it takes, or whether it is locked.

Notes:
- **How to read the result:**
    - $M = 1$ — one input (one motor) fully controls the mechanism. The usual design target.
    - $M = 0$ — a **structure**: zero mobility, it cannot move. Correct for a bracket, wrong for a machine that is supposed to move.
    - $M < 0$ — **over-constrained** (statically indeterminate): more constraints than DOF, so some are redundant and the linkage may bind unless geometry is exact.
    - $M > 1$ — needs that many independent inputs; a two-DOF arm needs two motors.
- An **idle** or **redundant** degree of freedom is local motion that does not affect the output — for example a roller free to spin on its own pin. It inflates the raw [[Grübler–Kutzbach Equation]] count, so subtract idle DOF to get the *useful* mobility.
- Mobility is a property of the joint *topology*, not the exact link lengths — but see the paradox note below.
- Deciding how many actuators a design needs *is* reading mobility. This is the payoff of drawing the [[Linkage Diagram]] and counting joints.

## Examples and Non-Examples
- **One motor, one motion.** The [[Four-Bar Linkage]] returns $M = 1$: drive the crank and every other link's position follows. One servo, fully determined output.
- **A brace that locks the machine.** The bottle capper starts at $M = 1$. Adding an anti-chatter brace drives it to $M = 0$ — the "improvement" turns the mechanism into a structure and it stops moving. Mobility is what exposes the mistake before it is built.
- **Counter-example — the geometry paradox.** A parallelogram four-bar has $M = 1$ by the formula, but at the instant all four pins line up it gains a momentary extra freedom the count never predicted. The equation counts topology, not special proportions; unusual geometry can beat it, which is why $M$ is a first check, not the last word.

## Resources
- ![](https://www.youtube.com/watch?v=hBrHcHpMXmY)
- <iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/dynamics/grubler-mobility.html" width="100%" height="450" style="border: none; border-radius: 8px;" loading="lazy" title="Interactive mobility explorer"></iframe>
- **[Norton, *Design of Machinery* — Ch. 2, Paradoxes and mobility interpretation](https://www.mheducation.com/)**

## Practice
- A designer computes $M = -1$ for a linkage. What does that tell them, and what is one way to fix it if the linkage is meant to move with a single input?

> [!NOTE]- Answer
> $M = -1$ means the linkage is **over-constrained** — it has one redundant constraint and will generally not move (or will bind). To reach $M = 1$, remove a constraint: delete a redundant link, or convert a [[Full Joint and Half Joint|full joint]] into a half joint (e.g. replace a pinned member with a rolling contact) to give back the needed freedom.
