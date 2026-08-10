---
tags:
  - dynamics
  - video-resources
  - youtube
  - draft
---

# Dynamics YouTube Resource Recommendations — First Pass

Purpose: candidate YouTube resources for the Dynamics section of the Obsidian vault.  
Audience: second-year Mechatronics and Robotics students with Physics 1 background.  
Selection bias: clear visuals, conceptual explanations, robotics relevance, and reusable channel value.

---

## Recommended New Approved Channels for Dynamics

### Modern Robotics / Northwestern Robotics
- **Channel:** https://www.youtube.com/@ModernRobotics
- **Why:** Best-fit canonical source for robotics-adjacent frame math, rigid-body motion, transformations, forward kinematics, Jacobians, singularities, and nonholonomic mobile robot ideas.
- **Best use:** Primary source for Phase 1 frame math and Phase 8 mechanism/robot kinematics.
- **Caution:** Some videos are dense and intended as supplements to the Modern Robotics text; best used after a student has already seen a simpler conceptual intro.

### CPPMechEngTutorials
- **Channel:** https://www.youtube.com/@CPPMechEngTutorials
- **Why:** Strong university-style engineering mechanics source with short introductory vector dynamics videos and longer dynamics playlists.
- **Best use:** Secondary lecture-style support for engineering dynamics topics.
- **Caution:** Less animation-heavy; better as reinforcement or worked-example support.

### Michel van Biezen
- **Channel:** https://www.youtube.com/@MichelvanBiezen
- **Why:** Huge physics/mechanics library with many short example-driven videos. Useful as a gap-filler when polished engineering explainers do not exist.
- **Best use:** Supplemental examples for relative motion, projectile motion, rolling motion, momentum, and rotational dynamics.
- **Caution:** More physics-classroom style than engineering-design style.

### Learn Engineering
- **Channel:** https://www.youtube.com/@LearnEngineering
- **Why:** Strong visual intuition and engineering context. Good for “why this matters” and physical system intuition.
- **Best use:** Introductory motivation videos for rotational motion, gyroscopes, mechanisms, and mechanical systems.
- **Caution:** Usually not enough mathematical depth to stand alone.

### Branch Education
- **Channel:** https://www.youtube.com/@BranchEducation
- **Why:** Excellent visuals and engineering intuition. Useful where physical mechanism visualization matters.
- **Best use:** Conceptual primer or “visual intuition” supplement.
- **Caution:** Not a comprehensive dynamics course.

### Steve Brunton
- **Channel:** https://www.youtube.com/@Eigensteve
- **Why:** Strong bridge from dynamics into systems, modeling, and controls.
- **Best use:** Further-exploration links for linearization, equilibrium, state-space thinking, and nonlinear systems.
- **Caution:** Often above second-year level; use selectively.

---

# Topic-to-Video Mapping — First Pass

## Phase 1 — Vector and Frame Math

### [[Degrees of Freedom]]
**Primary**
- Modern Robotics — *Chapter 2.1: Degrees of Freedom of a Rigid Body*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Also consider**
- Modern Robotics — *Chapter 2.2: Degrees of Freedom of a Robot*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Primary robotics-context reference.

---

### [[Coordinate Frames]]
**Primary**
- Modern Robotics — *Chapter 3: Introduction to Rigid-Body Motions*  
  https://www.youtube.com/watch?v=29LhXWjn7Pc

**Also consider**
- Modern Robotics — *Chapter 3: Rigid-Body Motions playlist*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc

**Vault role:** Primary robotics-frame reference. Good for linking body frame vs space frame.

---

### [[2D Rotation Matrix]] / [[3D Rotation Matrix]]
**Primary**
- Modern Robotics — *Chapter 3.2.1: Rotation Matrices, Part 1 of 2*  
  https://www.youtube.com/watch?v=OZucG1DY_sY

**Also consider**
- Modern Robotics — *Chapter 3: Rigid-Body Motions playlist*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc

**Vault role:** Primary robotics-style explanation of rotation matrices.

---

### [[Angular Velocity Vector]]
**Primary**
- Modern Robotics — *Chapter 3.2.2: Angular Velocities*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc

**Also consider**
- Modern Robotics — *Chapter 3.2.3: Exponential Coordinates of Rotation*  
  https://www.youtube.com/watch?v=WHn9xJl43nY

