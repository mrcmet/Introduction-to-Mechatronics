---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **full joint** ($j_1$) is a [[Kinematic Pair|joint]] that leaves **one** degree of relative freedom between two [[Link|links]] — a revolute or prismatic pair. A **half joint** ($j_2$) leaves **two** — a cam or gear contact. The names come from how much freedom each removes in the plane, and they are the two joint tallies fed into the [[Grübler–Kutzbach Equation]].

Notes:
- In a plane, a free link has 3 [[Degrees of Freedom]]. A **full joint** removes 2 (leaving 1), so it contributes $-2$ per joint. A **half joint** removes only 1 (leaving 2), contributing $-1$ per joint. That is precisely why the equation weights them as $-2j_1 - j_2$.
- "Full" and "half" refer to *how much of a full constraint they apply*, not to their physical size. A tiny pin is a full joint; a large rolling cam contact is a half joint.
- Every [[Pin Joint|revolute]] and [[Slider Joint|prismatic]] joint is a full joint; every cam-follower and meshing-gear contact is a half joint. If you can name the pair, you can name its $j$ category.
- Count carefully at multi-joint links: a pin shared by three links is *two* full joints, not one, because it makes two independent link-to-link connections.

## Examples and Non-Examples
- **Full joints in a four-bar.** The [[Four-Bar Linkage]] has four revolute pins and no cam contacts, so $j_1 = 4$ and $j_2 = 0$. Mobility is $M = 3(4-1) - 2(4) - 0 = 1$.
- **Mixed count in the capping station.** The bottle capper has five pin/slider connections and one cam contact: $j_1 = 5$, $j_2 = 1$. The half joint is what separates its tally from a purely revolute chain, and it feeds the $M = 3(5-1) - 2(5) - 1 = 1$ result.
- **Counter-example — treating a cam as a full joint.** If you wrongly log the capper's cam contact as a full joint ($j_1 = 6,\ j_2 = 0$), the equation gives $M = 3(4) - 12 = 0$ — you would predict a locked machine that in reality moves. Misclassifying one half joint flips the design conclusion.

## Resources
- ![](https://www.youtube.com/watch?v=w5xh9CFRms0)
- **[Norton, *Design of Machinery* — Ch. 2, Determining degrees of freedom](https://www.mheducation.com/)** — worked $j_1$/$j_2$ tallies.

## Practice
- A mechanism has three revolute pins, one slider, and one gear-mesh contact. What are $j_1$ and $j_2$?

> [!NOTE]- Answer
> Revolute pins and the slider are all full joints: $j_1 = 3 + 1 = 4$. The gear mesh is a half joint: $j_2 = 1$.
