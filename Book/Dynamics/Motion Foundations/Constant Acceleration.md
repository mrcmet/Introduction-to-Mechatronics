---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Constant acceleration** is the special case of motion in which the [[Acceleration]] $a$ does not change over the time interval of interest. The condition $a = \text{const}$ — including the trivial case $a = 0$ — is what unlocks the algebraic [[Constant Acceleration Equations]] (the SUVAT relations) and lets you predict [[Velocity]] and [[Position]] without integrating a time-varying function.

Notes:
- "Constant" here means **constant in time**, not constant in space. Acceleration that depends on position (a spring) or on velocity (drag) is not constant even if its magnitude looks steady at a glance.
- The trivial case $a = 0$ counts as constant acceleration. Motion at constant [[Velocity]] is just constant acceleration with the constant set to zero, and the [[Constant Acceleration Equations]] still apply (they reduce to $x = x_0 + v_0 t$).
- The canonical real-world instance is **free fall** near Earth's surface: with air resistance neglected, every falling object has $a = -g \approx -9.81\ \text{m/s}^2$ relative to an upward [[Positive Direction]].
- Constant acceleration is an **assumption you make**, not a property the world hands you. Before reaching for SUVAT, check whether $a$ actually stays put over the interval — see the counter-examples below.
- Over a *short enough* window, almost any acceleration profile looks roughly constant. That's why splitting a complicated motion (a trapezoidal velocity profile, say) into piecewise-constant segments is such a common modelling move.
- The sign of $a$ does not change under constant acceleration, but it can still be negative — see [[Negative Acceleration]] for why "negative" and "decelerating" are not the same thing.
- For the algebraic consequences of this assumption — $v = v_0 + at$, $\Delta x = v_0 t + \tfrac{1}{2}at^2$, $v^2 = v_0^2 + 2a\,\Delta x$ — see [[Constant Acceleration Equations]].

## Equations

> [!equation] The defining condition
> $$a(t) = a = \text{const}$$
>
> - $a(t)$ — [[Instantaneous Acceleration]] along the chosen axis ($\text{m/s}^2$)
> - The right-hand side is a single number, fixed for the interval under consideration
> - When this holds, [[Average Acceleration]] and [[Instantaneous Acceleration]] are equal everywhere in the interval
> - See [[Constant Acceleration Equations]] for the integrated forms used to solve problems

## Examples and Non-Examples

- **Worked example — checking the assumption for free fall.** A wrench is dropped from a scaffold and falls for $t = 1.2\ \text{s}$ before being caught. Taking the [[Positive Direction]] as upward and neglecting air drag, the [[Acceleration]] of the wrench is $a = -g = -9.81\ \text{m/s}^2$ for *every* instant in that 1.2 s window. Because $a$ is the same at $t = 0$, at $t = 0.6\ \text{s}$, and at $t = 1.2\ \text{s}$, the constant-acceleration assumption holds and the [[Constant Acceleration Equations]] are valid. The velocity just before the catch is
$$v = v_0 + at = 0 + (-9.81)(1.2) \approx -11.8\ \text{m/s}$$
i.e. 11.8 m/s downward. Notice we only needed the assumption to be true; the equation itself lives on the [[Constant Acceleration Equations]] page.

- **Worked example — a coasting cart.** A cart on a level frictionless track is given a push and then released. After release, no net force acts on it, so by [[Newton's Second Law]] its acceleration is $a = 0$ — constant. This is still constant-acceleration motion, even though nothing is "accelerating" in the colloquial sense. The cart's [[Velocity]] is the unchanging $v = v_0$, and its [[Position]] grows linearly with time.

- **Counter-example — mass on a spring.** A block attached to a spring obeys $a = -(k/m)\,x$. The acceleration depends on [[Position]], so as $x$ changes the acceleration changes too. There is no single constant $a$ to plug in. The motion is governed by a second-order differential equation (simple harmonic motion), and the [[Constant Acceleration Equations]] do not apply over any interval longer than an instant.

- **Counter-example — trapezoidal motion profile.** A servo-driven linear stage executes a three-phase move: accelerate at $a_1 = +3\ \text{m/s}^2$ for 0.2 s, cruise at constant velocity ($a_2 = 0$) for 1.0 s, then brake at $a_3 = -2\ \text{m/s}^2$ for 0.3 s. *No single value of $a$* describes the whole motion — but each of the three phases is individually a constant-acceleration interval. The standard move is to apply the [[Constant Acceleration Equations]] to each phase separately and chain the end-of-phase state into the next phase as initial conditions.

- **Counter-example — falling with air resistance.** A skydiver in free fall has acceleration $a(v) = -g + (c/m)v^2$ (drag depends on speed). At the moment of jump $a \approx -g$, but as speed builds drag grows and $a$ trends toward zero (terminal velocity). The acceleration changes with time, so the constant-acceleration assumption breaks down — exactly the same fall is well-modelled as constant-$a$ for the first fraction of a second, and badly modelled as constant-$a$ for the full descent.

## Resources

- **[Khan Academy — One-dimensional motion](https://www.khanacademy.org/science/physics/one-dimensional-motion)** — channel-level entry point with worked examples on identifying constant-acceleration motion and on free fall.
- **[The Organic Chemistry Tutor channel](https://www.youtube.com/@TheOrganicChemistryTutor)** — large library of physics worked examples; search the channel for "constant acceleration" and "free fall" for matched problems.
- **[Wikipedia — Equations of motion](https://en.wikipedia.org/wiki/Equations_of_motion)** — reference on the constant-acceleration assumption and the integrated equations it enables.

## Practice

- A robotics lab drops a small steel ball from rest off the edge of a workbench of height $h = 0.85\ \text{m}$. Air resistance is negligible. Take the [[Positive Direction]] as downward. (a) State the value of the ball's acceleration at the instant of release, at the midpoint of the fall, and just before impact. (b) Is the constant-acceleration assumption valid here? Justify in one sentence. (c) For the same drop done in a wind tunnel where drag is significant, is the constant-acceleration assumption still valid? Why or why not?

> [!NOTE]- Answer
> **(a) Acceleration at each instant.**
> With drag neglected, the only force on the ball is gravity, so by [[Newton's Second Law]] the acceleration is $a = +g \approx +9.81\ \text{m/s}^2$ (downward, which is the chosen [[Positive Direction]]) at **every** instant of the fall — release, midpoint, and impact alike.
>
> **(b) Is constant-$a$ valid?**
> Yes. The acceleration takes the same value $a = +g$ throughout the interval, so $a$ is constant in time and the [[Constant Acceleration Equations]] apply. (As a sanity check: the impact speed comes out to $v = \sqrt{2g h} = \sqrt{2(9.81)(0.85)} \approx 4.08\ \text{m/s}$.)
>
> **(c) With significant drag?**
> No. Drag adds a velocity-dependent term to the net force, so the acceleration shrinks in magnitude as the ball speeds up: $a$ is no longer constant. You would need to integrate the equation of motion numerically (or, for that short a drop, model it as approximately constant only if drag is small relative to gravity at the speeds involved).