**Vault role:** Advanced/robotics bridge. Use after a simpler intro to angular velocity.

---

### [[Homogeneous Transformation]]
**Primary**
- Modern Robotics — *Chapter 3.3.1: Homogeneous Transformation Matrices*  
  https://www.youtube.com/watch?v=vlb3P7arbkU

**Also consider**
- Modern Robotics — *Chapter 3: Rigid-Body Motions playlist*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc

**Vault role:** Essential primary source for transformation matrices and rigid-body configuration.

---

### [[Composing Transformations]]
**Primary**
- Modern Robotics — *Chapter 3.3.1: Homogeneous Transformation Matrices*  
  https://www.youtube.com/watch?v=vlb3P7arbkU

**Also consider**
- Modern Robotics — *Chapter 4.1.1 / 4.1.2 Product of Exponentials Formula*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq00efLcgMcG1m4k5CKlgRcGh

**Vault role:** Use Modern Robotics for rigorous composition ideas; supplement with a simpler in-house worked example.

---

## Phase 2 — Particle Kinematics

### [[Projectile Motion]]
**Primary**
- CPPMechEngTutorials — *Vector Dynamics: Introduction to Projectile Motion*  
  https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0

**Also consider**
- Michel van Biezen — search within channel for projectile motion examples  
  https://www.youtube.com/@MichelvanBiezen

**Vault role:** Review/lookup topic. Keep light and example-oriented.

---

### [[Curvilinear Motion]]
**Primary**
- CPPMechEngTutorials — *Vector Dynamics: Introduction to Curvilinear Motion*  
  https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0

**Also consider**
- CPPMechEngTutorials — Engineering Dynamics playlist, normal/tangential and frame-based motion topics  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Vault role:** Good topic for connecting path coordinates to robotics/path-following examples.

---

### [[Relative Motion]]
**Primary**
- CPPMechEngTutorials — *Vector Dynamics: Introduction to Relative Motion*  
  https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0

**Also consider**
- Michel van Biezen — *PHYSICS 7 RELATIVE VELOCITY playlist*  
  https://www.youtube.com/playlist?list=PLX2gX-ftPVXXg8aFq3rjf5DcTkyovxpDS
- CPPMechEngTutorials — *Relative Motion Examples - with deep explanations*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Vault role:** High-priority bottleneck topic. Use one engineering explanation and one physics-style example series.

---

## Phase 3 — Particle Kinetics

### [[Newton's Second Law (Vector Form)]]
**Primary**
- CPPMechEngTutorials — *Engineering Dynamics - Newton's 2nd law applied to particles*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Also consider**
- Organic Chemistry Tutor — continue using for Physics 1 reinforcement.

**Vault role:** Bridge from Physics 1 to engineering equation-of-motion thinking.

---

### [[Equation of Motion]]
**Primary**
- CPPMechEngTutorials — *Equations of Motion Explained: Newton to Euler | Work-Energy & Impulse-Momentum Examples*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Also consider**
- Steve Brunton — selected nonlinear/system modeling videos for advanced extensions  
  https://www.youtube.com/@Eigensteve

**Vault role:** Canonical dynamics page. Good place to introduce the self-balancing two-wheeled robot as a preview example.

---

## Phase 4 — Work, Energy, Power

### [[Work-Energy Theorem]]
**Primary**
- CPPMechEngTutorials — *Vector Dynamics: Introduction to Work-Energy Principle*  
  https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0

**Also consider**
- CPPMechEngTutorials — *Energy and Momentum in Rigid-Body Dynamics | Workout Example*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Vault role:** Use as the main transition from force-based thinking to energy methods.

---

### [[Mechanical Power]]
**Primary**
- Learn Engineering — search channel for mechanical systems / power transmission context  
  https://www.youtube.com/@LearnEngineering

**Also consider**
- Engineering Mindset, if an existing video fits the page’s physical examples.

**Vault role:** Use a machine/system video rather than only algebraic definitions.

---

## Phase 5 — Impulse and Momentum

### [[Impulse-Momentum Theorem]]
**Primary**
- CPPMechEngTutorials — *Vector Dynamics: Introduction to Linear Impulse & Momentum*  
  https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0

**Also consider**
- CPPMechEngTutorials — *Newton/Euler, Work-Energy & Impulse-Momentum | Key Derivations Explained*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Vault role:** Strong candidate for formal engineering explanation.

---

