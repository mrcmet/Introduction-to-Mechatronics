---
tags: [mechanics]
---
#mechanics

## Definition
> [!definition]
> The **stress tensor** ($\boldsymbol{\sigma}$) is a 3×3 matrix that fully describes the state of stress at a single point in a body — capturing all [[Normal Stress]] and [[Shear Stress]] components acting on three mutually perpendicular faces of an infinitesimal element.

Notes:
- The tensor has nine components, but rotational equilibrium requires $\tau_{ij} = \tau_{ji}$, leaving only six independent values:

$$\boldsymbol{\sigma} = \begin{bmatrix} \sigma_x & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_y & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_z \end{bmatrix}$$
         ![[Pasted image 20260513134013.png|460]]
The diagonal ($\sigma_x$, $\sigma_y$, $\sigma_z$) holds the [[Normal Stress|normal stresses]]. Everything off the diagonal is [[Shear Stress]].

- **Subscript notation:** $\sigma_{ij}$ means the stress acts on the face whose outward normal points in the $i$-direction, and the stress vector itself points in the $j$-direction. 
	- For normal stresses $i = j$;
	- For shear stresses $i \neq j$.
- The stress tensor is **coordinate-dependent.** The same physical stress state produces different numerical entries in a rotated coordinate system. Mohr's Circle is a 2D graphical tool for tracking how stress components change with rotation, and for finding the **principal stresses** — the orientation where all shear entries vanish and only normal stresses remain.
- Most problems in this course involve **plane stress**, where loading is confined to one plane and $\sigma_z = \tau_{xz} = \tau_{yz} = 0$. This reduces the tensor to three independent values: $\sigma_x$, $\sigma_y$, and $\tau_{xy}$.
- **Sign convention:** 
	- Normal stresses are positive in tension, negative in compression. 
	- Shear stresses on a positive face (outward normal in the positive coordinate direction) are positive when they point in the positive coordinate direction.

## Examples and Non-Examples

- **Pure axial tension.** A rod pulled along the $x$-axis develops only $\sigma_x = 120\ \text{MPa}$, all other components zero:
$$\boldsymbol{\sigma} = \begin{bmatrix} 120 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}\ \text{MPa}$$
This is the simplest possible stress state — a single diagonal entry, no shear terms.

- **Plane stress under combined loading.** A point on a shaft surface experiences $\sigma_x = 80\ \text{MPa}$ (from [[Bending Stress]]) and $\tau_{xy} = 45\ \text{MPa}$ (from [[Torsional Shear Stress]]), with all out-of-plane components zero:
$$\boldsymbol{\sigma} = \begin{bmatrix} 80 & 45 & 0 \\ 45 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}\ \text{MPa}$$
Note $\tau_{yx} = \tau_{xy} = 45\ \text{MPa}$ by symmetry. This tensor is the starting point for a Mohr's Circle analysis to find the principal stresses and the maximum shear stress.

- **Counter-example — a single stress value is not the full stress state.** Computing $\sigma = F/A$ gives the $\sigma_x$ entry of the tensor for a purely axial member — one number out of six. Under [[Combined Loading]], multiple entries are nonzero simultaneously. Making a [[Factor of Safety]] decision based on a single component while ignoring the others can be dangerously unconservative.

## Resources

![](https://youtu.be/P7aJq0U6lyM?si=Y4fzaNETXel6jIZJ)
 ![](https://www.youtube.com/watch?v=xkbQnBAOFEg)
![](https://youtu.be/78K0pbvHzjM?si=1WtGRweBmTAhhgjB)

## Practice
- A point in a loaded structure has the following stress state: $\sigma_x = 60\ \text{MPa}$, $\sigma_y = -20\ \text{MPa}$, $\tau_{xy} = 30\ \text{MPa}$, all out-of-plane components zero. (a) Write the full 3×3 stress tensor. (b) How many independent nonzero values does it contain?

> [!NOTE]- Answer
> **(a) Full tensor (plane stress):**
> $$\boldsymbol{\sigma} = \begin{bmatrix} 60 & 30 & 0 \\ 30 & -20 & 0 \\ 0 & 0 & 0 \end{bmatrix}\ \text{MPa}$$
>
> **(b)** Three independent nonzero values: $\sigma_x = 60\ \text{MPa}$, $\sigma_y = -20\ \text{MPa}$, and $\tau_{xy} = 30\ \text{MPa}$. The entry $\tau_{yx} = 30\ \text{MPa}$ appears in the matrix but is not independent — it equals $\tau_{xy}$ by rotational equilibrium.
