---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **kinematic pair** is a joint — a connection between two [[Link|links]] that permits some relative motions and removes others. Each pair type takes away a specific number of [[Degrees of Freedom]], and totaling those removals is exactly what the [[Grübler–Kutzbach Equation]] does. Pairs are grouped as **lower pairs** (surface contact, one relative freedom) and **higher pairs** (line or point contact, two relative freedoms).

Notes:
- **Lower pair — one degree of freedom.** A [[Pin Joint|revolute]] joint allows only rotation; a [[Slider Joint|prismatic]] joint allows only sliding. In a planar mechanism each removes 2 of a link's 3 planar DOF, leaving 1. These are the **full joints** ($j_1$) in the [[Full Joint and Half Joint]] count.
- **Higher pair — two degrees of freedom.** A cam-on-follower or a gear-tooth contact allows *both* rolling and sliding at the contact. In the plane it removes only 1 DOF, leaving 2 — these are the **half joints** ($j_2$).
- The rule of thumb: contact over a *surface* (pin in a hole, block in a slot) is a lower pair; contact along a *line or point* (cam edge, gear teeth) is a higher pair.
- Getting the pair type right is not cosmetic — a joint classified as full instead of half changes the $2j_1 + j_2$ term and therefore the computed [[Mobility]].

## Examples and Non-Examples
- **Revolute (lower pair).** The pin connecting the wiper crank to its coupler lets the two links rotate relative to each other and nothing else — 1 DOF. In the [[Grübler–Kutzbach Equation]] it counts as one $j_1$.
- **Cam and follower (higher pair).** In the bottle-capping station, the cam pushes a follower along a curved edge. The follower can both roll and slide against the cam face, so the contact is a higher pair — one $j_2$ — which is why the capper's tally is $j_1 = 5,\ j_2 = 1$.
- **Counter-example — a weld is not a kinematic pair.** Rigidly fastening two links (a weld, a bolted flange with no play) permits *zero* relative motion. It does not create a joint; it simply merges the two members into one [[Link]]. A kinematic pair must allow some relative motion.

## Resources
- ![](https://www.youtube.com/watch?v=w5xh9CFRms0)
- **[Norton, *Design of Machinery* — Ch. 2, Joint types and pair classification](https://www.mheducation.com/)** — figures for lower vs. higher pairs.

## Practice
- A ball rolling inside a track and a shaft turning in a bushing are each joints. Classify each as a lower or higher pair, and state how many DOF it leaves.

> [!NOTE]- Answer
> The **shaft in a bushing** is a lower pair (surface contact) — a revolute joint leaving **1 DOF**. The **ball on a track**, contacting along a line/point and free to both roll and slide, is a higher pair leaving **2 DOF**.
