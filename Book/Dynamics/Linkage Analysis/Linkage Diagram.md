---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **linkage diagram** (kinematic skeleton) is a stripped-down stick figure of a mechanism that keeps only what governs motion: each [[Link|link]] drawn as a line or shape, and each [[Kinematic Pair|joint]] drawn with its standard symbol. Shape, mass, and material are discarded. It is the drawing you count links and joints on to apply the [[Grübler–Kutzbach Equation]] and find the [[Mobility]], and the drawing you later hang forces on to build a [[Free Body Diagram]].

> [!note] Not the same as the "Kinematic Diagram" page
> In this book, [[Kinematic Diagrams]] refers to the *acceleration/velocity sketch* drawn next to an FBD in a dynamics problem — a different object. This page is about the **mechanism skeleton**: links and joints, no forces, no accelerations.

Notes:
- **How to draw one:** (1) identify the [[Link|ground link]] and mark it fixed; (2) draw each remaining link as a bar; (3) place a joint symbol at every connection — an open circle for a [[Pin Joint|revolute]], a block-in-slot for a [[Slider Joint|prismatic]], a rolling-contact symbol for a higher pair; (4) label the input link (the one a motor drives).
- The skeleton throws away geometry that does not affect the *type* of motion. A curved bracket and a straight bar that connect the same two pins are the same link on the diagram.
- The linkage diagram is step one of the course spine: **motion → force → stress → deflection**. You cannot draw the [[Free Body Diagram]] of a mechanism correctly until you have its skeleton, because the skeleton tells you where the [[Kinematic Constraint|joint reactions]] act.
- Count links and joints directly off the finished skeleton — this is what makes the [[Mobility]] calculation repeatable instead of a guess.

## Examples and Non-Examples
- **Bottle-capping station.** The real machine (servo, cam, follower arm, capping head) reduces to a five-link skeleton: ground, crank, coupler, rocker, and follower. Reading straight off the diagram gives $n = 5$, $j_1 = 5$, $j_2 = 1$, hence $M = 3(5-1) - 2(5) - 1 = 1$ — one motor drives it.
- **Wiper mechanism.** The windshield wiper's motor-crank-coupler-arm assembly collapses to the classic [[Four-Bar Linkage]] skeleton once the sheet metal is stripped away, exposing the single ground pivot and single moving output.
- **Counter-example — a scale drawing is not a linkage diagram.** A dimensioned CAD side-view that shows fillets, bosses, and material is a *machine drawing*, not a kinematic skeleton. It carries far more than motion analysis needs; the skeleton is the abstraction you extract *from* it.

## Resources
- ![](https://www.youtube.com/watch?v=i2D1CxJqMpY)
- **[Norton, *Design of Machinery* — Ch. 2, Kinematic diagrams / skeletons](https://www.mheducation.com/)** — symbol conventions for links and joints.

## Practice
- Sketch the linkage diagram of a desk lamp arm (two parallel-bar sections and a base clamp). Identify the ground link and count $n$ and $j_1$.

> [!NOTE]- Answer
> The **base clamp** is the ground link. A simple two-bar articulated arm modeled as a four-bar parallelogram gives $n = 4$ and $j_1 = 4$ revolute pins, so $M = 1$ — the lamp head follows one input motion, which is why it holds any position you set.
