---
title: "Physics Simulation Coursework: Rigid Bodies, Constraints, Soft Bodies, and Cloth"
date: 2025-04-01T00:00:00+02:00
draft: false
weight: 8
summary: "A collection of physics simulation coursework projects covering rigid-body dynamics, collision response, constraint-based resolution, finite-element soft-body deformation, and Unity cloth simulation."
tags: ["C++", "Unity", "C#", "Physics Simulation", "Rigid Body Simulation", "Collision Response", "Constraint Solver", "Finite Element Method", "Soft-Body Simulation", "Cloth Simulation", "Mass-Spring System", "Computer Graphics", "Course Project"]
showAuthor: false
---

## Overview

**Physics Simulation Coursework** is a collection of four practical projects completed for a physics simulation course. The projects explored different approaches to simulating physical motion and deformation, ranging from rigid-body collision response to soft-body deformation and cloth simulation. The first practical focused on rigid-body motion and impulse-based collision response. The second practical generalized collision handling into a constraint-based resolution framework. The third practical moved from rigid bodies to deformable objects using the finite element method. The final project was a Unity cloth simulation based on a mass-spring system. These projects helped me build practical experience with physical simulation, numerical integration, collision handling, constraint solving, mesh-based deformation, and real-time visual feedback.

## Assignment 1: Rigid-Body Simulation and Collision Response

The first assignment focused on rigid-body simulation and impulse-based collision response. I implemented the core physical update loop for rigid objects, including linear and angular velocity integration, position and orientation updates, interpenetration correction, and collision impulse handling. The simulation used tetrahedral mesh objects as rigid bodies. Their positions were updated through center-of-mass motion, while their orientations were represented and updated using quaternions. When two objects collided, the system corrected their interpenetration and applied collision impulses to update both linear and angular velocities. I also extended the basic simulation with additional effects such as drag, friction, and alternative time integration methods. The short demo below shows the resulting rigid-body motion and collision behavior.

<video controls muted playsinline preload="metadata" width="100%">
  <source src="/videos/physics-rigid-body-demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

*Short demo showing rigid-body motion, interpenetration correction, and impulse-based collision response.*

## Assignment 2: Constraint-Based Collision Resolution

The second assignment extended the rigid-body collision system from the first assignment by introducing a constraint-based resolution framework. Instead of resolving collisions through a dedicated collision response function, collisions and user-defined attachments were represented as constraints and solved through a shared velocity and position correction system. I implemented constraint-based velocity resolution using Jacobians, inverse mass matrices, inverse inertia tensors, and Lagrange multipliers. The system corrected both linear and angular velocities so that rigid bodies could satisfy distance constraints and collision constraints. I also implemented position correction for violated constraints, using inverse-mass weighting to adjust the center-of-mass positions of the involved bodies. This assignment helped me understand how collision response can be generalized into a broader constraint-solving framework. Compared with the first assignment, the focus shifted from handling collisions directly to expressing physical relationships as constraints and resolving them in a unified way.

<video controls muted playsinline preload="metadata" width="100%">
  <source src="/videos/physics-constraint-collision-demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

*Short demo showing constraint-based collision and attachment behavior between rigid bodies.*

## Assignment 3: Finite-Element Soft-Body Deformation

The third assignment shifted from rigid-body collision handling to soft-body simulation. The goal was to simulate deformable objects using the finite element method on tetrahedral meshes. I implemented the core FEM integration pipeline for soft-body dynamics. This included computing per-vertex masses from tetrahedral volumes, constructing sparse mass, stiffness, and damping matrices, and assembling the implicit integration system used to update vertex velocities and positions over time. The simulation used material parameters such as Young's modulus, Poisson's ratio, density, and damping coefficients to control the deformation behavior of the soft body. At each time step, internal elastic forces and external gravity were combined into the right-hand side of the system, and a Cholesky solver was used to compute the updated velocities. Compared with the previous rigid-body assignments, this assignment focused less on object-level motion and more on vertex-level deformation. It helped me understand how soft-body behavior can be modeled through internal forces, material stiffness, and numerical integration.

<video controls muted playsinline preload="metadata" width="100%">
  <source src="/videos/physics-soft-body-fem-demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

*Short demo showing finite-element soft-body deformation on a tetrahedral mesh.*

## Assignment 4: Unity Cloth Simulation

The fourth assignment was a self-directed physics simulation project. I implemented a simple cloth simulation in Unity using a mass-spring system. The cloth was generated as a procedural grid mesh. Each vertex was treated as a particle with its own position and velocity, while the mesh triangles were generated programmatically to form the cloth surface. The left side of the cloth was fixed, allowing the rest of the cloth to move freely under physical forces. The simulation used three types of springs: structural springs to preserve horizontal and vertical connections, shear springs to support diagonal deformation, and bend springs to reduce excessive folding. Gravity, damping, and a periodically changing wind force were also applied to create more dynamic cloth motion. At each frame, the system updated vertex velocities based on external forces and spring forces, then integrated the vertex positions using explicit Euler integration. The updated vertex positions were written back to the Unity mesh to display the simulated cloth deformation in real time.

<video controls muted playsinline preload="metadata" width="100%">
  <source src="/videos/physics-cloth-simulation-demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

*Short demo of a Unity cloth simulation using a mass-spring system with gravity, damping, and wind.*

## Tools and Methods

**Tools:** C++, Unity, C#, Eigen, libigl, libccd, OpenGL-based viewer  
**Methods:** rigid-body dynamics, impulse-based collision response, constraint-based resolution, Jacobian-based velocity correction, inverse-mass position correction, finite element method, sparse matrix construction, Cholesky solving, mass-spring cloth simulation, explicit Euler integration  
**Focus Areas:** physics simulation, numerical integration, collision handling, constraint solving, soft-body deformation, real-time simulation