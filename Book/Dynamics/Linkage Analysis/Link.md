---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **link** is one rigid body in a mechanism — a member that does not bend or change length as the mechanism moves. Links are joined by [[Kinematic Pair|joints]] to form a chain, and the whole assembly is analyzed with a [[Linkage Diagram]]. The one link that is fixed to the reference frame is the **ground link**, and it still counts when you total the links for the [[Grübler–Kutzbach Equation]].

Notes:
- "Rigid" is an idealization: real links flex a little, but for [[Degrees of Freedom|mobility]] analysis we assume the link holds its shape so that only the joints allow motion. Link flexibility comes back later as a source of stress and deflection, not as extra DOF.
- Links are named by how many joints they carry: a **binary** link connects two joints, a **ternary** link three, a **quaternary** link four.
- The ground link (also called the **frame** or **fixed link**) is easy to forget because it is often the bench, wall, or machine base rather than a drawn bar. Miscounting it is the most common error in setting up the [[Grübler–Kutzbach Equation]] — if $n$ is off by one, the mobility is wrong.
- A single free rigid body — a link with no joints attached — is not yet part of a mechanism; it simply has the 3 planar [[Degrees of Freedom]] of any rigid body.

## Examples and Non-Examples
- **Windshield-wiper four-bar.** The wiper mechanism has four links: the motor crank, the connecting coupler, the wiper-arm rocker, and the car body itself as the **ground link**. Three moving bars plus one fixed frame gives $n = 4$, which is why it is a *four*-bar and not a three-bar. See [[Four-Bar Linkage]].
- **Ternary link in a capping head.** In the bottle-capping station, the follower arm carries three pin connections — input from the cam follower, and two to the capping four-bar. That single rigid piece is one *ternary* link even though three joints attach to it.
- **Counter-example — a coupler is not two links.** A connecting rod with a pin at each end is *one* binary link, not two. Beginners sometimes count each end as its own body; the rigid bar between the pins is a single link, and only the pins are joints.

## Resources
- ![](https://www.youtube.com/watch?v=nQq3iw3Sd_o)
- **[Norton, *Design of Machinery* — Ch. 2, Links, Joints, and Kinematic Chains](https://www.mheducation.com/)** — standard reference for link and joint terminology.

## Practice
- A slider-crank engine mechanism has a crank, a connecting rod, a piston, and the engine block. Which body is the ground link, and what is the total link count $n$ you would use in the [[Grübler–Kutzbach Equation]]?

> [!NOTE]- Answer
> The **engine block** is the ground link. Counting it along with the crank, connecting rod, and piston gives $n = 4$.
