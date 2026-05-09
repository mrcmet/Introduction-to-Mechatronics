#GraphTheory #Definition 
# Definition

---

> [!tldr]
> In engineering plots, a **domain** is the physical quantity represented on the independent axis(x) of a graph. The domain defines _what is being controlled, varied, or observed independently_ and provides the context required to interpret how a measured response behaves. Common domains include time, position, temperature, voltage, frequency, and force.

A domain is not merely an axis label; it is a statement about the nature of the system and how measurements are related, or more succinctly stated from https://en.wikipedia.org/wiki/Domain_of_a_function: 

	In mathematics, the domain of a function is the set of inputs accepted by the function. It is sometimes denoted by dom(f) or dom_f, where f is the function.In layman's terms, the domain of a function can generally be thought of as "what x can be"
	
In other words, the domain is the answer to the question "what measurement system does the X axis belong to?"


# **Key Ideas**

---

- The domain is almost always plotted on the horizontal (x) axis against the [[Codomain]] plotted on the vertical axis (y).
    <br>
- A valid domain must correspond to a real physical quantity
    <br>
- Domains carry units and meaning (seconds, meters, volts, hertz)
    <br>
- Without a domain, causality and dynamics cannot be inferred
    <br>
- The chosen domain determines what analysis techniques are valid
    

## Why Domains Matter

---

The domain answers the question:

**“With respect to** _**what**_ **is this signal changing?”**

Changing the domain changes the interpretation of the data:

- Time domain → dynamics, transients, stability
    <br>
- Frequency domain → periodic content, interference, resonance
    <br>
- Spatial domain → deformation, gradients, distributions
    

Using the wrong domain—or omitting it entirely—leads to plots that look correct but communicate false conclusions.

## Common Engineering Domains

---

### Time Domain

Used when the independent variable is time.

Typical uses:

- Dynamic system behavior
    
- Transient response
    
- Control and stability analysis
    

Examples:

- Voltage vs *time
    
- Position vs *time
    
- Temperature vs *time
    

### Spatial Domain

Used when the independent variable is position or distance.

Typical uses:

- Strain or stress distributions
    
- Deflection along a beam
    
- Pressure variation along a pipe
    

Examples:

- Stress vs position
    
- Temperature vs distance
    

### Frequency Domain

Used when the independent variable is frequency.

Typical uses:

- Signal content analysis
    
- Noise and interference identification
    
- Filter design
    

Examples:

- Amplitude vs frequency
    
- Power spectral density vs frequency
    

### Other Domains

Depending on the system, domains may also include:

- Voltage
    
- Force
    
- Current
    
- Flow rate
    
- Magnetic field strength
    

The domain must always reflect the quantity being independently varied or evaluated.

---

## Domain vs Index

A domain must not be confused with an index.

- Domain: time, position, temperature (physical meaning)
    <br>
- Index: sample number, trial count (no physical meaning)
    

Plots using an index instead of a domain are [[Ordinate plot|ordinate plots]], not domain-based plots.
# Examples:

---

> [!example]  
> **Time Domain Example:**
A classic example showing how a signal varies over time (voltage vs time waveform). The time axis is explicitly shown with oscillations over time.
> [![example o-scope graph](https://cdn.sparkfun.com/r/600-600/assets/e/5/1/2/6/52f29ce3ce395f8c1b8b4569.png)](https://cdn.sparkfun.com/assets/e/5/1/2/6/52f29ce3ce395f8c1b8b4569.png)


> [!example]  
> **Frequency Domain Example:**
A frequency domain plot typically shows the spectral content (e.g., amplitude vs frequency). In this classic example we see a Spectrogram where the Domain is frequency represented in Hz. and the codomain is Amplitude. This is omst practically acheived through the use of an [[Fast Fourier Transform | FFT]]
> ![](https://miro.medium.com/v2/resize:fit:1400/1*u9ZbW2BrhUVnAmzm7yYOTg.jpeg)

> [!example]  
> **Spatial Domain Example:**
> A plot of stress Vs. Strain is a common example of a plot in the spatial domain. Here we see the domain as Strain and a unit system of % showing that a domain can have many different unit systems.
![[Pasted image 20251228122646.png]]


Common domains include:
+ Time
+ Position
+ Temperature
+ Frequency
+ Energy

> [!warning]
> Its important to remember that these domains are fundamental. This means that some of  these domains can be expanded on. For example Kinetic energy is a form of energy just as well as Potential energy. This can often lead to confusion with units, for example Work is a domain who has units of N-m or Jules and is a measure of force acting through a distance. 
> Similarly Torque is a measure of force acting at a distance through a line of action. Although this has units of N-m it is not part of the energy domain but the Torque domain. It could also be considered to be part of the Work domain since work is a requirement of torque. It's best not to over think this but you can see how units are connected to domains, and how domains can be intertwined. At the end of the day, what is the thing on the X axis.    

# Resources:
---
## Image Attributions:
+ *Stress and Strain Curve Explained | A Beginner's Guide* https://caeassistant.com/blog/stress-strain-curve/
+ SparkFun; *How to Use an Oscilloscope* https://learn.sparkfun.com/tutorials/how-to-use-an-oscilloscope/basics-of-o-scopes 
+ Medium; *Breaking down confusions over Fast Fourier Transform (FFT)* https://medium.com/analytics-vidhya/breaking-down-confusions-over-fast-fourier-transform-fft-1561a029b1ab