# Dynamics Sequence Tracker

A living doc for planning and tracking the Dynamics section of the web book. Update status columns as pages are built, reviewed, and published. Add backlinks to the **Connects to** column whenever a page is drafted — both the new page's outgoing links and any existing pages that should link back to it.

**Status key:** `—` not started · `🔨` built · `👁` reviewed · `✅` published

> [!note] Scope update (2026-05-23)
> Topic list revised to align with the integrated motion-systems course philosophy: **motion event → dynamic load → mechanical consequence → design judgment.** Key changes from the 2026-05-18 structure:
> - **Sections reorganized** around how motion is planned, analyzed, and loaded — not just classical mechanics phases.
> - **Motion profiles** are now a first-class section (trapezoidal, triangular, S-curve, jerk, cycle time).
> - **Actuator and motor dynamics** (reflected inertia, RMS torque, duty cycle) elevated to their own section.
> - **Vibration** is now in scope — covered at single-DOF/mass-spring-damper level, linking into any future separate vibration folder.
> - **Control-ready dynamics** (state variables, transfer function, settling time) added as a bridge to the controls section.
> - **Canonical example platforms** (used throughout *Examples* sections): XY gantry, conveyor indexer, rotary table, lead-screw actuator, mobile robot, vibrating machine.

> [!note] Scope update (2026-08-10) — MECA 290 Module 1/2 alignment
> Cross-referenced the vault against the MECA 290 lecture briefs (L2 Linkages & DOF, L3 Kinematic Diagrams & Constraints, L4 Vector Introduction, L5 Coordinate Frames). Module 2 (vectors, frames, rotations) is well covered by the built `Book/Dynamics/Advanced Motion/` pages. The clear gap is **Module 1's linkage-analysis toolkit** — added below as a new **Linkage Analysis and Mobility** section.
> - **Naming decision:** the mechanism links-and-joints skeleton is titled **[[Linkage Diagram]]**. The existing `Advanced Motion/Kinematic Diagram` page (the acceleration/kinetic diagram drawn beside an FBD) is a *different concept* and stays as-is — no rename.
> - Also added: [[Forward Kinematics]] and [[Scalar and Vector]] (vector/frame on-ramps), and [[Static Equilibrium]] (may instead live in the Mechanics tracker — flagged there).
> - **Reconciliation note:** the built `Advanced Motion/` pages (DOF, Coordinate Frames, Unit Vectors and Basis, Vector Addition and Components, 2D Rotation Matrix, Position Vector, etc.) are not yet represented as rows in this tracker's planned sections; their titles differ from the generic placeholders in *Coordinate Systems and Vectors* / *Angular Motion*. Reconcile in a later pass.

---

## Motion Foundations