### [[Conservation of Linear Momentum]]
**Primary**
- Michel van Biezen — channel search for conservation of momentum examples  
  https://www.youtube.com/@MichelvanBiezen

**Also consider**
- Khan Academy or Organic Chemistry Tutor for a softer Physics 1 review.

**Vault role:** Keep practical and example-based.

---

## Phase 6 — Rigid-Body Kinematics

### [[Translation vs Rotation]]
**Primary**
- CPPMechEngTutorials — *Motions of a Rigid Body - Translation, Pure Rotation about a Fixed Axis, Planar Motion*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Also consider**
- Learn Engineering — use for visual intuition if a concise rotational-motion explainer is found.

**Vault role:** Foundation page for rigid-body motion.

---

### [[Rolling Without Slipping]]
**Primary**
- Michel van Biezen — *Physics 11.1 Rigid Body Rotation: Rolling Object on an Incline*  
  https://www.youtube.com/watch?v=cJfynUjTLVU

**Also consider**
- CPPMechEngTutorials — rigid body relative motion / instantaneous center playlist topics  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX
- Animations for Physics and Astronomy — *Moment of Inertia and Rolling Down a Ramp*  
  https://www.youtube.com/watch?v=7mxV6f5nuJY

**Vault role:** High-priority visual intuition topic. Use animation plus engineering example.

---

### [[Instantaneous Center of Zero Velocity]]
**Primary**
- CPPMechEngTutorials — *How to Locate the Instantaneous Center of a Rigid Body*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Also consider**
- CPPMechEngTutorials — *Instantaneous Center of Rotation - Rigid Bodies*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Vault role:** Strong engineering-dynamics source. Link directly from rolling and relative velocity pages.

---

### [[Relative Velocity on a Rigid Body]]
**Primary**
- CPPMechEngTutorials — *Rigid Body Relative Motion - Velocity and Acceleration*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Also consider**
- Engineering Curiosity — *General Plane Motion: Relative Velocity: Rolling without Slipping*  
  https://www.youtube.com/watch?v=w4SxmW-Y3-w

**Vault role:** High-priority bottleneck topic.

---

### [[Holonomic and Nonholonomic Constraints]]
**Primary**
- Modern Robotics — *Chapter 13.3.1: Modeling of Nonholonomic Wheeled Mobile Robots*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Also consider**
- Modern Robotics — *Chapter 2.4: Configuration and Velocity Constraints*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Strong robotics-specific application page. Excellent link to self-balancing two-wheeled robot examples.

---

## Phase 7 — Rigid-Body Kinetics

### [[Moment of Inertia (Mass)]]
**Primary**
- Learn Engineering — *Rotational Motion: Torque | Angular Momentum | Moment of Inertia*  
  https://www.youtube.com/watch?v=c5dnHBuXLo4

**Also consider**
- Animations for Physics and Astronomy — *Moment of Inertia and Rolling Down a Ramp*  
  https://www.youtube.com/watch?v=7mxV6f5nuJY

**Vault role:** Start with visual intuition, then move into mass distribution and formula tables.

---

### [[Radius of Gyration]]
**Primary**
- Physics Ninja — *Rotation, Angular Momentum, and Moment of Inertia playlist*  
  https://www.youtube.com/playlist?list=PL-mV9m5bis8Hh_NMXocF8TdhWRzjx9BtZ

**Also consider**
- CPPMechEngTutorials if a specific radius-of-gyration example is found.

**Vault role:** Likely supplemental only unless used directly in rigid-body kinetics examples.

---

### [[Rotational Kinetic Energy]]
**Primary**
- CPPMechEngTutorials — *Energy and Momentum in Rigid-Body Dynamics | Workout Example*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Also consider**
- Michel van Biezen / Physics Ninja rolling-object examples.

**Vault role:** Connect directly to rolling without slipping and moment of inertia.

---

### [[Moment Equation for Rigid Bodies]]
**Primary**
- CPPMechEngTutorials — *Newton/Euler, Work-Energy & Impulse-Momentum | Key Derivations Explained*  
  https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX

**Also consider**
- Modern Robotics dynamics videos for advanced robotics connection  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Major bridge to self-balancing robot dynamics.

---

### [[Equilibrium and Stability]]
**Primary**
- Steve Brunton — dynamical systems / stability videos  
  https://www.youtube.com/@Eigensteve

