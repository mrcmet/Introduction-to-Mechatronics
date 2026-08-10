---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **Grübler–Kutzbach equation** counts the [[Mobility]] of a planar mechanism — how many independent inputs it needs — from just its link and joint tallies. Read the counts off the [[Linkage Diagram]], and the equation returns the number of [[Degrees of Freedom]] the whole mechanism has.

> [!equation] Grübler–Kutzbach (planar)
> $$M = 3(n - 1) - 2j_1 - j_2$$
>
> - $M$ — mobility, the number of independent inputs (DOF of the mechanism)
> - $n$ — total number of [[Link|links]], **including the ground link**
> - $j_1$ — number of [[Full Joint and Half Joint|full joints]] (revolute, prismatic — 1 DOF each)
> - $j_2$ — number of [[Full Joint and Half Joint|half joints]] (cam, gear — 2 DOF each)

Notes:
- **Where it comes from:** $n$ links each start with 3 planar DOF, but the fixed ground removes one link's worth, giving $3(n-1)$ free DOF. Every [[Kinematic Pair|full joint]] removes 2 and every half joint removes 1, so subtract $2j_1 + j_2$. What survives is the mobility.
- The most common mistake is miscounting $n$ — forgetting the [[Link|ground link]], or splitting one link into two. An error of one in $n$ shifts $M$ by 3.
- This is the *planar* form. Spatial mechanisms use the Kutzbach criterion with a factor of 6 instead of 3, because a rigid body in space has 6 DOF. The book stays planar for now.
- The equation counts DOF but does not check geometry. Special proportions can give a mechanism more motion than the formula predicts — see the [[Mobility]] page for these paradox cases.

## Examples and Non-Examples
- **Four-bar linkage.** $n = 4$, $j_1 = 4$, $j_2 = 0$: $M = 3(4-1) - 2(4) - 0 = 9 - 8 = 1$. One input fully drives it — the defining property of a [[Four-Bar Linkage]].
- **Bottle-capping station.** $n = 5$, $j_1 = 5$, $j_2 = 1$: $M = 3(4) - 10 - 1 = 1$. One servo runs the whole capper. Add a well-meant anti-chatter brace (one binary link, two pins → $n = 6$, $j_1 = 7$): $M = 3(5) - 14 - 1 = 0$ — the brace *locks* the machine.
- **Counter-example — a rigid triangle.** Three links pinned in a closed triangle: $n = 3$, $j_1 = 3$: $M = 3(2) - 6 = 0$. Zero mobility means it is a structure, not a mechanism — it cannot move no matter how you push it.

## Resources
- ![](https://www.youtube.com/watch?v=hBrHcHpMXmY)
- <iframe src="https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/dynamics/grubler-mobility.html" width="100%" height="450" style="border: none; border-radius: 8px;" loading="lazy" title="Interactive Grübler–Kutzbach mobility calculator"></iframe>
- **[Norton, *Design of Machinery* — Ch. 2, Kutzbach's mobility criterion](https://www.mheducation.com/)** — derivation and worked examples.

## Practice
- A five-bar linkage has five links in an open loop joined by five revolute pins ($n = 5$, $j_1 = 5$, $j_2 = 0$). Compute $M$ and say how many motors it needs.

> [!NOTE]- Answer
> $M = 3(5-1) - 2(5) - 0 = 12 - 10 = 2$. Mobility 2 means it needs **two** independent inputs (two motors) to control fully — see [[Mobility]].
