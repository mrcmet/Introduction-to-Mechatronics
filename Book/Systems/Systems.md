#Systems #Concept 
# **Concept**
---

> [!concept]
>A **system** is a set of interconnected components (physical or computational) that, given an **input signal** u(t) and an **initial condition** (what state it starts in), produces an **output signal** y(t) according to some rule or dynamics. Once you define the boundary of a system, you can name inputs/outputs, model behavior, and decide whether simple tools (like **LTI** models and **transfer functions**) are avalable.
  
  ---
# **Key Ideas:**

- ## **You get to draw the system boundary.** 
  Engineers choose what’s inside vs. outside of the system, giving control over the depth of analysis. A tighter boundary is simpler but may ignore real effects leading to a lower fidelity analysis; a wider boundary is more accurate with higher fidelity but often becomes mathematically difficult. Systems often use a graphical approach called a [[Block Diagrams|block diagram]]
  <br>
- ## **A useful system description starts with I/O and the plant.**
    + **Input:** the command/forcing function you apply
    + **[[Plant]]:**  the physical thing doing the work. This is often modeled with a [[Transfer Function]]
    + **Output:** the response from the plant.
    + Real systems also suffer **[[Disturbances]]** or uncontrolled physical influences.
    + **sensor noise:** is a quantifiable measurement corruption based on real measurement device.
    **These terms change** based on our choice of a [[closed loop system]] vs an [[open loop system]].
    <br>
- ##  [[LTI (Linear Time-Invariant) systems]]:
	They’re the rare corner of the universe where prediction is friendly and we have a robust set of mathematical tools for dealing with the [[ODE | Ordinary Differential Equation (ODE)]]. for a system to be LTI it's Transfer Function must pass **two tests.**
    Linearity or [[Superposition]] which is captured by:
    $$H(a,x_1(t)+b,x_2(t)) = a,H(x_1(t)) + b,H(x_2(t))$$
    
    And [[Time Invariant Systems | Time invariance]] which means shifting the input shifts the output by the same amount: if y(t)=H(x(t)), then
    $$H(x(t-T)) = y(t-T)$$
    
    This is why LTI systems can be characterized cleanly by an [[Impulse response ]].   
    <br>
- ## [[Transfer function]] 
	This is the “input-to-output rule” in a system as it performs an exchange in [[Domains]]. For an LTI, single input single output(SISO) system with zero initial conditions, we often define the system with either a - **[[State-space]] (most general for many engineered systems)** representation.
    $$\dot{x}(t)=f(x(t),u(t),t), \quad y(t)=g(x(t),u(t),t)$$
    Or we use the **[[S-Domain | S-Domain Transfer function]]** (Common for LTI Systems) representation.
    $$G(s)=\frac{Y(s)}{U(s)}$$
    
    Conceptually, it’s the mathematical version of “if I put in u, what y comes out?”—even when time isn’t explicitly plotted on the [[Domain Plot]], time is _implicitly_ tying cause to effect.   
<br>
- ## **Open-loop vs closed-loop.**
	Systems, typically are of practical use when we want to control the output to match the input into the system. These systems are control systems and are typically broken into 2 categories.
    [[Open-loop]] control acts without knowing the current state of a system.
    [[Closed-loop]] control uses measurement feedback to reject disturbances—at the cost of added dynamics like phase delay and possible instability if poorly designed. 
    

# **Examples:**

---

> [!example]
>
> TBD

  
# **Resources:**

---

+ ***Everything You Need to Know About Control Theory**
https://youtu.be/lBC1nEq0_nk?si=GoVC61NxdmaM3nc7

+ ** What Control Systems Engineers Do **
https://youtu.be/ApMz1-MK9IQ?si=0lF7uzO7biS3vJS8

- **Course sources (slides):** Intro to Systems; Closing the Loop.
    
- **Definition (systems engineering):** “A combination of interacting elements organized to achieve one or more stated purposes.” 
    
- **LTI primer:** Wikipedia LTI overview; Signals & Systems (LibreTexts). 
    
- **Transfer functions (clean intro):** KU Open Textbook chapter on Laplace/transfer functions. 
    
- **Broader systems perspective:** NASA Systems Engineering Handbook; SEBoK system glossary.