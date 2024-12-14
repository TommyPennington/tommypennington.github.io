---
title: "Generative Design Skateboard Hanger"
excerpt: "Generative Design SLS Truck Hanger with Integrated Motor Mount"
header:
  image: assets/img/Mark III.jpg
  teaser: assets/img/Mark III.jpg
gallery:
  - image_path: assets/img/Mark 1.jpg
  - image_path: assets/img/Mark II.JPG
  - image_path: assets/img/Mark III.jpg
   
---

# **Generative Design SLS Truck Hanger** 

## **Powder Bed Fusion and Generative Design**

The combination of powder bed fusion (PBF) and generative design represents a powerful synergy in advanced manufacturing, particularly evident in aerospace and automotive applications where lightweight, optimized components are mission-critical. The success of this pairing stems from PBF's capability to fabricate the intricate, organic structures that generative design typically produces. Unlike traditional manufacturing methods that often constrain design freedom, PBF can create internal lattices, complex cooling channels, and variable wall thicknesses \- all common features in generatively designed parts. This manufacturing freedom allows for optimized components that wouldn't be possible with many conventional processes like CNC milling (which cannot create internal voids). 

This synergy was leveraged by Airbus when their Innovation Team partnered with Autodesk to design a “bionic partition” \- a central component of the Airbus 2050 Concept Plane.

Ultimately, generative design was used to create an optimized partition structure by:

1. Incorporating biological growth patterns from slime mold and mammal bones  
2. Generating and evaluating over 10,000 design iterations  
3. Optimizing for multiple constraints, including weight, strength, and crash resistance

The resulting design achieved several key benefits:

* 45% lighter than the traditional partition  
* Required 95% less raw material during manufacturing  
* Reduced the aircraft's fuel consumption by approximately 3,180 kg per partition annually  
* Decreased CO2 emissions by 166 metric tons per plane per year when all four partitions are installed

This illustrates the transformative power of generative design when applied at an industrial scale and the potential for optimizations to yield dramatic results over time (such as significant cost savings or decreased environmental impact).

## **Generative Skateboard Hanger**

For this project, I wanted to use Fusion 360’s generative design capabilities to optimize a skateboard hanger. The hanger is the arguably most critical component of a skateboard, and provides the connection between the mounting plate, axle, and motor mount, while enabling turning via the pivot point. Furthermore, it also experiences most of the significant loads and forces exerted on the skateboard. Thus, it was a prime candidate for lightweight optimization via generative design. 

The “design space” is defined by a combination of Preserve Geometries and Obstacle Geometries. Preserve Geometries are the core features that must be maintained in the generated design (like the pivot and mounting plate), and the Obstacle Geometries are the bodies that must be avoided (like the axle, wheels, bolts, and the motor). The main goal is to constrain the design space as little as possible by minimizing both the Preserve and Obstacle Geometries used. Lastly, you can apply forces and structural constraints to the model to ensure that the generated part is strong enough to survive the various loading cases. 

## Gallery

{% include gallery caption="Original 3D render, final product, and circuit schematic." %}

## 3D Model

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a420076f0a92eef089?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>
ALSi10Mg Generative Design Assembly

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a45b708ca865ee4c70?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>
Nylon Design Assembly

## **Design Considerations**

The generative design needed to meet several key requirements:

1. Fit and Assembly  
   * Proper fit over kingpin and into base plate (pivot cup)  
   * 8.2 mm through-hole for steel axle  
   * Maximum 18 mm diameter at wheel/bearing interface (608ZZ bearings)  
   * Overall hanger length of 210 mm  
2. Manufacturing Constraints  
   * Maximum print size on Fuse 1: 160 mm × 160 mm × 290 mm  
   * Must include student's name/initials  
   * Design should maintain generative characteristics with minimal form editing  
3. Motor Mount and Belt System  
   * Drive belt outer diameter: 285 mm  
   * \~4 mm adjustment range for belt tensioning  
   * Motor height balanced between ground clearance and turning ability

These constraints guided the development of a functional design that balanced performance requirements with manufacturing limitations.

## **Preserve and Obstacle Geometries**

### **Preserve Geometries**

I preserved the following critical features that define the functionality of the hanger:

1. Required Preservations  
   * Pivot point  
   * Kingpin through-hole pattern  
   * Threaded rod sleeve  
     1. Here, I separated the sleeve into two bodies (the far left and the far right) instead of doing a full-length rod sleeve. This added additional generative freedom and decreased the final weight significantly.  
   * Motor mounting plate

To avoid overly constraint the generative design, I avoided constraining these features: 

1. Explicitly Not Preserved  
   * Motor mount to hanger connection  
   * Hanger geometry itself

### **Obstacle Geometries**

The following obstacles are required:

1. Wheel Assembly Clearances  
   * Drive pulley space  
   * Bearing outer-race clearance  
   * Threaded rod pathway  
2. Component Clearances  
   * Bushings and kingpin  
   * Motor shaft and mounting holes  
   * Belt pathway  
   * Mounting plate  
3. Operational Clearances  
   * Ground clearance  
   * Skateboard deck 

