# Mechanics Sequence Tracker

A living doc for planning and tracking the Mechanics section of the web book. Update status columns as pages are built, reviewed, and published. Add backlinks to the **Connects to** column whenever a page is drafted — both the new page's outgoing links and any existing pages that should link back to it.

**Status key:** `—` not started · `🔨` built · `👁` reviewed · `✅` published

---

## Existing Pages

| Page                          | Built | Reviewed | Published | Connects to                                                                                                                                |
| ----------------------------- | ----- | -------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| [[Axial Stress]]              | ✅     | ✅        | ✅         | [[Normal Stress]], [[Shear Stress]], [[Hooke's Law]], [[Strain]], [[Young's Modulus]], [[Saint-Venant's Principle]], [[Free Body Diagram]] |
| [[Axial Deformation]]         | ✅     | ✅        | ✅         | [[Young's Modulus]], [[Strain]], [[Hooke's Law]], [[Axial Stress]]                                                                         |
| [[Strain]]                    | ✅     | ✅        | ✅         | [[Axial Deformation]], [[Young's Modulus]], [[Hooke's Law]], [[Stress-Strain Curve]]                                                       |
| [[Young's Modulus]]           | ✅     | ✅        | ✅         | [[Hooke's Law]], [[Strain]], [[Axial Stress]], [[Stress-Strain Curve]]                                                                     |
| [[Hooke's Law]]               | ✅     | ✅        | ✅         | [[Young's Modulus]], [[Strain]], [[Axial Stress]], [[Stress-Strain Curve]]                                                                 |
| [[Stress-Strain Curve]]       | ✅     | ✅        | ✅         | [[Yield Strength]], [[Ultimate Tensile Strength]], [[Young's Modulus]], [[Strain]], [[Hooke's Law]]                                        |
| [[Yield Strength]]            | ✅     | ✅        | ✅         | [[Stress-Strain Curve]], [[Factor of Safety]], [[Axial Stress]]                                                                            |
| [[Ultimate Tensile Strength]] | ✅     | ✅        | ✅         | [[Stress-Strain Curve]], [[Factor of Safety]], [[Yield Strength]]                                                                          |
| [[Factor of Safety]]          | ✅     | ✅        | ✅         | [[Yield Strength]], [[Ultimate Tensile Strength]], [[Axial Stress]]                                                                        |

---

## Phase 1 — Gap-fillers (dangling backlinks in existing pages)

| Page                         | Built | Reviewed | Published | Connects to                                                                                                                               |
| ---------------------------- | ----- | -------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| [[Shear Stress]]             | ✅     | ✅        | ✅         | [[Axial Stress]], [[Normal Stress]], [[Transverse Shear Stress in Beams]], [[Torsional Shear Stress]], [[Shear Modulus]], [[Hooke's Law]] |
| [[Normal Stress]]            | ✅     | ✅        | ✅         | [[Axial Stress]], [[Bending Stress]], [[Shear Stress]], [[Neutral Axis]], [[Combined Loading]]                                            |
| [[Stress Tensor]]            | ✅     | ✅        | ✅         | [[Normal Stress]], [[Shear Stress]], [[Bending Stress]], [[Torsional Shear Stress]], [[Combined Loading]], [[Factor of Safety]]           |
| [[Poisson's Ratio]]          | ✅     | ✅        | ✅         | [[Axial Deformation]], [[Strain]], [[Young's Modulus]], [[Shear Modulus]]                                                                 |
| [[Free Body Diagram]]        | ✅     | ✅        | ✅         | [[Axial Stress]], [[Support Reactions]], [[Internal Forces in Beams]], [[Beam End Conditions]], [[Point Load and Distributed Load]], [[Static Equilibrium]]       |
| [[Saint-Venant's Principle]] | ✅     | ✅        | ✅         | [[Axial Stress]], [[Bending Stress]], [[Bending Moment Diagram]], [[Stress Concentrations]]                                               |

---

## Phase 2 — Beam setup and internal forces

| Page                                | Built | Reviewed | Published | Connects to                                                                                                                                                            |
| ----------------------------------- | ----- | -------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Internal Forces in Beams]]        | ✅     | ✅        | ✅         | [[Free Body Diagram]], [[Shear Force Diagram]], [[Bending Moment Diagram]], [[Axial Stress]], [[Bending Stress]], [[Support Reactions]]                                |
| [[Beam End Conditions]]             | ✅     | ✅        | ✅         | [[Support Reactions]], [[Internal Forces in Beams]], [[Shear Force Diagram]], [[Bending Moment Diagram]], [[Free Body Diagram]]                                        |
| [[Point Load and Distributed Load]] | ✅     | ✅        | ✅         | [[Beam End Conditions]], [[Support Reactions]], [[Shear Force Diagram]], [[Bending Moment Diagram]], [[Free Body Diagram]]                                             |
| [[Support Reactions]]               | ✅     | ✅        | ✅         | [[Free Body Diagram]], [[Beam End Conditions]], [[Point Load and Distributed Load]], [[Internal Forces in Beams]], [[Shear Force Diagram]], [[Bending Moment Diagram]], [[Static Equilibrium]] |

---

## Phase 3 — Diagrams

| Page                       | Built | Reviewed | Published | Connects to                                                                                                                                                                    |
| -------------------------- | ----- | -------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [[Shear Force Diagram]]    | ✅     | ✅        | ✅         | [[Internal Forces in Beams]], [[Bending Moment Diagram]], [[Support Reactions]], [[Point Load and Distributed Load]], [[Transverse Shear Stress in Beams]], [[Bending Stress]] |
| [[Bending Moment Diagram]] | ✅     | ✅        | ✅         | [[Shear Force Diagram]], [[Internal Forces in Beams]], [[Bending Stress]], [[Neutral Axis]]                                                                                    |
| [[Singularity Functions]]  | ✅     | ✅        | ✅         | [[Shear Force Diagram]], [[Bending Moment Diagram]]                                                                                                                            |

> [!note] Singularity Functions
> Optional/advanced — include if students will write programmatic beam solutions. Hold until Phases 2–3 are drafted and scope is clearer.

---

## Phase 4 — Bending stress

| Page                                 | Built | Reviewed | Published | Connects to                                                                                                                                                                                                                                           |
| ------------------------------------ | ----- | -------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Second Moment of Area]]            | ✅     | ✅        | ✅         | [[Bending Stress]], [[Neutral Axis]], [[Transverse Shear Stress in Beams]], [[Beam Deflection]], [[Torsional Shear Stress]], [[Polar Moment of Area]]                                                                                                 |
| [[Neutral Axis]]                     | ✅     | ✅        | ✅         | [[Second Moment of Area]], [[Bending Stress]], [[Bending Moment Diagram]], [[Young's Modulus]], [[Shear Stress]]                                                                                                                                      |
| [[Bending Stress]]                   | ✅     | ✅        | ✅         | [[Bending Moment Diagram]], [[Second Moment of Area]], [[Neutral Axis]], [[Normal Stress]], [[Axial Stress]], [[Factor of Safety]], [[Saint-Venant's Principle]], [[Transverse Shear Stress in Beams]], [[Yield Strength]], [[Stress Concentrations]] |
| [[Transverse Shear Stress in Beams]] | ✅     | ✅        | ✅         | [[Shear Force Diagram]], [[Second Moment of Area]], [[Neutral Axis]], [[Shear Stress]], [[Bending Stress]], [[Direct Shear Stress]]                                                                                                                   |
| [[Beam Deflection]]                  | ✅     | ✅        | ✅         | [[Bending Moment Diagram]], [[Second Moment of Area]], [[Young's Modulus]], [[Beam End Conditions]], [[Bending Stress]]                                                                                                                               |

---

## Phase 5 — Torsion

| Page                       | Built | Reviewed | Published | Connects to                                                                                                                                                                                                                            |
| -------------------------- | ----- | -------- | --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Torque]]                 | ✅     | ✅        | ✅         | [[Torsional Shear Stress]], [[Angle of Twist]], [[Polar Moment of Area]], [[Shear Modulus]], [[Bending Stress]], [[Combined Loading]], [[Internal Forces in Beams]]                                                                    |
| [[Shear Modulus]]          | ✅     | ✅        | ✅         | [[Shear Stress]], [[Poisson's Ratio]], [[Young's Modulus]], [[Torque]], [[Angle of Twist]], [[Stress-Strain Curve]]                                                                                                                    |
| [[Polar Moment of Area]]   | ✅     | ✅        | ✅         | [[Torsional Shear Stress]], [[Angle of Twist]], [[Torque]], [[Second Moment of Area]]                                                                                                                                                  |
| [[Torsional Shear Stress]] | ✅     | ✅        | ✅         | [[Torque]], [[Polar Moment of Area]], [[Shear Stress]], [[Shear Modulus]], [[Saint-Venant's Principle]], [[Factor of Safety]], [[Second Moment of Area]], [[Combined Loading]], [[Transverse Shear Stress in Beams]], [[Axial Stress]] |
| [[Angle of Twist]]         | ✅     | ✅        | ✅         | [[Torque]], [[Polar Moment of Area]], [[Shear Modulus]], [[Axial Deformation]]                                                                                                                                                         |

---

## Phase 6 — Design connections (stretch)

| Page                      | Built | Reviewed | Published | Connects to                                                                                                                                                                                                     |
| ------------------------- | ----- | -------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Combined Loading]]      | ✅     | ✅        | ✅         | [[Axial Stress]], [[Bending Stress]], [[Torsional Shear Stress]], [[Transverse Shear Stress in Beams]], [[Shear Stress]], [[Factor of Safety]], [[Stress Concentrations]], [[Neutral Axis]], [[Yield Strength]] |
| [[Stress Concentrations]] | ✅     | ✅        | ✅         | [[Axial Stress]], [[Bending Stress]], [[Torsional Shear Stress]], [[Factor of Safety]], [[Fatigue]], [[Combined Loading]], [[Saint-Venant's Principle]]                                                         |
| [[Fatigue]]               | ✅     | ✅        | ✅         | [[Stress Concentrations]], [[Yield Strength]], [[Ultimate Tensile Strength]], [[Factor of Safety]], [[Torsional Shear Stress]], [[Bending Stress]], [[Combined Loading]]                                        |

> [!note] Fatigue & Stress Concentrations
> These are deliberate, longer-form pages — write them after the core sequence is complete. Fatigue in particular should carry mechatronics-specific flavor: rotating shafts, motor mounts, S-N curves, vibration.

---

## Statics for Mechanisms (MECA 290 L3)

Added 2026-08-10 to support the Lecture 3 diagram→force step. [[Static Equilibrium]] is now the canonical $\sum F = 0,\ \sum M = 0$ page — [[Free Body Diagram]] and [[Support Reactions]] link to it. [[Joint Reaction Force]] is the mechanism-joint counterpart to beam [[Support Reactions]] and pairs with the Dynamics-side [[Linkage Diagram]] / [[Kinematic Pair]] pages.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Static Equilibrium]] | 🔨 | — | — | [[Free Body Diagram]], [[Support Reactions]], [[Joint Reaction Force]], [[Newton's Second Law]] |
| [[Joint Reaction Force]] | 🔨 | — | — | [[Static Equilibrium]], [[Kinematic Pair]], [[Newton's Third Law]], [[Free Body Diagram]], [[Support Reactions]], [[Linkage Diagram]] |

---

## Progress Summary

| Phase                    | Total  | Built  | Reviewed | Published |
| ------------------------ | ------ | ------ | -------- | --------- |
| Existing                 | 9      | 9      | 9        | 9         |
| Phase 1 — Gap-fillers    | 6      | 6      | 0        | 0         |
| Phase 2 — Beam setup     | 4      | 4      | 0        | 0         |
| Phase 3 — Diagrams       | 3      | 0      | 0        | 0         |
| Phase 4 — Bending stress | 5      | 1      | 0        | 0         |
| Phase 5 — Torsion        | 5      | 2      | 0        | 0         |
| Phase 6 — Stretch        | 3      | 0      | 0        | 0         |
| Statics for Mechanisms   | 2      | 2      | 0        | 0         |
| **Total**                | **37** | **24** | **9**    | **9**     |
