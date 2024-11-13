---
title: "Multi-Material Pliers"
excerpt: "Custom 3D-Printed Pliers with 2 Materials"
header:
  image: assets/img/Mark III.jpg
  teaser: assets/img/Mark III.jpg
gallery:
  - image_path: assets/img/Mark 1.jpg
  - image_path: assets/img/Mark II.JPG
  - image_path: assets/img/Mark III.jpg
   
---

# Project Overview

For this project, I designed and 3D-printed functional multi-material pliers optimized for handling through-hole resistors. The design incorporates both rigid PLA for the handles and jaws, along with flexible TPU for the spring mechanism, creating a self-returning mechanism where squeezing the handles temporarily closes the jaws of the pliers, and releasing the handles causes the TPU spring to return to its normal non-stretched state, and thus opens the jaws. 

A rapid iterative design process was used to design the form and dimensions of the pliers. Multiple versions of the spring were printed to determine the optimal height, clearance, and infill parameters. Additionally, the handle designs were updated to improve ergonomics and functionality. Lastly, the jaws themselves were improved to enable them to pick up the small resistors more easily and effectively. 

Ultimately, this project illustrated the power of combining multiple materials to create functional parts or tools by leveraging the material properties of different plastics and the capability to print complex designs quickly and cheaply. 

## Final Multi-Material Plyers
![Pliers in Action](/assets/img/PlyerGIF.gif)

# Background on Print-in-Place Technology

Print-in-place (PIP) technology enables 3D printing components that are "ready to go" without additional post-processing or assembly. Crucially, print-in-place allows you to create mechanical parts (like joints, hinges, and linkages) that are integrated into each other during the printing process itself. Typically, print-in-place designs rely on careful clearances between moving parts printed in a single material (since the clearance gap enables separation of the components, even if one component is inside the other - like a pin in a hinge). 

Print-in-place technology has expanded the value of 3D printing applications across various fields:
* Robotics: Joint mechanisms and grippers
* Consumer Products: Articulating toys, adjustable mounts, and tools
* Rapid Prototyping: Quickly print and test mechanical devices and systems
* Educational Models: Complex models

However, these PIP parts can have rough movement due to printing irregularities or flaws. Fortunately, an alternate PIP approach exists to enable smooth, flexible movement: multi-material printing. By combining a flexible plastic like TPU with a rigid plastic like PLA or ABS, you can print a hybrid part as one continuous print using specialized printers. For example, you can create a rigid hinge with an integrated, flexible joint, or you can quickly print and test a shock-dampening spring assembly.

# Design Process

## Goal & Initial Concept

For this project, the goal was to replicate print-in-place multi-material printing by printing parts in two different materials and then press-fitting them together. 

The pliers were designed with three main components:
* Upper and lower handles (identical)
* Upper and lower jaws (identical)
* TPU spring element

To join the handles and jaws to the spring, I used dovetail joints for a secure press-fit. 

To design the pliers, I created three different prototypes through rapid prototyping to change the design and the dimensions. 

## Key Features
* Self-returning mechanism requires no manual reset
* Precise jaw alignment for consistent gripping
* Able to pick up small resistors
* Ergonomic handle design
* Tool-free assembly and disassembly (press-fit)

## Spring Mechanism

I designed a square TPU spring to function as the joint between the handles and the jaws (the pivot point in conventional spring). The spring went through multiple revisions:

**Version 1**: Thin 4 mm height spring, with thick rectangular cutouts (manually designed in CAD). This spring used 1 dovetail per side, with a 0.2 mm clearance. Ultimately, it was too stiff to function, and the clearance was too wide to enable press fit. 

**Version 2**: Infill-controlled, 7 mm tall spring without any dovetail clearance, but with 3 dovetails per side. Using the infill to generate the rectangular cutouts (described below) provided the correct thickness, and increasing the height and number of dovetails made the joint more secure. However, it was too tight to press-fit without any clearance. 

**Final Product**: Added a 0.15 mm offset to the dovetails. This enabled a secure press-fit connection, and the spring functioned as intended. 

## Handles

I used rigid PLA to create the handles. The handle geometry went through several revisions to provide the proper leverage, spacing, and ergonomics:

**Version 1**: Medium-length handles with medium spacing. When attached to the spring, the handles were too close together to provide enough leverage.

**Version 2**: Long-length handles with wide spacing. This was a significant improvement, but the flexible spring made the pliers too wobbly with the long handles. I also increased the height to 7 mm to match the spring.

**Final Product**: Kept the wide spacing but shortened the length to the minimum ergonomic length, which made it much more compact. 

## Jaws

I used rigid PLA to create the jaws. Here, the jaws went through one major revision to enable them to pick up the resistors:

**Version 1**: Medium-length jaws with a rectangular "contact pad" jutting downward. The flat side of the pad would hit the surface first, before the pads could close around the small restor. 

**Version 2 & Final Product**: Short-length jaws with sharp tips. The sharper tips were successfully able to pick up the resistors. 


## Gallery
{% include gallery caption="Version 1, Version 2, and Final Product." %}

## CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a470ff057255634bd7?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>


# Technical Specifications

## Plier Dimensions
* Overall Length: 189 mm
* Jaw Length: 45.8 mm
* Core Spring Dimensions: 30 mm x 30 mm
* Maximum Jaw Opening: 7.325 mm
* Standard Grip Width: 88.7 mm
* Handle Length: 120 mm
* Handle Thickness: 19.4 mm

## Materials Used
* Ridgid Handles and Jaws: PLA 
* Spring: TPU 95A 

## Special Print Settings

**TPU Spring:**
* Infill Type: Rectilinear
* Infill Angle: 90° (perpendicular to spring walls)
* Fill Density: 12%
* Perimeters: 4
* Solid Top Layers: None
* Solid Bottom Layers: None