**Also consider**
- Search specific term: “linearization equilibrium stability Brunton”.

**Vault role:** Further exploration / controls bridge. Likely needs in-house scaffolding for second-year students.

---

### [[Linearization About an Equilibrium]]
**Primary**
- Steve Brunton — use selectively from nonlinear systems / dynamics playlists  
  https://www.youtube.com/@Eigensteve

**Also consider**
- APMonitor — *Clear and Correct Explanation of Linearization of Nonlinear Systems*  
  https://www.youtube.com/watch?v=SfbRknFoSZ0

**Vault role:** Advanced bridge topic. Should be paired with a simple pendulum or self-balancing robot example.

---

## Phase 8 — Mechanism and Chain Kinematics

### [[Joint Types]]
**Primary**
- Modern Robotics — use Chapter 2 / robot degrees-of-freedom videos as conceptual support  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** General intro; likely needs diagrams or in-house examples.

---

### [[Joint Space and Task Space]]
**Primary**
- Modern Robotics — *Chapter 2.5: Task Space and Workspace*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Strong robotics vocabulary page.

---

### [[Forward Kinematics]]
**Primary**
- Modern Robotics — *Chapter 4: Forward Kinematics playlist*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq00efLcgMcG1m4k5CKlgRcGh

**Also consider**
- Modern Robotics — *Chapter 4: Forward Kinematics Example*  
  https://www.youtube.com/watch?v=cKHsil0V6Qk

**Vault role:** Primary robotics source. Since DH is deferred, use carefully; emphasize transformation composition first.

---

### [[Inverse Kinematics]]
**Primary**
- Modern Robotics — *Chapter 6: Inverse Kinematics of Open Chains*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Use as advanced reference after FK is established.

---

### [[Workspace and Reach]]
**Primary**
- Modern Robotics — *Chapter 2.5: Task Space and Workspace*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Good fit for 6-axis industrial robot example.

---

### [[Kinematic Singularity]]
**Primary**
- Modern Robotics — *Chapter 5.3: Singularities*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Excellent 6-axis arm example topic.

---

### [[Jacobian (Intro)]]
**Primary**
- Modern Robotics — *Chapter 5.1.1: Space Jacobian* and *Chapter 5.1.2: Body Jacobian*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Also consider**
- Use a simpler in-house intro before linking to Modern Robotics.

**Vault role:** Important but mathematically dense. Best as “what the Jacobian does” before “how to compute it.”

---

## Phase 9 — 3D Rotational Dynamics

### [[Inertia Tensor]]
**Primary**
- Modern Robotics — *Chapter 8.1.3: Understanding the Mass Matrix*  
  https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx

**Vault role:** Stretch topic. May require a custom page before students are ready for external videos.

---

### [[Gyroscopic Effects]]
**Primary**
- Physics Ninja — *Rotation, Angular Momentum, and Moment of Inertia playlist*  
  https://www.youtube.com/playlist?list=PL-mV9m5bis8Hh_NMXocF8TdhWRzjx9BtZ

**Also consider**
- Learn Engineering — rotational motion / gyroscope content  
  https://www.youtube.com/watch?v=c5dnHBuXLo4

**Vault role:** Visual intuition topic. Good for “further exploration” if Phase 9 stays stretch.

---

# First-Pass Priority Queue

Use this order for deeper video curation next:

1. [[Coordinate Frames]]
2. [[Homogeneous Transformation]]
3. [[Relative Motion]]
4. [[Rolling Without Slipping]]
5. [[Angular Velocity Vector]]
6. [[Instantaneous Center of Zero Velocity]]
7. [[Forward Kinematics]]
8. [[Jacobian (Intro)]]
9. [[Holonomic and Nonholonomic Constraints]]
10. [[Linearization About an Equilibrium]]

---

# Notes for Merge into Source List

Suggested additions to **Approved YouTube Channels**:

- Modern Robotics / Northwestern Robotics
- CPPMechEngTutorials
- Michel van Biezen
- Learn Engineering
- Branch Education
- Steve Brunton

Suggested usage policy:

> For Dynamics pages, prefer a three-layer video strategy:
> 1. visual intuition video,
> 2. engineering mechanics explanation or worked example,
> 3. robotics/control bridge where relevant.
>
> Do not force every page to have all three. Use all three only for bottleneck topics such as frames, transformations, relative motion, rolling motion, Jacobians, and linearization.