Scalar and vector descriptions of motion. Terminal/lookup pages — exist mainly as link targets for downstream sections.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Position]] | 🔨 | — | — | [[Displacement]], [[Velocity]], [[Reference Frame]], [[Position Vector]], [[Initial Condition]], [[Distance Traveled]], [[Positive Direction]], [[Coordinate Frames]] |
| [[Displacement]] | 🔨 | — | — | [[Position]], [[Distance Traveled]], [[Velocity]], [[Constant Acceleration Equations]], [[Positive Direction]] |
| [[Distance Traveled]] | 🔨 | — | — | [[Displacement]], [[Speed]], [[Velocity]], [[Position]], [[Positive Direction]] |
| [[Time Interval]] | 🔨 | — | — | [[Velocity]], [[Acceleration]], [[Average Velocity]], [[Average Acceleration]], [[Impact Duration]], [[Displacement]], [[Constant Acceleration Equations]] |
| [[Velocity]] | 🔨 | — | — | [[Position]], [[Acceleration]], [[Instantaneous Velocity]], [[Average Velocity]], [[Speed]], [[Velocity Vector]], [[Reference Frame]], [[Positive Direction]], [[Position Vector]] |
| [[Speed]] | 🔨 | — | — | [[Velocity]], [[Distance Traveled]], [[Position]], [[Positive Direction]] |
| [[Average Velocity]] | 🔨 | — | — | [[Velocity]], [[Displacement]], [[Time Interval]], [[Speed]], [[Distance Traveled]], [[Instantaneous Velocity]], [[Position]] |
| [[Instantaneous Velocity]] | 🔨 | — | — | [[Velocity]], [[Velocity-Time Graph]], [[Velocity from Position]], [[Average Velocity]], [[Position-Time Graph]], [[Acceleration]], [[Time Interval]] |
| [[Acceleration]] | 🔨 | — | — | [[Velocity]], [[Newton's Second Law]], [[Constant Acceleration]], [[Acceleration Vector]], [[Average Acceleration]], [[Instantaneous Acceleration]], [[Jerk]], [[Negative Acceleration]], [[Positive Direction]] |
| [[Average Acceleration]] | 🔨 | — | — | [[Acceleration]], [[Time Interval]], [[Velocity]], [[Average Velocity]], [[Instantaneous Acceleration]], [[Positive Direction]], [[Newton's Second Law]] |
| [[Instantaneous Acceleration]] | 🔨 | — | — | [[Acceleration]], [[Acceleration-Time Graph]], [[Average Acceleration]], [[Velocity-Time Graph]], [[Velocity]], [[Position]], [[Jerk]] |
| [[Constant Acceleration]] | 🔨 | — | — | [[Acceleration]], [[Constant Acceleration Equations]], [[Negative Acceleration]], [[Velocity]], [[Position]], [[Average Acceleration]], [[Instantaneous Acceleration]], [[Positive Direction]] |
| [[Positive Direction]] | 🔨 | — | — | [[Displacement]], [[Velocity]], [[Acceleration]], [[Reference Frame]], [[Coordinate Axis]], [[Negative Acceleration]], [[Position]] |
| [[Negative Acceleration]] | 🔨 | — | — | [[Acceleration]], [[Positive Direction]], [[Deceleration Phase]], [[Required Deceleration]], [[Velocity]], [[Constant Acceleration]] |
| [[Initial Condition]] | 🔨 | — | — | [[Final Condition]], [[Constant Acceleration Equations]], [[Position]], [[Velocity]], [[Time Interval]], [[Equation of Motion]] |
| [[Final Condition]] | 🔨 | — | — | [[Initial Condition]], [[Constant Acceleration Equations]], [[Position]], [[Velocity]], [[Time Interval]], [[Stopping Distance]], [[Stopping Time]] |
| [[Relative Position]] | 🔨 | — | — | [[Position]], [[Reference Frame]], [[Relative Velocity]], [[Position Vector]], [[Moving Reference Frame]], [[Coordinate Frames]] |
| [[Relative Velocity]] | 🔨 | — | — | [[Velocity]], [[Relative Position]], [[Relative Acceleration]], [[Moving Reference Frame]], [[Velocity Vector]], [[Reference Frame]], [[Inertial Reference Frame]] |
| [[Relative Acceleration]] | 🔨 | — | — | [[Acceleration]], [[Relative Velocity]], [[Acceleration Constraint Equation]], [[Relative Position]], [[Acceleration Vector]], [[Reference Frame]], [[Moving Reference Frame]] |

---

## Motion Graphs

Reading and interpreting position, velocity, and acceleration graphs. Builds intuition before equations.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Position-Time Graph]] | — | — | — | [[Velocity-Time Graph]], [[Slope of a Position-Time Graph]], [[Piecewise Motion Graph]] |
| [[Velocity-Time Graph]] | — | — | — | [[Position-Time Graph]], [[Acceleration-Time Graph]], [[Area Under a Velocity-Time Graph]], [[Slope of a Velocity-Time Graph]], [[Trapezoidal Velocity Profile]] |
| [[Acceleration-Time Graph]] | — | — | — | [[Velocity-Time Graph]], [[Area Under an Acceleration-Time Graph]], [[Slope of a Velocity-Time Graph]] |
| [[Slope of a Position-Time Graph]] | — | — | — | [[Position-Time Graph]], [[Velocity]], [[Instantaneous Velocity]] |
| [[Slope of a Velocity-Time Graph]] | — | — | — | [[Velocity-Time Graph]], [[Acceleration]], [[Instantaneous Acceleration]] |
| [[Area Under a Velocity-Time Graph]] | — | — | — | [[Velocity-Time Graph]], [[Displacement]], [[Position from Velocity]] |
| [[Area Under an Acceleration-Time Graph]] | — | — | — | [[Acceleration-Time Graph]], [[Velocity from Acceleration]] |
| [[Motion Graph Consistency]] | — | — | — | [[Position-Time Graph]], [[Velocity-Time Graph]], [[Acceleration-Time Graph]] |
| [[Piecewise Motion Graph]] | — | — | — | [[Motion Graph Consistency]], [[Constant Acceleration]], [[Initial Condition]], [[Trapezoidal Velocity Profile]] |

---

## Linear Motion Equations

Deriving and applying equations of motion under constant and variable acceleration.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Constant Acceleration Equations]] | — | — | — | [[Constant Acceleration]], [[Velocity from Acceleration]], [[Position from Velocity]], [[Initial Condition]], [[Final Condition]] |
| [[Velocity from Acceleration]] | — | — | — | [[Acceleration]], [[Constant Acceleration Equations]], [[Area Under an Acceleration-Time Graph]] |
| [[Position from Velocity]] | — | — | — | [[Velocity]], [[Constant Acceleration Equations]], [[Area Under a Velocity-Time Graph]] |
| [[Acceleration from Velocity]] | — | — | — | [[Velocity]], [[Velocity-Time Graph]], [[Slope of a Velocity-Time Graph]] |
| [[Velocity from Position]] | — | — | — | [[Position]], [[Position-Time Graph]], [[Slope of a Position-Time Graph]] |
| [[Stopping Time]] | — | — | — | [[Velocity]], [[Constant Acceleration Equations]], [[Required Deceleration]], [[Stopping Distance]] |
| [[Stopping Distance]] | — | — | — | [[Velocity]], [[Constant Acceleration Equations]], [[Required Deceleration]], [[Stopping Time]] |
| [[Required Deceleration]] | — | — | — | [[Stopping Time]], [[Stopping Distance]], [[Constant Acceleration Equations]], [[Deceleration Phase]], [[Braking Torque]] |
| [[Motion Reversal]] | — | — | — | [[Velocity]], [[Acceleration]], [[Position-Time Graph]], [[Positive Direction]] |
| [[Peak Velocity]] | — | — | — | [[Trapezoidal Velocity Profile]], [[Triangular Velocity Profile]], [[Velocity-Time Graph]], [[Move Time]] |
| [[Peak Acceleration]] | — | — | — | [[Acceleration]], [[Trapezoidal Velocity Profile]], [[S-Curve Motion Profile]], [[Acceleration Torque]] |

