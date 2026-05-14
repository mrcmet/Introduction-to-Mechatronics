---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> **Singularity functions** (Macaulay brackets) express the [[Internal Forces in Beams|shear force and bending moment]] in a beam as single, continuous equations over the full span. The bracket $\langle x - a \rangle^n$ equals $(x - a)^n$ when $x > a$, and zero when $x \leq a$, letting you account for [[Point Load and Distributed Load|point loads and distributed loads]] that start at arbitrary positions without splitting the beam into segments.

Notes:
- Integration rule for $n \geq 0$: $\displaystyle\int \langle x - a \rangle^n \, dx = \frac{\langle x - a \rangle^{n+1}}{n+1}$. 
	- Integrate exactly like a power function — keep the brackets intact.
- Each load type maps to a specific exponent: 
	- an upward [[Support Reactions|reaction]] $R$ at $x = a$ contributes $+R\langle x - a \rangle^0$ to $V(x)$.
	- a downward point load $P$ at $x = a$ contributes $-P\langle x - a \rangle^0$.
	- a UDL of intensity $w$ starting at $x = a$ contributes $-w\langle x - a \rangle^1$.
- To **stop** a UDL at position $b$, superimpose an equal and opposite load starting at $b$: add $+w\langle x - b \rangle^1$. This is the key trick — distributed loads are always started and then cancelled.
- Integrating $V(x)$ gives $M(x)$; integrating $M(x)$ gives slope $\theta(x)$; integrating again gives deflection $y(x)$. Boundary conditions at known support points (zero deflection at a pin or roller) solve for integration constants. This makes singularity functions particularly powerful for [[Beam Deflection]] problems.

## Examples and Non-Examples

- **Point load on a simply supported beam.** Beam length $L = 4\ \text{m}$, downward load $P = 12\ \text{kN}$ at $x = 1\ \text{m}$. Reactions (by statics): $A_y = 9\ \text{kN}$ (up), $B_y = 3\ \text{kN}$ (up).

  Shear (writing left-to-right, upward positive):
  $$V(x) = 9\langle x \rangle^0 - 12\langle x - 1 \rangle^0 - 3\langle x - 4 \rangle^0$$

  Integrate to get moment:
  $$M(x) = 9\langle x \rangle^1 - 12\langle x - 1 \rangle^1 - 3\langle x - 4 \rangle^1$$

  Check at $x = 4\ \text{m}$ (roller, must have $M = 0$): $M = 9(4) - 12(3) - 3(0) = 36 - 36 = 0\ \checkmark$

- **UDL over a partial span.** A simply supported beam of length $L = 6\ \text{m}$ carries a UDL $w = 8\ \text{kN/m}$ from $x = 1\ \text{m}$ to $x = 4\ \text{m}$ (total load $= 8 \times 3 = 24\ \text{kN}$, centroid at $x = 2.5\ \text{m}$). Reactions: $A_y = 14\ \text{kN}$, $B_y = 10\ \text{kN}$.

  $$V(x) = 14\langle x \rangle^0 - 8\langle x - 1 \rangle^1 + 8\langle x - 4 \rangle^1 - 10\langle x - 6 \rangle^0$$

  $$M(x) = 14\langle x \rangle^1 - 4\langle x - 1 \rangle^2 + 4\langle x - 4 \rangle^2 - 10\langle x - 6 \rangle^1$$

  Note the $+8\langle x-4\rangle^1$ term that cancels the UDL at $x = 4\ \text{m}$ — without it the distributed load would run to the end of the beam.

- **Counter-example — treating Macaulay brackets as ordinary parentheses.** A student evaluates $\langle x - 3 \rangle^0$ at $x = 2\ \text{m}$ and gets $(2 - 3)^0 = 1$. But the bracket is zero for $x \leq 3$: the correct value is $0$. Using regular parentheses produces a shear diagram that is wrong for every point to the left of the load.

## Resources
- ![](https://youtu.be/IW9uvArmypg?si=dpT0ayH0YaDBIswQ&t=346)

## Practice
- A simply supported beam of length $L = 6\ \text{m}$ carries a downward point load $P = 18\ \text{kN}$ at $x = 2\ \text{m}$. Write $V(x)$ and $M(x)$ using singularity functions, and evaluate $M$ at $x = 2\ \text{m}$ and $x = 4\ \text{m}$.

> [!NOTE]- Answer
> **Reactions:** $B_y = 18(2)/6 = 6\ \text{kN}$; $A_y = 12\ \text{kN}$
>
> $V(x) = 12\langle x \rangle^0 - 18\langle x - 2 \rangle^0 - 6\langle x - 6 \rangle^0$
>
> $M(x) = 12\langle x \rangle^1 - 18\langle x - 2 \rangle^1 - 6\langle x - 6 \rangle^1$
>
> $M(2) = 12(2) - 18(0) = 24\ \text{kN·m}$
>
> $M(4) = 12(4) - 18(2) = 48 - 36 = 12\ \text{kN·m}$
