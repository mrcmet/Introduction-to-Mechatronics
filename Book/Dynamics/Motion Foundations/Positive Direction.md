---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **positive direction** is the direction along a [[Coordinate Axis]] that the analyst chooses to call "positive" before writing any kinematic or dynamic equation. Once fixed, every signed scalar along that axis — [[Position]], [[Displacement]], [[Velocity]], [[Acceleration]], and the components of forces — is measured relative to it. The choice is a [[Reference Frame]] convention, not a physical fact about the system.

Notes:
- Choosing a positive direction is a **decision you make**, not a property of the world. Two analysts using opposite conventions for the same problem will get scalars with opposite signs and identical physics.
- Once chosen, **stick with it for the entire problem**. A vector that points along positive gets a $+$ sign on its scalar component; one that points the other way gets a $-$ sign. Mixing conventions partway through is the single most common source of sign errors in dynamics homework.
- A negative [[Velocity]] or [[Acceleration]] does **not** mean "slowing down" or "wrong." It means "pointing opposite to the chosen positive direction." See [[Negative Acceleration]] for why a deceleration can be either positive or negative depending on the convention.
- Pick the convention that makes the math cleanest: align positive $x$ with the expected direction of motion, with gravity, or with the sensor's reported direction. The physics doesn't care, but your sanity does.
- For multi-axis problems, every axis of the [[Reference Frame]] needs its own positive direction, and the chosen set should form a consistent right-handed frame for 3D work.
- The positive direction lives with the axis, not with the object. A robot moving in $-x$ still has positive $x$ pointing the same way it always did; only the *sign* of the robot's velocity is negative.

## Examples and Non-Examples

- **Gantry move — convention A.** A linear gantry travels from $x_i = 0.20\ \text{m}$ to $x_f = 0.85\ \text{m}$ in 1.3 s, with positive $x$ defined as "toward the far end of the rail." The [[Displacement]] is $\Delta x = +0.65\ \text{m}$, the average [[Velocity]] is $\bar v = +0.50\ \text{m/s}$, and if the head was speeding up from rest, the [[Acceleration]] is positive. All three quantities being $+$ tells the controller "this motion runs in the chosen positive direction."

- **Gantry move — convention B (same motion, flipped axis).** Repeat the same physical move, but redefine positive $x$ as "toward the home end of the rail." The starting position is now $x_i' = -0.20\ \text{m}$ and the final position $x_f' = -0.85\ \text{m}$. The displacement becomes $\Delta x' = -0.65\ \text{m}$ and the average velocity $\bar v' = -0.50\ \text{m/s}$. **The robot did not change what it did — only the bookkeeping flipped.** Magnitudes (0.65 m, 0.50 m/s) are convention-independent; signs are not.

- **Free-body diagram.** When you draw a free-body diagram and sum forces, every force vector is projected onto the positive direction. Gravity on a block sitting on a table contributes $-mg$ if positive $y$ points up, and $+mg$ if positive $y$ points down — same gravity, same block, different convention.

- **Counter-example — mixing conventions mid-problem.** A robot decelerating from $v_1 = +5\ \text{m/s}$ to $v_2 = 0$ along $+x$ has $a = -2.5\ \text{m/s}^2$ if it took 2 s — the [[Acceleration]] is negative because the change in velocity points in $-x$. A student who then writes "$a = +2.5\ \text{m/s}^2$ because it's decelerating" has silently switched conventions: they used $+x$ for velocity and "direction of slowing" for acceleration. The numbers in any later step (force, distance traveled, time-to-stop) will be wrong. **Pick one convention per axis and use it everywhere.**

- **Counter-example — symmetric case with opposite sign.** The *same* magnitude of deceleration from $v_1 = -5\ \text{m/s}$ to $v_2 = 0$ along the *same* $+x$ axis gives $a = +2.5\ \text{m/s}^2$. Same physical "slowing down," opposite sign. Sign is set by the convention, not by whether the object is speeding up or slowing down.

## Resources

- **[CPPMechEngTutorials — Engineering Dynamics playlist](https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX)** — engineering-mechanics worked examples that consistently set up a positive direction before applying Newton's second law; watch any introductory video to see the convention picked, drawn on the FBD, and used end-to-end.
- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — search the channel for "coordinate system" or "free-body diagram" to see the convention-first workflow.
- **[Wikipedia — Sign convention](https://en.wikipedia.org/wiki/Sign_convention)** — short reference on how arbitrary sign choices propagate through physics and engineering equations.

## Practice

- A mobile robot moves along a straight track. With positive $x$ chosen as "east," the robot's velocity at $t = 0$ is $v_0 = +3\ \text{m/s}$ and at $t = 4\ \text{s}$ it is $v_1 = -1\ \text{m/s}$. (a) What is the robot's average acceleration over those 4 s, with sign? (b) Re-solve the same physical problem with positive $x$ redefined as "west." (c) Does the robot speed up, slow down, or both during this interval?

> [!NOTE]- Answer
> **(a) Positive $x$ = east.**
> $$\bar a = \frac{v_1 - v_0}{\Delta t} = \frac{-1 - (+3)}{4} = \frac{-4}{4} = -1\ \text{m/s}^2$$
> The acceleration points west (negative $x$).
>
> **(b) Positive $x$ = west.**
> Flipping the axis flips the sign of every scalar. Now $v_0' = -3\ \text{m/s}$ and $v_1' = +1\ \text{m/s}$, so
> $$\bar a' = \frac{+1 - (-3)}{4} = +1\ \text{m/s}^2$$
> Same physical acceleration, opposite sign. The acceleration still points west — but west is now the positive direction.
>
> **(c) Speeding up or slowing down?**
> The robot is moving east at 3 m/s, decelerates to 0, then moves west at 1 m/s. It slows down for part of the interval and speeds up (in the opposite direction) for the rest. Notice that the sign of $\bar a$ alone does **not** tell you "slowing down" — in part (a) the negative $\bar a$ described both phases at once. This is exactly why "negative acceleration ≠ deceleration."