---

## Motion Profiles

Planned motion as a function of time — the language of machine motion control.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Motion Profile]] | — | — | — | [[Trapezoidal Velocity Profile]], [[Triangular Velocity Profile]], [[S-Curve Motion Profile]], [[Velocity-Time Graph]], [[Move Time]] |
| [[Trapezoidal Velocity Profile]] | — | — | — | [[Motion Profile]], [[Acceleration Phase]], [[Constant Velocity Phase]], [[Deceleration Phase]], [[Peak Velocity]], [[Move Time]], [[Required Motor Torque]] |
| [[Triangular Velocity Profile]] | — | — | — | [[Motion Profile]], [[Trapezoidal Velocity Profile]], [[Peak Velocity]], [[Move Time]] |
| [[S-Curve Motion Profile]] | — | — | — | [[Motion Profile]], [[Jerk]], [[Jerk-Limited Motion]], [[Trapezoidal Velocity Profile]], [[Motion Profile Continuity]] |
| [[Jerk]] | — | — | — | [[Acceleration]], [[S-Curve Motion Profile]], [[Motion Profile Continuity]], [[Jerk-Limited Motion]] |
| [[Acceleration Phase]] | — | — | — | [[Trapezoidal Velocity Profile]], [[Acceleration]], [[Required Motor Torque]], [[Acceleration Torque]] |
| [[Constant Velocity Phase]] | — | — | — | [[Trapezoidal Velocity Profile]], [[Velocity]], [[Motor Torque]] |
| [[Deceleration Phase]] | — | — | — | [[Trapezoidal Velocity Profile]], [[Negative Acceleration]], [[Braking Torque]], [[Required Deceleration]] |
| [[Move Time]] | — | — | — | [[Motion Profile]], [[Cycle Time]], [[Trapezoidal Velocity Profile]], [[Peak Velocity]], [[Peak Acceleration]] |
| [[Dwell Time]] | — | — | — | [[Cycle Time]], [[Move Time]], [[Indexing Motion]] |
| [[Cycle Time]] | — | — | — | [[Move Time]], [[Dwell Time]], [[Duty Cycle]], [[RMS Torque]] |
| [[Indexing Motion]] | — | — | — | [[Motion Profile]], [[Cycle Time]], [[Trapezoidal Velocity Profile]], [[Dwell Time]] |
| [[Motion Profile Continuity]] | — | — | — | [[Jerk]], [[S-Curve Motion Profile]], [[Jerk-Limited Motion]] |
| [[Jerk-Limited Motion]] | — | — | — | [[Jerk]], [[S-Curve Motion Profile]], [[Motion Profile Continuity]] |

---

## Coordinate Systems and Vectors

Building blocks for expressing position, force, and motion in any direction.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Scalar and Vector]] | — | — | — | [[Vector Component]], [[Unit Vector]], [[Position Vector]] — *L4 on-ramp: scalar vs vector, magnitude–direction form* |
| [[Forward Kinematics]] | — | — | — | [[Coordinate Frames]], [[2D Rotation Matrix]], [[Position Vector]], [[Composing Transformations]] — *L5 synthesis: base translation + rotated offset* |
| [[Reference Frame]] | — | — | — | [[Inertial Reference Frame]], [[Moving Reference Frame]], [[Coordinate Axis]], [[Position Vector]], [[Relative Position]], [[Positive Direction]] |
| [[Inertial Reference Frame]] | — | — | — | [[Reference Frame]], [[Newton's First Law]], [[Newton's Second Law]] |
| [[Moving Reference Frame]] | — | — | — | [[Reference Frame]], [[Relative Velocity]], [[Relative Acceleration]] |
| [[Coordinate Axis]] | — | — | — | [[Reference Frame]], [[Vector Component]], [[Unit Vector]], [[Positive Direction]] |
| [[Vector Component]] | — | — | — | [[Coordinate Axis]], [[Resultant Vector]], [[Unit Vector]] |
| [[Resultant Vector]] | — | — | — | [[Vector Component]], [[Net Force]], [[Unit Vector]] |
| [[Unit Vector]] | — | — | — | [[Vector Component]], [[Coordinate Axis]], [[Position Vector]] |
| [[Position Vector]] | — | — | — | [[Unit Vector]], [[Reference Frame]], [[Relative Position]], [[Velocity Vector]] |
| [[Velocity Vector]] | — | — | — | [[Position Vector]], [[Velocity]], [[Acceleration Vector]] |
| [[Acceleration Vector]] | — | — | — | [[Velocity Vector]], [[Acceleration]], [[Net Force]] |

