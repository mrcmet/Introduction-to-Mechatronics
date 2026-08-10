---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Units** are standardized quantities used to express physical measurements. **Dimensional analysis** is the technique of tracking the units — called *dimensions* — through every step of a calculation to verify that an equation is physically consistent, catch errors, and perform conversions. An equation in which the dimensions on both sides do not match is always wrong. An equation that is dimensionally consistent may or may not be correct, but it has passed the first check.

Notes:
- The SI system (International System of Units) is used throughout this book. The seven SI base units that appear in dynamics are: meter (m), kilogram (kg), second (s), kelvin (K), and ampere (A). Everything else is derived.
- Common derived units in dynamics:

| Quantity | SI Unit | Symbol | In base units |
|---|---|---|---|
| Force | newton | N | kg·m/s² |
| Energy / Work | joule | J | kg·m²/s² |
| Power | watt | W | kg·m²/s³ |
| Pressure / Stress | pascal | Pa | kg/(m·s²) |
| Angular velocity | radian per second | rad/s | s⁻¹ |
| Torque | newton-meter | N·m | kg·m²/s² |

- Radians are dimensionless — they are a ratio of arc length to radius, both in meters. This means rad/s and s⁻¹ are the same dimension, but writing "rad/s" communicates intent.
- Dimensional homogeneity: every term added or subtracted in an equation must have the same dimensions. You cannot add meters to seconds. This rule catches many algebra errors before plugging in numbers.
- When performing a calculation, carry units symbolically through each step. Cancel units the same way you cancel variables. The remaining unit should match the expected unit of the answer.
- The technique generalizes beyond checking: it can derive the form of an equation from known physical relationships (the Buckingham π theorem, used in fluid mechanics and control scaling). At this level, use it primarily for checking and converting.
- In robotics and mechatronics, unit mismatches between subsystems are a real source of bugs — e.g., mixing degrees and radians in joint angle commands, or passing a value in millimeters where a function expects meters.

## Examples and Non-Examples

- **Checking the kinematic equation.** Verify that $v^2 = v_0^2 + 2a\Delta x$ is dimensionally consistent:
$$\left[\frac{\text{m}}{\text{s}}\right]^2 = \left[\frac{\text{m}}{\text{s}}\right]^2 + \left[\frac{\text{m}}{\text{s}^2}\right][\text{m}] = \frac{\text{m}^2}{\text{s}^2} + \frac{\text{m}^2}{\text{s}^2} \checkmark$$
Every term has dimensions m²/s². The equation passes the dimensional check.

- **Checking Newton's Second Law.** $F = ma$:
$$[\text{N}] = [\text{kg}]\left[\frac{\text{m}}{\text{s}^2}\right] = \frac{\text{kg}\cdot\text{m}}{\text{s}^2}$$
This is exactly the definition of the newton — so the equation is dimensionally self-consistent, as expected.

- **Unit conversion — angular velocity.** A servo encoder reports $1800\ \text{RPM}$ (revolutions per minute). Convert to rad/s for use in dynamics equations:
$$1800\ \frac{\text{rev}}{\text{min}} \times \frac{2\pi\ \text{rad}}{1\ \text{rev}} \times \frac{1\ \text{min}}{60\ \text{s}} = 60\pi \approx 188.5\ \text{rad/s}$$

- **Counter-example — dimensionally correct but physically wrong.** Dimensional analysis cannot catch an error in a numerical coefficient. The equation $v = 2v_0 + at$ is dimensionally correct but physically wrong (the coefficient 2 should not be there). Dimensional analysis is a necessary check, not a sufficient proof of correctness.

- **Counter-example — degrees vs. radians in code.** A robot controller expects joint angles in radians but receives sensor data in degrees. The trigonometric functions produce wrong outputs, and the arm moves to the wrong position. The code compiles and the units are both "angle" — dimensional analysis at the type-system level would not catch this. Always document and verify angular unit conventions explicitly.

## Resources

![](https://www.youtube.com/watch?v=hQpQ0hxVNTg)

![](https://www.youtube.com/watch?v=yGWQjbpS1kM)

**[NIST — The International System of Units (SI)](https://www.nist.gov/pml/owm/metric-si/si-units)**

## Practice

- A hydraulic actuator exerts a force of $F = 850\ \text{N}$ over a piston area of $A = 12\ \text{cm}^2$. What is the pressure in pascals? First convert the area to m², then apply $P = F/A$, and check that the result has units of Pa.

> [!NOTE]- Answer
> **Convert area.**
> $$A = 12\ \text{cm}^2 \times \left(\frac{1\ \text{m}}{100\ \text{cm}}\right)^2 = 12 \times 10^{-4}\ \text{m}^2 = 1.2 \times 10^{-3}\ \text{m}^2$$
>
> **Compute pressure.**
> $$P = \frac{F}{A} = \frac{850\ \text{N}}{1.2 \times 10^{-3}\ \text{m}^2} \approx 7.08 \times 10^5\ \text{Pa} = 708\ \text{kPa}$$
>
> **Dimensional check.**
> $$\frac{[\text{N}]}{[\text{m}^2]} = \frac{[\text{kg}\cdot\text{m/s}^2]}{[\text{m}^2]} = \frac{\text{kg}}{\text{m}\cdot\text{s}^2} = [\text{Pa}] \checkmark$$
