---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Speed** is the magnitude of [[Velocity]]. It is a non-negative scalar that tells you *how fast* a point is moving without saying *which way*. In one dimension, $s = |v|$; in two or three dimensions, $s = |\mathbf{v}|$.

Notes:
- Speed is a **scalar**, and it is **always non-negative**. A negative speed has no physical meaning — if you see one in your code or on a plot, you are looking at a signed velocity, not a speed.
- Speed carries **no direction information**. Two objects moving at $5\ \text{m/s}$ have the same speed whether one is heading north and the other south, or one is rising and the other falling.
- **Speed vs. [[Velocity]].** Velocity is the vector $\mathbf{v}$ that captures both rate and direction; speed is just its length. Stripping the direction is a one-way operation — you can get speed from velocity, but not the other way around.
- **Average speed vs. average velocity.** Average speed is [[Distance Traveled]] divided by elapsed time: $\bar{s} = d/\Delta t$. Average velocity uses [[Displacement]] over time instead. A round trip has zero average velocity but nonzero average speed — this is the cleanest way to see they are different quantities.
- **Instantaneous speed** is what a speedometer or a tachometer reads at a given instant: $s(t) = |v(t)|$. The sign of $v$ (which depends on the chosen [[Positive Direction]]) is discarded.
- Watch the everyday-English trap. Outside this course, "speed" and "velocity" are used interchangeably. Inside this course, and in any controller you write, the distinction matters — many controller bugs trace back to confusing $|v|$ with $v$.
- For rotating shafts the same idea applies: shaft speed is the magnitude of [[Angular Velocity]], typically reported as a positive number in rpm or rad/s regardless of rotation direction.

## Equations

> [!equation] Instantaneous speed from velocity
> $$s = |\mathbf{v}| \qquad \text{(1D: } s = |v|\text{)}$$
>
> - $s$ — speed, a non-negative scalar (m/s)
> - $\mathbf{v}$ — [[Velocity]] vector (m/s)
> - $v$ — signed scalar velocity along a chosen axis (m/s)

> [!equation] Average speed over a time interval
> $$\bar{s} = \frac{d}{\Delta t}$$
>
> - $\bar{s}$ — average speed (m/s)
> - $d$ — [[Distance Traveled]] along the path (m), always $\ge 0$
> - $\Delta t$ — elapsed time (s)
> - Note: this is **not** $|\Delta x|/\Delta t$ — that would be the magnitude of average velocity.

## Examples and Non-Examples

- **Worked example — conveyor belt linear speed.** A conveyor is driven by a motor through a pulley of radius $r = 40\ \text{mm}$. The pulley spins at $\omega = 25\ \text{rad/s}$. The linear speed of the belt surface is
$$s = r\,|\omega| = (0.040)(25) = 1.0\ \text{m/s}$$
Reversing the motor flips the sign of $\omega$ but the belt speed is still $1.0\ \text{m/s}$ — direction lives in the velocity, not the speed.

- **Tip speed of a motor shaft.** A coupling on a servo shaft has outer radius $r = 15\ \text{mm}$ and the shaft turns at $3000\ \text{rpm}$. Convert: $\omega = 3000 \cdot 2\pi/60 = 314\ \text{rad/s}$. The tip speed is
$$s = r\,|\omega| = (0.015)(314) \approx 4.7\ \text{m/s}$$
This is the kind of number you check against a "max surface speed" rating in a coupling or bearing datasheet.

- **Counter-example — same speed, different velocity.** Two AGVs cross an intersection. AGV-A heads east at $\mathbf{v}_A = [1.5, 0]^T\ \text{m/s}$, AGV-B heads north at $\mathbf{v}_B = [0, 1.5]^T\ \text{m/s}$. Both have speed $s = 1.5\ \text{m/s}$, but their velocities are different vectors. A collision-avoidance system that only knows speed cannot tell them apart — it needs the full [[Velocity]].

- **Counter-example — average speed ≠ |average velocity|.** A delivery robot drives 10 m east in 5 s, then 10 m back west in 5 s. Its [[Displacement]] is zero, so its average velocity is $0\ \text{m/s}$. But its [[Distance Traveled]] is 20 m over 10 s, giving an average *speed* of $2\ \text{m/s}$. The robot was clearly moving the whole time — average speed captures that, average velocity does not.

## Resources

- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)** — engineering-style intro videos on position, velocity, and the scalar/vector distinction.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples; search for "average speed vs average velocity" for the cleanest contrast.
- **[Wikipedia — Speed](https://en.wikipedia.org/wiki/Speed)** — concise reference for the scalar definition and the distinction from velocity.

## Practice

- A two-wheeled mobile robot has wheels of radius $r = 50\ \text{mm}$. Its left wheel spins at $\omega_L = +12\ \text{rad/s}$ and its right wheel spins at $\omega_R = -12\ \text{rad/s}$ (the robot is spinning in place). (a) What is the linear speed of the contact point at the bottom of each wheel relative to the wheel's axle? (b) Over a 4-second spin, the right contact point travels along its path a distance of... what? (c) Why is the *robot's* translational speed zero even though each wheel's contact point has nonzero speed?

> [!NOTE]- Answer
> **(a) Contact-point speed at each wheel.**
> $$s = r\,|\omega| = (0.050)(12) = 0.60\ \text{m/s}$$
> Same for both wheels — the *sign* of $\omega$ differs, but speed throws that away.
>
> **(b) Distance traveled by the right contact point.**
> $$d = s \cdot \Delta t = (0.60)(4) = 2.4\ \text{m}$$
> [[Distance Traveled]] is path length, so it accumulates regardless of which way the wheel is turning.
>
> **(c) Why the robot's translational speed is zero.**
> The robot's center is the average of two wheel velocities that are equal in magnitude and opposite in direction, so the *vector* sum gives a translational velocity of zero — and hence a translational speed of zero. The wheels still have plenty of surface speed; that energy is going into rotation, not translation. This is exactly why speed alone is not enough to describe motion: you have to look at the full [[Velocity]] vector of the body you care about.
