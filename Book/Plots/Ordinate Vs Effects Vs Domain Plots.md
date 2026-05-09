#GraphTheory  #Concept
# **Concept**

---

> [!concept]
> Engineering plots are not interchangeable. The type of plot you choose determines what conclusions you are allowed to draw from data. Many analytical errors in measurement and control do not come from incorrect mathematics, but from using the _wrong class of plot_ and then over interpreting it.

---

## **Key Ideas**
  
+ Understanding the distinctions between these plot types is required before meaningful discussion of sampling, filtering, calibration, or system modeling.
  <br>
+ Every plot makes an implicit claim about causality, predictability, and system behavior. If the plot type is incorrect, downstream analysis may appear mathematically sound while still being physically wrong.
  <br>
+ The single most important question to ask before plotting data is: **What does the x-axis represent?** That answer determines whether adjacency is meaningful, whether causality is implied, and whether prediction is justified.

	+ In an [[Ordinate plot]], the horizontal axis is _not_ a physical domain. It is an index such as sample number, observation order, or group label. *Adjacency between points has no physical meaning.*


	+ In an [[Effects plot]], the horizontal axis represents a real physical domain such as time, temperature, position, voltage, or force. Effects plots answer the question: **How does Y respond when X changes?** Effects plots are exploratory. *They do not guarantee a deterministic or predictive relationship.*


	+ In a [[Domain Plot]] or transfer plot, the relationship between axes is defined by a known model. Each input value maps to a specific output value according to theory, design, or validated characterization. Transfer plots answer the question: **If I apply X, what Y will the system produce?**  *Lines on transfer plots represent system behavior, not visual guidance.*


> [!warning]
> **Common Failure Modes**
> + Treating an ordinate plot as time-based
> + Drawing best-fit lines on effects plots and calling them models
> + Assuming noisy experimental data defines a transfer function
> 
These errors often survive correct mathematics and still lead to incorrect conclusions.
  # Examples: 
---
> [!example]
> TBD




# Resources:
---

- MCET 520 – Lecture 1: Graph Theory (Ordinate vs Effects Plots)