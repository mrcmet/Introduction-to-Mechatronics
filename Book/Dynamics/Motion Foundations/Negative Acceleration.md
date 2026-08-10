---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **negative acceleration** is an [[Acceleration]] whose signed scalar carries a minus sign — meaning the acceleration vector points opposite to the chosen [[Positive Direction]]. It is *not* a synonym for "slowing down": whether a body decelerates depends on how the sign of $a$ compares to the sign of [[Velocity]], not on the sign of $a$ alone. Deceleration occurs precisely when $a$ and $v$ have **opposite** signs, regardless of what either sign happens to be.

Notes:
- "Negative" is a **bookkeeping label**, set by the [[Positive Direction]] convention. A negative $a$ tells you the acceleration vector points in the $-x$ direction along the chosen axis — nothing more.
- The body **decelerates** when $a$ and $v$ have **opposite** signs. It **speeds up** when $a$ and $v$ have the **same** sign. Both rules hold regardless of whether $a$ itself is positive or negative.
- Equivalent restatement: a body slows down when the acceleration vector points *opposite* to the velocity vector; it speeds up when they point the *same* way. Sign is just the 1D shorthand for that vector comparison.
- The single most common student error in introductory dynamics is reading "$a < 0$" as "decelerating." It is wrong in exactly half the cases — specifically, when the body is already moving in the negative direction. See the worked examples below.
- Flipping the [[Positive Direction]] flips the sign of $a$, but the *physics* — whether the body is speeding up or slowing down — is invariant. The sign-vs-direction-of-motion rule above is convention-independent because both $a$ and $v$ flip together.
- In a motion profile (e.g. the trapezoidal velocity profile of a servo-driven axis), the [[Deceleration Phase]] is the segment where the controller applies an acceleration opposite to the current velocity. That phase often shows up as "negative $a$" on a plot only because positive $x$ was chosen to align with the motion — see [[Required Deceleration]] for sizing it.
- For [[Constant Acceleration]] problems, negative $a$ just substitutes a negative number into the SUVAT equations — nothing about the equations themselves changes. The interpretation of the result is what requires care.

## Examples and Non-Examples

- **Worked example A — negative $a$, decelerating.** A car travels in the $+x$ direction at $v_0 = +20\ \text{m/s}$ and brakes uniformly with $a = -2.0\ \text{m/s}^2$. Velocity is positive, acceleration is negative — *opposite signs*, so the car is **decelerating**. The speed shrinks: after $1\ \text{s}$, $v = +18\ \text{m/s}$; after $5\ \text{s}$, $v = +10\ \text{m/s}$; after $10\ \text{s}$, $v = 0$. The minus sign on $a$ here matches student intuition — but only because $v$ happens to be positive.

- **Worked example B — same negative $a$, speeding up.** Now a car travels in the $-x$ direction at $v_0 = -5.0\ \text{m/s}$ with the *same* acceleration $a = -2.0\ \text{m/s}^2$. Velocity is negative, acceleration is negative — *same signs*, so the car is **speeding up** in the negative direction. After $1\ \text{s}$, $v = -7.0\ \text{m/s}$; after $3\ \text{s}$, $v = -11\ \text{m/s}$. The speed (magnitude of velocity) is growing, not shrinking. Same number on $a$, opposite physical interpretation.

- **Worked example C — deceleration with *positive* $a$.** A robot rolls backward at $v_0 = -3.0\ \text{m/s}$ and the controller commands $a = +1.5\ \text{m/s}^2$. Velocity is negative, acceleration is positive — *opposite signs*, so the robot is **decelerating** even though $a > 0$. After $2\ \text{s}$, $v = 0$. This is the mirror image of Example A and is the clearest demonstration that "decelerating" and "negative acceleration" are independent statements.

- **Motion-profile sketch — the braking ramp.** In a trapezoidal velocity profile, a servo-driven axis accelerates from rest, cruises at $v_{\max}$, then enters the [[Deceleration Phase]] back to rest. If [[Positive Direction]] is aligned with the motion, the deceleration ramp has $a < 0$ — the textbook "negative acceleration." If the same physical move were analyzed with positive $x$ pointing the other way, the same ramp would show $a > 0$. The [[Required Deceleration]] needed to stop in a given distance depends only on magnitudes, not on the sign convention.

- **Counter-example — "negative acceleration means slowing down."** This is the canonical wrong statement. A two-wheeled balancer rolling at $v = -0.30\ \text{m/s}$ with a commanded $a = -1.0\ \text{m/s}^2$ is *speeding up*, not slowing down, because $a$ and $v$ share a sign. The sign of $a$ alone is never enough; you must compare it to the sign of $v$.

- **Counter-example — free fall on the way up vs. down.** A ball thrown upward with positive $y$ chosen as "up" has $a = -g \approx -9.81\ \text{m/s}^2$ throughout the flight — a [[Constant Acceleration]]. On the way up, $v > 0$ and $a < 0$: opposite signs, the ball decelerates. At the apex, $v = 0$, but $a$ is unchanged. On the way down, $v < 0$ and $a < 0$: same signs, the ball speeds up. *One* sign of acceleration, *two* different motion behaviours — driven entirely by what $v$ is doing.

## Resources

- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples; search the channel for "negative acceleration" and "deceleration" to see the sign-vs-direction-of-motion rule applied across several scenarios.
- **[The Organic Chemistry Tutor channel](https://www.youtube.com/@TheOrganicChemistryTutor)** — extensive 1D kinematics walkthroughs; useful for seeing many sign-convention problems worked side by side.
- **[Wikipedia — Acceleration](https://en.wikipedia.org/wiki/Acceleration)** — the "Tangential and centripetal acceleration" and sign-of-acceleration discussions reinforce the vector-comparison interpretation used here.

## Practice

- A linear actuator moves along its rail with positive $x$ defined toward the far end. At $t = 0$ its velocity is $v_0 = -0.40\ \text{m/s}$ and its acceleration is $a = -0.20\ \text{m/s}^2$, held constant. (a) Is the actuator speeding up or slowing down at $t = 0$? (b) What is its velocity at $t = 1.0\ \text{s}$? (c) Now repeat the question with everything physically the same but with positive $x$ redefined toward the home end — re-state $v_0$, $a$, and whether the actuator is speeding up or slowing down. (d) State the general rule in one sentence.

> [!NOTE]- Answer
> **(a) At $t = 0$.**
> $v_0 = -0.40\ \text{m/s}$ and $a = -0.20\ \text{m/s}^2$ — same sign. The actuator is **speeding up** in the negative direction, *not* slowing down. The minus sign on $a$ is misleading at first glance; what matters is that $a$ and $v$ agree in sign.
>
> **(b) Velocity at $t = 1.0\ \text{s}$.**
> Using [[Constant Acceleration]],
> $$v = v_0 + a\,t = -0.40 + (-0.20)(1.0) = -0.60\ \text{m/s}$$
> The speed (magnitude) grew from $0.40$ to $0.60\ \text{m/s}$ — confirming the actuator is speeding up.
>
> **(c) Flipped convention.**
> Redefining positive $x$ toward the home end flips the sign of every scalar along the axis: $v_0' = +0.40\ \text{m/s}$, $a' = +0.20\ \text{m/s}^2$. Both are now positive — same sign — so the actuator is still **speeding up**. Same physics, opposite signs, identical conclusion.
>
> **(d) Rule.**
> A body decelerates when $a$ and $v$ have **opposite** signs, and speeds up when they share a sign — independent of what either sign happens to be, and independent of the chosen [[Positive Direction]].
