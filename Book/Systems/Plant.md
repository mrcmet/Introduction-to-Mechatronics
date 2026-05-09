#Systems #Definition

# Definition
---

> [!definition]
> In systems and controls, a plant is the part of the system that does the work: it takes an input (a command or stimulus) and produces an output (the response you care about). The plant is the physical process you’re trying to model and (often) control—everything from “a pendulum” to “an oven” to “a vehicle drivetrain.”   

In [[Block Diagrams|block-diagram]] terms, we often treat the plant as a black box described by a model (commonly a [[Transfer Function]] $G(s))$ that maps input $\rightarrow$ output, while keeping the controller and sensors as separate blocks.   
  

# Key Ideas:
 ---
  
- Plant ≠ controller: the controller decides what to do; the plant is what happens in the real world when you do it.  
<br>
- A plant is typically described using inputs $u(t)$, outputs $y(t)$, and disturbances $d(t)$ .  
<br>
- Plants can be simple (single mass–spring) or messy (cars, aircraft, ovens).  
<br>
- In many controls texts, “plant” may implicitly include the actuator + process together (because both shape the input→output behavior).  

# Examples:

---

> [!example]
> **Plant example:** A spring mass system with force as an input and position as an output
> 
**Physical setup:** A mass m attached to a spring with stiffness k on a frictionless surface.
**Input:** applied force u(t) (N)
**Output:** displacement y(t)=x(t) (m)
&nbsp;
**1) Differential equation (the plant model)**
From Newton’s 2nd law:
$$m\ddot{x}(t) = u(t) - kx(t)$$
Rearrange into standard form:
$$m\ddot{x}(t) + kx(t) = u(t)$$
&nbsp;
   **2) Transfer function** $G(s)$
Take the Laplace transform assuming zero initial conditions:
$$ms^2X(s) + kX(s) = U(s)$$
Factor $X(s)$:
$$X(s)\left(ms^2 + k\right) = U(s)$$
So the transfer function from force to position is:
$$G(s) = \frac{X(s)}{U(s)} = \frac{1}{ms^2 + k}$$
This is a **second-order plant**.


> [!example]
> **Plant example:** an oven (temperature control)
> 
**Goal:** command oven temperature.
**Input:** $u(t)$: heater power (often via voltage or PWM duty cycle).
**Output:** $y(t)$: oven air (or wall) temperature $T(t)$.
**Disturbances:** $d(t)$: room temperature changes, opening the door, adding cold food, airflow leaks.
>
A very common “good enough” model is first-order thermal dynamics (lumped capacitance + thermal resistance):
>$$ C_{th}\,\frac{dT}{dt} = P_{in}(t) - \frac{T(t)-T_{ամբ}}{R_{th}}$$
where $C_{th}$ is thermal capacitance (how much heat it “stores”) and $R_{th}$ is thermal resistance (how hard it is to leak heat to ambient). This gives a time constant
>$$ \tau = R_{th}C_{th} $$
and for temperature rise above ambient an input→output transfer function form:
>$$ \frac{\Delta T(s)}{P_{in}(s)}=\frac{R_{th}}{1+\tau s}$$
That’s the plant model your controller “talks to,” even though the real oven has extra complexity (fan convection, radiation, multi-zone heating, etc.). 
>
Practical note: the oven is a nice teaching plant because it’s intuitive, strongly affected by disturbances, and naturally illustrates why closed-loop control exists (setpoint vs measured temperature, noise vs disturbance).  

  
# Resources
---

- Course source (terminology: input/plant/output):  
- Course source (plant + disturbances explanation):  
- Plant (control theory) overview:  
- MIT OCW (plant as the system inputs act through):  
- Oven/heater thermal plant modeling example: