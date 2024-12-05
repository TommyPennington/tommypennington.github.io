---
title: "Bicycle Phone Mount"
excerpt: "Top-Down Modeling Project: Bicycle Phone Mount"
header:
  image: assets/img/Syringe Pump Final.jpg
  teaser: assets/img/Syringe Pump Final.jpg
gallery:
  - image_path: assets/img/Syringe Pump Render.png
  - image_path: assets/img/Syringe Pump Final.jpg
  - image_path: assets/img/Syringe Pump Circuit Schematic.png
   
---

# **Top-Down Modeling: Bicycle Phone Mount** 

# **Project Overview**

For this project, I developed a 3D-printed bicycle phone mount system that enables secure, adjustable smartphone viewing while biking. The design prioritizes quick phone attachment, full rotational freedom, and adaptable viewing angles up to 120 degrees through a durable ball joint mechanism. The phone mount features a tool-free quick-release mechanism (flexing the phone holder), handlebar-friendly clamping, and thoughtful port access—combining security and convenience for reliable phone access during rides. By leveraging parametric design principles and rapid 3D printing iteration, I fine-tuned the tolerances and made the design easily adaptable to not just perfectly fit my phone and case but also most iPhones. I chose to maximize degrees of freedom to the greatest extent possible, a design choice that drove my decision to use a ball joint. 

I used top-down modeling to streamline my design process. Top-down modeling is a hierarchical design approach in computer-aided design (CAD) where components are modeled based on reference geometry from higher-level components rather than building parts independently and assembling them later. This methodology establishes a parent-child design system that drives the geometry of all dependent components, creating intelligent relationships between parts. For example, you can use top-down modeling to design a shaft and then create a bearing defined by the original shaft’s geometry. When key parameters or reference geometry change, these updates automatically cascade through the entire assembly, enabling rapid design iterations without manually updating each component. This approach contrasts with traditional bottom-up modeling, where individual parts are created in isolation and then assembled, making systemic changes more labor-intensive and complicated. However, top-down modeling makes it harder to make dramatic redesigns of earlier components since it’s easy for a “breaking change” to destroy other later components in the model. Additionally, I had to be careful to follow the rules of top-down modeling (component creation and bodies) and fully define all sketches and operations. Fortunately, all together, this approach enabled the rapid and effective design of my phone mount, and I did not encounter major top-down modeling challenges.

### **Critical Requirements**

1. **Quick Phone Attachment**  
   * Tool-free phone insertion/removal  
   * Sub-5 second attachment time  
   * Unobstructed access to ports and controls  
2. **Orientation Adjustment**  
   * 90° rotation capability (vertical or horizontal) \- lockable in place  
   * Maintain position under vibration/bumps during the ride  
   * Bonus objective: Additional degrees of freedom (viewing angle)  
3. **Handlebar Mounting**  
   * No permanent modification (drilling or set screws) required  
   * Accommodates 23-25mm diameter handlebar

## Gallery

{% include gallery caption="Original 3D render, final product, and circuit schematic." %}

## 3D Model

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a49e16a75f247b02ce?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## **Design Approach**

### **Top-Down Modeling Strategy**

The design process began with the grounding of handlebar geometry (25mm OD) as the primary reference feature. A phone model (iPhone 12 Pro) was then imported and positioned at an ergonomic viewing angle to establish the second key reference. These two elements drove the subsequent component modeling, and parametric design enabled rapid iteration through different fits and clearances:

1. **Single-piece handlebar Collar & and Ball Joint**  
   * Split-clamp design with parametric clearance around maximum handlebar shaft diameter. It was top-down modeled around the handlebar OD (the collar \+ clearance ID)  
   * Integrated ball joint cup with parametric overlap depth and offset (ball clearance)  
   * Mechanical fastener system (screws and nuts) for secure long-term clamping  
2. **Ball Joint Mechanism**  
   * Top-down modeled to ensure an accurate and adaptable fit within the cup  
   * Resin-printed ball and rod for durability and smoothness (high resolution)  
   * Parametric tolerance of 0.5mm for smooth operation  
   * Integrated tensioning system via thumb screw (durable heat-set insert in cup component)  
3. **Phone Holder Component**  
   * Top-down modeled around phone model for accuracy with 4mm parametric offset to accommodate standard phone case  
   * TPU construction for flexibility and grip  
   * Quick-release design (flex open) with secure retention  
4. **Thumbscrew**  
   * Ergonomic oversized thumbscrew top-down modeled around M5 screw and hex nut

### **Key Design Parameters**

| Parameter Description | Name | Value | Purpose |
| ----- | ----- | ----- | ----- |
| Clamp Slot Depth | MountSlot | 6mm | Enables flex for installation |
| Cup Tolerance | CupOffset | 0.5mm | Ball joint smooth operation |
| Ball Coverage | BallOverlapDepth | 6mm | Secure ball retention |
| Insert Diameter | ThumbScrewInsertDiameter | 6.4mm | Heat-set insert fit |
| Phone Case Allowance | PhoneOffset | 4mm | Case accommodation |
| Handlebar Fit | HandlebarOffset | 0.25mm | Installation clearance |
| Handlebar Size | HandlebarOD | 25mm | Base reference dimension |

## **Material Selection Rationale**

### **Component-Specific Materials**

1. **PLA Components (Collar & Thumb Screw Cap)**  
   * High strength & rigid (but flexible enough for ball-cup press-fit)  
   * Easy to print with high-detail  
2. **Resin Ball Joint**  
   * High-resolution surface finish for smooth operation  
   * High strength  
   * Wear resistance  
3. **TPU Phone Holder**  
   * Flexible for phone insertion/removal  
   * Vibration dampening properties

## **Assembly Components**

### **Bill of Materials**

| Item | Description | Material/Spec | Qty | Function |
| ----- | ----- | ----- | ----- | ----- |
| 1 | Handlebar Collar | PLA | 1 | Primary mount |
| 2 | Ball Joint Rod | Epoxy Resin | 1 | Motion & articulation |
| 3 | Phone Case Mount | TPU | 1 | Secure phone holder |
| 4 | Thumb Screw Cap | PLA | 1 | Ergonomic grip |
| 5 | Thumb Screw | M5 x 20mm | 1 | Joint tension control & securing position |
| 6 | Thumb Screw Nut | M5 | 1 | Cap attachment |
| 7 | Mount Screw | M5 x 10mm | 1 | Phone mount fastener |
| 8 | Collar Screws | M5 x 30mm | 2 | Handlebar clamping |
| 9 | Collar Nuts | M5 | 2 | Clamp assembly |
| 10 | Heat Set Insert | M5 x 5mm | 1 | Thumb screw thread |

## **Assembly Instructions**

1. Install heat-set insert into thumbscrew housing and screw the thumbscrew partially in (it should not enter the cup void yet).  
2. Attach phone holder to ball joint rod using M5 screw (the rod has internal threads) and an Allen key to ensure the tightest possible fit.   
3. Insert ball joint assembly (press fit the ball into the cup).  
4. Assemble collar around handlebar with M5 screws and hex nuts (intended to be fastened securely long-term using an Allen key).  
5. Place phone into holder by flexing the holder. Test range of motion and adjust thumscrew tightness as needed.