---

## Force Concepts for Dynamics

The forces that appear in equations of motion for machines and mechanisms.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Force]] | — | — | — | [[Net Force]], [[Newton's Second Law]], [[Newton's First Law]], [[Free Body Diagram (Dynamics)]] |
| [[Net Force]] | — | — | — | [[Force]], [[Newton's Second Law]], [[Equation of Motion]], [[Resultant Vector]] |
| [[Mass]] | — | — | — | [[Weight]], [[Newton's Second Law]], [[Mass Moment of Inertia]], [[Reflected Inertia]], [[Center of Mass]] |
| [[Weight]] | — | — | — | [[Mass]], [[Gravitational Potential Energy]], [[Normal Force]], [[Static Deflection]] |
| [[Normal Force]] | — | — | — | [[Weight]], [[Friction Force]], [[Static Friction]], [[Kinetic Friction]] |
| [[Friction Force]] | — | — | — | [[Normal Force]], [[Static Friction]], [[Kinetic Friction]], [[Dynamic Load]] |
| [[Static Friction]] | — | — | — | [[Friction Force]], [[Normal Force]], [[Kinetic Friction]] |
| [[Kinetic Friction]] | — | — | — | [[Friction Force]], [[Normal Force]], [[Static Friction]] |
| [[Tension Force]] | — | — | — | [[Cable Constraint]], [[Newton's Third Law]], [[Free Body Diagram (Dynamics)]] |
| [[Spring Force]] | — | — | — | [[Linear Spring]], [[Spring Stiffness]], [[Elastic Potential Energy]] |
| [[Damping Force]] | — | — | — | [[Viscous Damper]], [[Damping Coefficient]], [[Damping Ratio]] |
| [[Dynamic Load]] | — | — | — | [[Dynamic Load Factor]], [[Acceleration Load]], [[Braking Load]], [[Impact Load]], [[Vibration Load]] |

---

## Newton's Laws and Translational Kinetics

Applying Newton's laws to translating bodies — the core of dynamic analysis.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Newton's First Law]] | — | — | — | [[Inertial Reference Frame]], [[Net Force]], [[Equation of Motion]] |
| [[Newton's Second Law]] | — | — | — | [[Net Force]], [[Mass]], [[Acceleration]], [[Equation of Motion]], [[Newton's First Law]], [[Newton's Third Law]] |
| [[Newton's Third Law]] | — | — | — | [[Newton's Second Law]], [[Joint Reaction Force]], [[Tension Force]] |
| [[Equation of Motion]] | — | — | — | [[Newton's Second Law]], [[Net Force]], [[Mass]], [[Acceleration]], [[Free Body Diagram (Dynamics)]], [[Lumped Parameter Model]] |
| [[Center of Mass]] | — | — | — | [[Mass]], [[Translational Kinetic Energy]], [[Equation of Motion]] |
| [[Inertial Force]] | — | — | — | [[Mass]], [[Acceleration]], [[Newton's Second Law]], [[Dynamic Support Reaction]], [[Acceleration Load]] |
| [[Dynamic Support Reaction]] | — | — | — | [[Inertial Force]], [[Normal Force]], [[Acceleration Load]] |
| [[Acceleration-Limited Force]] | — | — | — | [[Newton's Second Law]], [[Required Actuator Force]], [[Required Motor Torque]], [[Peak Acceleration]] |

---

## Angular Motion

Rotational kinematics — position, velocity, and acceleration on a spinning body.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Radian Measure]] | — | — | — | [[Angular Position]], [[Angular Velocity]], [[Angular Acceleration]] |
| [[Angular Position]] | — | — | — | [[Radian Measure]], [[Angular Displacement]], [[Angular Velocity]] |
| [[Angular Displacement]] | — | — | — | [[Angular Position]], [[Angular Velocity]], [[Constant Acceleration Equations]] |
| [[Angular Velocity]] | — | — | — | [[Angular Position]], [[Angular Acceleration]], [[Tangential Velocity]], [[Rotational Power]], [[No-Slip Rolling Condition]] |
| [[Angular Acceleration]] | — | — | — | [[Angular Velocity]], [[Torque]], [[Mass Moment of Inertia]], [[Rotational Equation of Motion]], [[Tangential Acceleration]] |
| [[Tangential Velocity]] | — | — | — | [[Angular Velocity]], [[No-Slip Rolling Condition]], [[Gear Ratio]], [[Centripetal Acceleration]] |
| [[Tangential Acceleration]] | — | — | — | [[Angular Acceleration]], [[Centripetal Acceleration]] |
| [[Centripetal Acceleration]] | — | — | — | [[Tangential Acceleration]], [[Centripetal Load]], [[Tangential Velocity]] |
| [[No-Slip Rolling Condition]] | — | — | — | [[Tangential Velocity]], [[Angular Velocity]], [[Gear Ratio]] |

---

## Torque and Rotational Kinetics

Applying Newton's second law in the rotational sense — moment, inertia, angular acceleration.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Moment of a Force]] | — | — | — | [[Moment Arm]], [[Torque]], [[Net Torque]] |
| [[Moment Arm]] | — | — | — | [[Moment of a Force]], [[Torque]] |
| [[Torque]] | — | — | — | [[Moment of a Force]], [[Net Torque]], [[Angular Acceleration]], [[Mass Moment of Inertia]], [[Rotational Equation of Motion]] |
| [[Net Torque]] | — | — | — | [[Torque]], [[Rotational Equation of Motion]], [[Newton's Second Law]] |
| [[Mass Moment of Inertia]] | — | — | — | [[Torque]], [[Rotational Equation of Motion]], [[Parallel Axis Theorem for Mass Moment of Inertia]], [[Reflected Inertia]], [[Rotational Kinetic Energy]] |
| [[Parallel Axis Theorem for Mass Moment of Inertia]] | — | — | — | [[Mass Moment of Inertia]] |
| [[Rotational Equation of Motion]] | — | — | — | [[Torque]], [[Net Torque]], [[Mass Moment of Inertia]], [[Angular Acceleration]], [[Acceleration Torque]], [[Lumped Parameter Model]] |
| [[Acceleration Torque]] | — | — | — | [[Rotational Equation of Motion]], [[Angular Acceleration]], [[Required Motor Torque]], [[Mass Moment of Inertia]], [[Acceleration Phase]] |
| [[Braking Torque]] | — | — | — | [[Rotational Equation of Motion]], [[Deceleration Phase]], [[Angular Velocity]], [[Required Motor Torque]] |

---

## Work, Energy, and Power

Energy methods for evaluating motion without tracking every force.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Work]] | — | — | — | [[Translational Kinetic Energy]], [[Work-Energy Principle]], [[Force]], [[Displacement]] |
| [[Translational Kinetic Energy]] | — | — | — | [[Work]], [[Work-Energy Principle]], [[Mass]], [[Velocity]], [[Center of Mass]] |
| [[Rotational Kinetic Energy]] | — | — | — | [[Mass Moment of Inertia]], [[Angular Velocity]], [[Work-Energy Principle]] |
| [[Gravitational Potential Energy]] | — | — | — | [[Weight]], [[Work-Energy Principle]], [[Static Deflection]] |
| [[Elastic Potential Energy]] | — | — | — | [[Spring Force]], [[Spring Stiffness]], [[Work-Energy Principle]], [[Energy Absorption]] |
| [[Work-Energy Principle]] | — | — | — | [[Work]], [[Translational Kinetic Energy]], [[Rotational Kinetic Energy]], [[Gravitational Potential Energy]], [[Elastic Potential Energy]] |
| [[Mechanical Power]] | — | — | — | [[Work]], [[Force]], [[Velocity]], [[Rotational Power]], [[Efficiency]] |
| [[Rotational Power]] | — | — | — | [[Torque]], [[Angular Velocity]], [[Mechanical Power]], [[Required Motor Torque]] |
| [[Efficiency]] | — | — | — | [[Mechanical Power]], [[Rotational Power]], [[Gear Ratio]] |

---

## Momentum, Impulse, and Impact

Short-duration force events — stopping, collisions, and sudden loads.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Linear Momentum]] | — | — | — | [[Mass]], [[Velocity]], [[Impulse]], [[Impulse-Momentum Principle]] |
| [[Impulse]] | — | — | — | [[Force]], [[Time Interval]], [[Linear Momentum]], [[Impulse-Momentum Principle]], [[Average Impact Force]] |
| [[Impulse-Momentum Principle]] | — | — | — | [[Impulse]], [[Linear Momentum]] |
| [[Average Impact Force]] | — | — | — | [[Impulse]], [[Impact Duration]], [[Peak Impact Force]] |
| [[Peak Impact Force]] | — | — | — | [[Average Impact Force]], [[Impact Duration]], [[Impact Load]] |
| [[Impact Duration]] | — | — | — | [[Average Impact Force]], [[Impulse]] |
| [[Energy Absorption]] | — | — | — | [[Translational Kinetic Energy]], [[Impact Load]], [[Elastic Potential Energy]], [[Dynamic Deflection]] |

---

## Springs, Dampers, and Compliance

Elastic and dissipative elements that appear in every real machine.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Linear Spring]] | — | — | — | [[Spring Force]], [[Spring Stiffness]], [[Mechanical Compliance]], [[Mass-Spring-Damper System]] |
| [[Spring Stiffness]] | — | — | — | [[Linear Spring]], [[Spring Force]], [[Static Deflection]], [[Natural Frequency]] |
| [[Viscous Damper]] | — | — | — | [[Damping Force]], [[Damping Coefficient]], [[Mass-Spring-Damper System]] |
| [[Damping Coefficient]] | — | — | — | [[Viscous Damper]], [[Damping Ratio]], [[Damping Force]] |
| [[Mechanical Compliance]] | — | — | — | [[Linear Spring]], [[Spring Stiffness]], [[Static Deflection]], [[Dynamic Deflection]] |
| [[Static Deflection]] | — | — | — | [[Spring Stiffness]], [[Gravitational Potential Energy]], [[Mechanical Compliance]], [[Natural Frequency]] |
| [[Dynamic Deflection]] | — | — | — | [[Static Deflection]], [[Dynamic Load Factor]], [[Mass-Spring-Damper System]], [[Energy Absorption]] |

---

## Vibration

Single-DOF oscillatory behavior — free, forced, damped. Gateway to vibration isolation and resonance avoidance.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Single Degree of Freedom System]] | — | — | — | [[Mass-Spring-Damper System]], [[Natural Frequency]], [[Damping Ratio]], [[Lumped Parameter Model]] |
| [[Mass-Spring-Damper System]] | — | — | — | [[Single Degree of Freedom System]], [[Natural Frequency]], [[Damping Ratio]], [[Free Vibration]], [[Forced Vibration]], [[Equation of Motion]] |
| [[Free Vibration]] | — | — | — | [[Mass-Spring-Damper System]], [[Natural Frequency]], [[Damping Ratio]], [[Transient Response]] |
| [[Forced Vibration]] | — | — | — | [[Mass-Spring-Damper System]], [[Resonance]], [[Natural Frequency]] |
| [[Natural Frequency]] | — | — | — | [[Mass-Spring-Damper System]], [[Spring Stiffness]], [[Mass]], [[Resonance]], [[Second-Order System]] |
| [[Damping Ratio]] | — | — | — | [[Damping Coefficient]], [[Natural Frequency]], [[Critical Damping]], [[Second-Order System]] |
| [[Critical Damping]] | — | — | — | [[Damping Ratio]], [[Transient Response]] |
| [[Resonance]] | — | — | — | [[Natural Frequency]], [[Forced Vibration]], [[Vibration Isolation]] |
| [[Transient Response]] | — | — | — | [[Natural Frequency]], [[Damping Ratio]], [[Critical Damping]], [[Overshoot]], [[Settling Time]] |
| [[Vibration Isolation]] | — | — | — | [[Resonance]], [[Natural Frequency]], [[Vibration Load]], [[Mechanical Compliance]] |

---

## Actuator and Motor Dynamics

Sizing actuators and motors for a given motion profile — the design output of dynamics.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Actuator Force]] | — | — | — | [[Required Actuator Force]], [[Newton's Second Law]], [[Equation of Motion]] |
| [[Required Actuator Force]] | — | — | — | [[Actuator Force]], [[Newton's Second Law]], [[Acceleration-Limited Force]], [[Motion Profile]] |
| [[Motor Torque]] | — | — | — | [[Required Motor Torque]], [[Torque]], [[Angular Velocity]], [[Continuous Torque]], [[Peak Torque]] |
| [[Required Motor Torque]] | — | — | — | [[Motor Torque]], [[Acceleration Torque]], [[Braking Torque]], [[RMS Torque]], [[Reflected Inertia]] |
| [[Continuous Torque]] | — | — | — | [[Motor Torque]], [[RMS Torque]], [[Duty Cycle]] |
| [[Peak Torque]] | — | — | — | [[Motor Torque]], [[Acceleration Torque]], [[Required Motor Torque]] |
| [[RMS Torque]] | — | — | — | [[Required Motor Torque]], [[Continuous Torque]], [[Duty Cycle]], [[Cycle Time]] |
| [[Reflected Inertia]] | — | — | — | [[Mass Moment of Inertia]], [[Gear Ratio]], [[Required Motor Torque]] |
| [[Gear Ratio]] | — | — | — | [[Reflected Inertia]], [[Efficiency]], [[Tangential Velocity]], [[No-Slip Rolling Condition]], [[Mechanical Advantage]] |
| [[Duty Cycle]] | — | — | — | [[Cycle Time]], [[RMS Torque]], [[Continuous Torque]] |

---

## Dynamic Load Transfer into Mechanics

Translating a motion profile into structural loads — the bridge between dynamics and machine design.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Acceleration Load]] | — | — | — | [[Newton's Second Law]], [[Inertial Force]], [[Mass]], [[Acceleration Phase]], [[Dynamic Load]] |
| [[Braking Load]] | — | — | — | [[Braking Torque]], [[Deceleration Phase]], [[Dynamic Load]] |
| [[Centripetal Load]] | — | — | — | [[Centripetal Acceleration]], [[Mass]], [[Dynamic Load]] |
| [[Impact Load]] | — | — | — | [[Peak Impact Force]], [[Dynamic Load]], [[Energy Absorption]] |
| [[Vibration Load]] | — | — | — | [[Dynamic Load]], [[Mass-Spring-Damper System]], [[Vibration Isolation]] |
| [[Dynamic Load Factor]] | — | — | — | [[Dynamic Load]], [[Static Deflection]], [[Dynamic Deflection]] |
| [[Peak Dynamic Load]] | — | — | — | [[Dynamic Load Factor]], [[Acceleration Load]], [[Peak Acceleration]] |
| [[Dynamic Load Path]] | — | — | — | [[Dynamic Load]], [[Joint Reaction Force]] |
| [[Dynamic Factor of Safety]] | — | — | — | [[Dynamic Load Factor]], [[Peak Dynamic Load]] |

---

## Linkage Analysis and Mobility

MECA 290 Module 1 (Lectures 2–3): describing a real mechanism as links and joints, counting its mobility, and classifying it. The load-bearing gap in the current vault — L2/L3 have almost nothing to link into yet.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Link]] | — | — | — | [[Linkage Diagram]], [[Kinematic Pair]], [[Degrees of Freedom]], [[Rigid Body]] |
| [[Kinematic Pair]] | — | — | — | [[Link]], [[Degrees of Freedom]], [[Grübler–Kutzbach Equation]], [[Full Joint and Half Joint]], [[Pin Joint]], [[Slider Joint]], [[Joint Reaction Force]] |
| [[Full Joint and Half Joint]] | — | — | — | [[Kinematic Pair]], [[Grübler–Kutzbach Equation]], [[Degrees of Freedom]] |
| [[Linkage Diagram]] | — | — | — | [[Link]], [[Kinematic Pair]], [[Mobility]], [[Free Body Diagram]], [[Grübler–Kutzbach Equation]] |
| [[Grübler–Kutzbach Equation]] | — | — | — | [[Degrees of Freedom]], [[Mobility]], [[Full Joint and Half Joint]], [[Four-Bar Linkage]], [[Linkage Diagram]] |
| [[Mobility]] | — | — | — | [[Grübler–Kutzbach Equation]], [[Degrees of Freedom]], [[Kinematic Constraint]], [[Four-Bar Linkage]] |
| [[Four-Bar Linkage]] | — | — | — | [[Grübler–Kutzbach Equation]], [[Mobility]], [[Linkage Diagram]], [[Degrees of Freedom]] |

> [!note] Naming: [[Linkage Diagram]] vs the existing Kinematic Diagram
> `[[Linkage Diagram]]` is the mechanism skeleton (links + joints → mobility) taught in Lecture 3. It is deliberately **not** titled "Kinematic Diagram" — that title is already used by `Advanced Motion/Kinematic Diagram` for the acceleration/kinetic diagram drawn beside an FBD. Two different concepts; both pages coexist.

> [!note] Cross-references into existing pages (add when drafting)
> - `Advanced Motion/Degrees of Freedom` → link out to [[Grübler–Kutzbach Equation]], [[Mobility]], [[Kinematic Pair]], [[Four-Bar Linkage]] (it already name-drops "Grübler formula" and "four-bar linkage" in prose, unlinked).
> - `Advanced Motion/Kinematic Diagram` → add a disambiguation link to [[Linkage Diagram]].
> - `Mechanics/Free Body Diagram` → link out to [[Linkage Diagram]], [[Static Equilibrium]], [[Joint Reaction Force]].

---

## Mechanisms and Constrained Motion

How joints and linkages impose relationships between velocities and forces.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Kinematic Constraint]] | — | — | — | [[Pin Joint]], [[Slider Joint]], [[Cable Constraint]], [[Linkage Constraint]] |
| [[Pin Joint]] | — | — | — | [[Kinematic Constraint]], [[Joint Reaction Force]], [[Newton's Third Law]] |
| [[Slider Joint]] | — | — | — | [[Kinematic Constraint]], [[Joint Reaction Force]] |
| [[Cable Constraint]] | — | — | — | [[Tension Force]], [[Kinematic Constraint]], [[Velocity Constraint Equation]] |
| [[Linkage Constraint]] | — | — | — | [[Kinematic Constraint]], [[Velocity Constraint Equation]], [[Acceleration Constraint Equation]] |
| [[Velocity Constraint Equation]] | — | — | — | [[Kinematic Constraint]], [[Relative Velocity]], [[Linkage Constraint]] |
| [[Acceleration Constraint Equation]] | — | — | — | [[Velocity Constraint Equation]], [[Relative Acceleration]] |
| [[Mechanical Advantage]] | — | — | — | [[Gear Ratio]], [[Torque]], [[Force]] |
| [[Joint Reaction Force]] | — | — | — | [[Newton's Third Law]], [[Pin Joint]], [[Slider Joint]], [[Dynamic Load Path]], [[Static Equilibrium]], [[Linkage Diagram]] |
| [[Static Equilibrium]] | — | — | — | [[Free Body Diagram]], [[Joint Reaction Force]], [[Support Reactions]] — *L3; may instead belong in the Mechanics tracker* |

---

## Control-Ready Dynamics

Bridging dynamics and controls — models, state variables, and response characteristics.

| Page | Built | Reviewed | Published | Connects to |
| ---- | ----- | -------- | --------- | ----------- |
| [[Lumped Parameter Model]] | — | — | — | [[Mass-Spring-Damper System]], [[Single Degree of Freedom System]], [[State Variable]], [[Equation of Motion]] |
| [[Input Variable]] | — | — | — | [[Output Variable]], [[State Variable]], [[Transfer Function]] |
| [[Output Variable]] | — | — | — | [[Input Variable]], [[State Variable]], [[Transfer Function]] |
| [[State Variable]] | — | — | — | [[Lumped Parameter Model]], [[Input Variable]], [[Output Variable]], [[First-Order System]], [[Second-Order System]] |
| [[First-Order System]] | — | — | — | [[State Variable]], [[Time Constant]], [[Transfer Function]] |
| [[Second-Order System]] | — | — | — | [[State Variable]], [[Natural Frequency]], [[Damping Ratio]], [[Transfer Function]], [[Mass-Spring-Damper System]] |
| [[Time Constant]] | — | — | — | [[First-Order System]], [[Settling Time]] |
| [[Settling Time]] | — | — | — | [[Transient Response]], [[Time Constant]], [[Overshoot]] |
| [[Overshoot]] | — | — | — | [[Transient Response]], [[Damping Ratio]], [[Settling Time]] |
| [[Transfer Function]] | — | — | — | [[Input Variable]], [[Output Variable]], [[First-Order System]], [[Second-Order System]] |

---

## Canonical example index

Pages where the in-class platforms will headline the *Examples and Non-Examples* section. Fill in as drafted — this is a coverage check, not a separate phase.

| Platform | Headline example lives on |
| -------- | ------------------------- |
| XY gantry / pick-and-place | [[Motion Profile]], [[Trapezoidal Velocity Profile]], [[Required Motor Torque]], [[Reflected Inertia]], [[Gear Ratio]], [[Acceleration Phase]], [[Move Time]], [[Cycle Time]] |
| Conveyor indexer | [[Indexing Motion]], [[Cycle Time]], [[Dwell Time]], [[Trapezoidal Velocity Profile]], [[Duty Cycle]], [[RMS Torque]] |
| Rotary table | [[Angular Velocity]], [[Angular Acceleration]], [[Mass Moment of Inertia]], [[Rotational Equation of Motion]], [[Acceleration Torque]], [[Braking Torque]] |
| Lead-screw actuator | [[Gear Ratio]], [[Reflected Inertia]], [[Required Actuator Force]], [[Mechanical Advantage]], [[Efficiency]] |
| Mobile robot | [[No-Slip Rolling Condition]], [[Angular Velocity]], [[Velocity Constraint Equation]], [[Relative Velocity]] |
| Vibrating machine | [[Mass-Spring-Damper System]], [[Natural Frequency]], [[Damping Ratio]], [[Resonance]], [[Vibration Isolation]] |

---

## Progress Summary

| Section | Total | Built | Reviewed | Published |
| ------- | ----- | ----- | -------- | --------- |
| Motion Foundations | 19 | 19 | 0 | 0 |
| Motion Graphs | 9 | 0 | 0 | 0 |
| Linear Motion Equations | 11 | 0 | 0 | 0 |
| Motion Profiles | 14 | 0 | 0 | 0 |
| Coordinate Systems and Vectors | 12 | 0 | 0 | 0 |
| Force Concepts for Dynamics | 12 | 0 | 0 | 0 |
| Newton's Laws and Translational Kinetics | 8 | 0 | 0 | 0 |
| Angular Motion | 9 | 0 | 0 | 0 |
| Torque and Rotational Kinetics | 9 | 0 | 0 | 0 |
| Work, Energy, and Power | 9 | 0 | 0 | 0 |
| Momentum, Impulse, and Impact | 7 | 0 | 0 | 0 |
| Springs, Dampers, and Compliance | 7 | 0 | 0 | 0 |
| Vibration | 10 | 0 | 0 | 0 |
| Actuator and Motor Dynamics | 10 | 0 | 0 | 0 |
| Dynamic Load Transfer into Mechanics | 9 | 0 | 0 | 0 |
| Linkage Analysis and Mobility | 7 | 0 | 0 | 0 |
| Mechanisms and Constrained Motion | 10 | 0 | 0 | 0 |
| Control-Ready Dynamics | 10 | 0 | 0 | 0 |
| **Total** | **182** | **19** | **0** | **0** |
