#GraphTheory #Definition 
# Definition

---

> [!Definition]  
> An ordinate plot is a graph where measured values are plotted against an arbitrary or non-physical index rather than a true independent variable. The horizontal axis does not represent a domain such as time, distance, or temperature; instead, it represents sample number, observation order, or group index. Ordinate plots are useful for visualizing variation, trends, or outliers in a dataset when no causal or functional relationship is implied between neighboring points.

---

## **Key Ideas**

- The x-axis is an index, not a physical quantity
    <br>
- Adjacent points have no guaranteed physical relationship
    <br>
- Lines connecting points are a visual convenience, not a model
    <br>
- Commonly used for quick inspection, debugging, or quality checks
    <br>
- Ordinate plots should **not** be used to infer system behavior
    

# Examples:

---

> [!example]  
> A strain gauge is sampled 1,000 times during a static load test, but the sampling interval is unknown or irrelevant. Plotting strain magnitude versus sample number allows the engineer to quickly identify drift, noise, or outliers without implying any time-based behavior.

- The plot shows stability and repeatability, not dynamics
    
- A time-domain interpretation would be incorrect without time information

### Ordinate plots are used to:

- Visualize variation, noise, and drift
    
- Identify outliers
    
- Perform quick inspection or debugging
    

### Ordinate plots must _not_ be used to:

- Infer dynamics
    
- Imply causality
    
- Describe system behavior
    


# Resources:

---

- MCET 520 – Lecture 1: Graph Theory (Ordinate vs Effects Plots)
    
- Tufte, E. _The Visual Display of Quantitative Information_