#Definition #Systems 

# Definition
---

> [!Definition]
> **System block diagrams** are simplified visual models that show how signals flow through a [[Systems|system]] by connecting functional elements (“blocks”). Each block represents a relationship between an input and an output (often a _transfer function_), and the connections show how signals are combined, split, and fed back to achieve a desired behavior. In this course context, block diagrams are the fast way to communicate **plant–input–output** structure and (when present) **feedback** interactions, including where disturbances and sensor noise enter the system.   

  

# Key Ideas:
---
- **Signal line (arrow):** Direction of information flow (the variable could be voltage, speed, position, etc.). 
    <br>
- **Block (rectangle):** A subsystem that maps input to output; in controls we often label it with a transfer function like $G(s)$ or a gain K. 
    <br>
- **Summing junction (Σ / circle):** Algebraically adds/subtracts signals. The signs on the incoming arrows define “+” or “−”. 
    <br>
- **Takeoff / pickoff point (branch node):** Copies a signal to multiple paths **without changing it** (an ideal “signal splitter”). 
    <br>
- **Gain** K**:** A constant scalar block: y = Kx. Common in actuator scaling, sensor scaling, or simplified modeling. 
    <br>
- **[[Transfer Function]]** $G(s)$**:** A compact input–output model in the Laplace domain; blocks can be composed (series/parallel/feedback) to get an overall system transfer function. 
    <br>
- **Controller** $C(s)$**:** The “decision” block that turns error into an actuator command (could be PID, lead/lag, state feedback, etc.). 
    <br>
- **[[Plant]]nt** $P(s)$**:** The physical system being controlled (motor, heater, suspension, etc.). 
    <br>
- **Sensor / measurement** $H(s)$**:** Maps the physical output into a measured signal used for feedback (often includes scaling and dynamics). 
    <br>
- **[[Disturbances|Disturbance]] input** $d(t)$ **or** $D(s)$**:** An external/uncommanded influence entering the plant (load torque, wind gust, ambient temperature shift).   
    <br>
- **Noise** $n(t)$**:** Unwanted variation in measurement (often injected on the sensor/feedback path). 
    <br>
- **Canonical closed-loop form:** If forward path is $G(s)=C(s)P(s)$ and feedback is $H(s)$, then
    $$\frac{Y(s)}{R(s)}=\frac{G(s)}{1+G(s)H(s)}$$
    
    (This is the “why feedback works… and sometimes explodes” equation.)
    

  

# Examples:
---

> [!example]
> **Example 1 — Open-loop (feedforward) system with a disturbance**
> 
> **Walkthrough:** The command r(t) is processed by a feedforward command law C(s) (could be as simple as a gain or a model-based mapping). That drives the plant P(s), producing the output y(t). A disturbance d(t) enters _at the plant_, changing the output even if r(t) stays the same—because open-loop control has no direct mechanism to “notice and correct” the deviation.
>  
Practical read: open-loop is fast and simple, but assumes your model is good and disturbances are small/predictable. 
    

---

> [!example]
> **Example 2 — Closed-loop feedback system (reference tracking) with sensor noise**
> 
> **Walkthrough:** The summing junction computes the **error** between the reference and the measured output (the feedback enters with a “−” sign conceptually, even if you don’t draw the minus explicitly on every sketch):
>  $$e(t)=r(t)-\hat{y}(t)$$
>   
> The controller C(s) turns e(t) into an actuator command that drives the plant P(s). The output y(t) is measured by the sensor block H(s) to produce \hat{y}(t), which is fed back through the pickoff/return path to the summing junction. Disturbances d(t) push directly on the plant; sensor noise n(t) contaminates the measurement path—so feedback improves disturbance rejection, but forces you to care about measurement quality and phase delay. 
> 
> The core trade: closed-loop control can reject disturbances and track setpoints, but it introduces phase delay and can destabilize a system if designed poorly. 


# **Resources:**

---

- Course: **Intro to Systems** (system/plant/input/output terminology, transfer-function framing). 
    
- Course: **Closing the Loop** (open vs closed loop, disturbances, noise, stability concerns). 
    
- K. Webb (Oregon State), _Section 2: Block Diagrams & Signal Flow Graphs_ (signals, summing junctions, standard interconnections). 
    
- F. Belkhouche (CSUS), _Introduction to feedback systems_ (summing junctions and pickoff points terminology).