---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Torque** ($T$) is the rotational equivalent of force — a moment that tends to twist a body about an axis rather than translate it. For a force $F$ applied at perpendicular distance $r$ from the axis of rotation: $T = F \cdot r$. Torque is the mechanical input that drives [[Torsional Shear Stress]] and [[Angle of Twist]] in shafts.

Notes:
- Units are newton-metres (N·m), the same as bending moment. The two are physically different:
	- torque acts about the *long* axis of a shaft.
	- bending moment acts about a *transverse* axis.
- In mechatronics, torque is delivered by motors and transmitted through shafts, gears, and couplings. 
	- A **gearbox** trades speed for torque: $T_{out} = T_{in} \times \text{gear ratio}$ (ignoring losses). The output shaft sees more torque and must be sized accordingly.
- **Power and torque** are related by rotational speed: 
	- $P = T\omega$, where $\omega$ is angular velocity in rad/s. In practical terms: $P = T \times 2\pi n / 60$, where $n$ is speed in RPM. 
	- A motor nameplate gives any two of $P$, $T$, $n$ — the third follows from this relation.
- Torque is a vector quantity (right-hand rule about the shaft axis), but in most shaft problems it is treated as a signed scalar: positive torque twists in one direction, negative in the other.
- The internal torque in a shaft at any cross-section is found by the same cut-and-isolate method used for [[Internal Forces in Beams]] — cut the shaft, isolate one segment, and sum moments about the shaft axis.

## Equations

> [!equation] Torque from a Force
> $$T = F \cdot r$$
>
> - $T$ — torque (N·m)
> - $F$ — applied force (N)
> - $r$ — perpendicular distance from the line of action to the axis of rotation (m)

> [!equation] Power–Torque–Speed Relationship
> $$P = T\omega = T \cdot \frac{2\pi n}{60}$$
>
> - $P$ — power (W)
> - $\omega$ — angular velocity (rad/s)
> - $n$ — rotational speed (RPM)

## Examples and Non-Examples

- **Wrench on a bolt.** A force of $F = 150\ \text{N}$ is applied at the end of a wrench $r = 250\ \text{mm}$ from the bolt center.
$$T = 150 \times 0.250 = 37.5\ \text{N·m}$$

- **Motor shaft.** A motor produces $P = 1.5\ \text{kW}$ at $n = 1{,}450\ \text{RPM}$.
$$T = \frac{P}{\omega} = \frac{1{,}500}{1{,}450 \times 2\pi / 60} = \frac{1{,}500}{151.8} \approx 9.9\ \text{N·m}$$
This is the torque the shaft must transmit — the starting point for sizing the shaft using [[Torsional Shear Stress]].

- **Gear ratio.** A motor outputs $T_{in} = 10\ \text{N·m}$ through a 5:1 gearbox. The output shaft carries:
$$T_{out} = 10 \times 5 = 50\ \text{N·m}$$
at one-fifth the input speed. The output shaft sees five times the torque and must be sized accordingly using [[Torsional Shear Stress]] and [[Angle of Twist]].

- **Counter-example — torque is not bending moment.** A simply supported shaft loaded transversely develops a bending moment and [[Bending Stress]] — not torque. Torque requires a moment about the *longitudinal* axis. Real motor shafts often carry both simultaneously — see [[Combined Loading]].

## Resources
- ![](https://youtu.be/T99yH_gw3p8?si=M8JjKpbY-oyilwem)
- ![](https://www.youtube.com/watch?v=oFXn6gOhwTM)
- **[Engineering Toolbox — Torque, Work and Power](https://www.engineeringtoolbox.com/work-torque-d_1377.html)** — torque–power–speed relationships with unit conversions and worked examples.

## Practice
- A servo motor outputs $P = 250\ \text{W}$ at $n = 3{,}000\ \text{RPM}$. (a) What torque does the output shaft carry? (b) If the motor is connected through a 4:1 reduction gearbox, what is the output torque and speed?

> [!NOTE]- Answer
> **(a) Shaft torque at motor output:**
> $$T = \frac{P}{2\pi n/60} = \frac{250}{2\pi \times 3{,}000/60} = \frac{250}{314.2} \approx 0.80\ \text{N·m}$$
>
> **(b) After gearbox:**
> $$T_{out} = 0.80 \times 4 = 3.18\ \text{N·m} \qquad n_{out} = 3{,}000 / 4 = 750\ \text{RPM}$$
