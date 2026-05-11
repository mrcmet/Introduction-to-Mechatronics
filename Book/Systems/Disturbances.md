 #Definition #Systems

# Definition
---
  
> [!definition]
> A disturbance is an uncommanded physical influence on a [[Systems|system]] that pushes the output away from what the input alone would produce. Disturbances are typically irregular, uncontrollable, and not perfectly predictable (e.g., wind gusts, ambient temperature swings, component wear). In [[Block Diagrams|block-diagram]] terms, they are “extra inputs” that act on the plant, often modeled as an additive signal d(t) (or D(s)) acting at the plant input or output. 

A common [[LTI (Linear Time-Invariant) systems|LTI]] modeling move is:
$$Y(s)=G(s)\,U(s)+G_d(s)\,D(s)$$
where $G(s)$ is the commanded input-to-output [[Transfer Function|transfer function]], and $G_d(s)$ is the disturbance-to-output transfer function.

  
# Key Ideas:
---

- Disturbances come from the real world acting on the [[Plant]], not from what we asked the plant to do.  
<br>
- Disturbances are different from measurement noise (noise corrupts what you read; disturbances change what the plant does).  
<br>
- In analysis, we care about disturbance rejection: how much the controller reduces the effect of D on Y. 
<br>
- Some disturbances are partially measurable (e.g., outside temperature) and can be mitigated with feedforward, not just feedback.  

# Examples:
---

> [!example]
Wind gust on a quadcopter (external disturbance)
>
A sudden gust adds an uncommanded lateral force $F_w(t)$ , changing acceleration even if motor commands are unchanged. The measured position drifts, and the controller must reject $F_w$ to hold position. 


  > [!example]
> An oven door is cracked open to look at cookies and ambient temperature swing (thermal disturbance)The kitchen air acts like a disturbance heat-flow term $\dot{Q}_d(t)$. Even with the same heater power command, the oven temperature output deviates because the environment changed. 


  > [!example]
>  Motor load change from wear/friction (load disturbance)
>  
A DC motor driving a mechanism experiences an added load torque $\tau_d(t)$ (bearing wear, misalignment, friction changes). Speed drops at the same voltage/PWM command until the controller increases command to compensate. In many plants, “load disturbance” is the dominant real-world annoyance.  

  
# Resources:
---

- Course source (Disturbances definition & examples) — Lecture 1: Intro to Systems. 
- Load disturbance vs measurement noise in feedback loops — “Specifications and disturbance models” (Lund University notes).  
- Disturbance rejection (control objective + block diagram framing) — Engineering LibreTexts section on disturbance rejection.  
- Course note on citing AI-assisted writing — MCET520 welcome slide deck.