I ultimately combined many of these to simplify the design and provide improved clearances/offsets, including a Pulley Obstacle (belt pathway and gears) and a Kingpin Obstacle (kingpin, bushings, washers, bolt, etc.). I also added an additional offset and shields around the mounting plate to enable turning clearance. 

## **Load Case Application and Structural Constraints**

For this generative design study, a variety of common load cases were created, including scenarios for normal loads (typical riding) and special cases like turning or collisions. These forces were estimated based on engineering principles and force analysis. A 2x safety factor was applied to help ensure that the generated design would be strong enough to account for any small discrepancies between expected and actual forces. 

Real performance can only be validated through physical testing. By printing test components and subjecting them to actual riding conditions, we can data on the true forces experienced during both normal operation and extreme scenarios using tools like stress/strain gauges. This real-world data can reveal unexpected loading patterns and forces. Fortunately, SLS manufacturing enables rapid prototyping and iteration, so if the predicted loading cases don’t work in the real world, we can easily re-optimize the design using a new study. 

For this first prototype, load cases for the longboard truck were estimated and divided into static and dynamic forces. The cases used in the study for these forces and their justifications are presented below:

### **Static Loading Analysis**

| Force Type | Magnitude | Justification |
| ----- | ----- | ----- |
| Gravity | 9.08 m/s^2 | Applied to generated design |
| Rider Weight | 890 N | Based on a 90.7 kg rider with F \= mg |
| Motor Weight | 8.43 N | Weight of 6374 brushless motor (0.86 kg) |
| Motor Torque | 8 Nm | Typical torque output for 6374 brushless motor |
| Belt Tension | 533 N | Calculated from drive belt parameters and motor torque |

### **Dynamic Loading Analysis**

| Force Type | Magnitude | Justification |
| ----- | ----- | ----- |
| Vertical Impact (Jump) | 2670 N | 3x rider weight for landing impact |
| Horizontal Impact | 2670 N | Equivalent to vertical impact for collision scenarios (hard horizontal hit) |
| Turning Forces | 712 N (each direction) | 0.8x rider weight for lateral forces during turns |
| Wheel Impacts | 890 N (per wheel) | Equal to rider weight for obstacle impacts |

### **Structural Constraint Methodology**

The structural constraint for the study is critical since all calculations use this as the “static point” to which forces are translated. Thus, its location defines much of the generative design and shapes how deformation is predicted based on the applied loads (and therefore where material is added or removed).

The structural constraint was singularly placed at the pivot point where the hanger interfaces with the baseplate. This specific placement was chosen because:

1. It represents the primary rotation point during turning maneuvers  
2. It allows natural force distribution through the structure during both static and dynamic loading and allows for the most direct transfer of force between the hanger and the mounting plate

## **Comparison of Nylon and Aluminum Outcomes**

The generative design solutions for Nylon 12 and ALSi10Mg produced notably different results, reflecting the materials' distinct properties:

**Nylon 12 Design: 0.995 kg**

* Required thicker structural members due to lower material strength  
* Resulted in a heavier overall structure due to weaker material  
* Did not fully benefit from generative design, since the material weakness resulted in a “brick” being generated (which did not really exhibit optimizations)

**ALSi10Mg Design: 0.454 kg**

* Achieved higher stiffness with thinner structural members  
* Exhibited the classic, organic features created by generative design  
* Significantly lighter (over 50%) than aluminum, and produced better results than human design

## **Critique of Generative Design**

For this skateboard truck application, generative design proved valuable in integrating the motor mount with the truck hanger while optimizing for weight and strength. Additionally, the complex/organic generated design was compatible with our chosen manufacturing method (powder bed fusion), so this did not cause a problem. However, it was likely “overkill” for this part, since it didn’t really need complex optimization or high performance. Additionally, it took longer to create the required Preserve and Obstacle geometries than it likely would have to design the part from scratch, and test performance in the real-world. 

This was highly representative of the real-life advantages and limitations of generative design:

Advantages:

* Ability to explore design spaces beyond human intuition (organic bodies and voids)  
* Optimization of material usage and weight reduction  
* Integration of multiple features into single streamlined components (like simplifying a bracket)  
* Easy iteration of design alternatives with different load cases  
* Excellent compatibility with additive manufacturing

Limitations:

* Computational intensity and time requirements  
* High sensitivity to initial constraints and load cases  
* Manufacturing constraints may limit theoretical optimizations, which can be difficult/expensive to produce

As a result of these advantages and limitations, this technology is most useful in:

1. Weight-critical applications (aerospace, high-performance automotive)  
2. Thermal management systems requiring complex internal channels (like a rocket engine or motor)  
3. Small-batch production where additive manufacturing is used (instead of industrial-scale tooling)

Ultimately, the future of generative design lies in its integration with more sophisticated manufacturing processes and improved simulation capabilities. As computational power increases and algorithms improve, we can expect to see more widespread adoption across various industries, particularly in applications where performance optimization and part consolidation provide significant advantages. While a true “ChatGPT for CAD” may be quite a far way off, this emerging technology promises to transform engineering. 
