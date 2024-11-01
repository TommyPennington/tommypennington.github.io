---
title: "Microfluidic PFF Device"
excerpt: "Pinched Flow Fractionation Device for Particle Sorting"
header:
  image: assets/img/Syringe Pump Final.jpg
  teaser: assets/img/Syringe Pump Final.jpg
gallery:
  - image_path: assets/img/Syringe Pump Render.png
  - image_path: assets/img/Syringe Pump Final.jpg
  - image_path: assets/img/Syringe Pump Circuit Schematic.png
   
---

# Design and Analysis of a Pinched Flow Fractionation Device for Large Particle Separation

## Introduction

Pinched flow fractionation (PFF) has emerged as a powerful microfluidic technique for continuous, size-based particle separation that utilizes the characteristics of laminar flow at the microscale within a microfluidic chip or system. This passive separation method requires no external fields and offers advantages including operational simplicity, continuous processing capability, and compatibility with various particle types (Sajeesh and Sen, 2014).

The fundamental principle of PFF relies on the precise manipulation of fluid streams carrying particles to be sorted. The particle-laden sample stream is hydrodynamically focused by a particle-free sheath flow (a laminar, "high speed" flow of buffer solution) against a channel wall in a constricted "pinched" segment. Due to the laminar flow conditions, particles align their centers of mass along specific streamlines based on their size, with larger particles forced to align farther from the wall compared to smaller particles. When these streams enter a sudden expansion region, the aligned particles follow diverging streamlines according to their initial positions, enabling spatial separation (Yamada et al., 2004). The smaller particles follow a trajectory closer to the wall of the expansion section, whereas the larger particles tend to deflect less aggressively and tend closer toward the centerline.

Critical design and operational parameters govern PFF performance. The width ratio between the pinched and expanded segments (the expansion ratio) determines the degree of stream spreading and, therefore, separation resolution. The flow rate ratio between sample and sheath flows must be carefully controlled to achieve proper particle alignment. The pinched segment geometry, particularly its width and the angle of the pinch-to-expansion transition, significantly impacts separation efficiency. The pinched section should be as narrow as possible while still enabling clog-free operation, and the interplay between the width of the section, the overall flow rate, and the buffer vs. particle solution flow rates influence both the resulting shear forces (which drives particle alignment) and the Reynold's number (which indicates the degree of laminar flow, and thus separation stability) (Yamada et al., 2004).

For particles perfectly focused against the channel wall in the pinched segment, their effluent position (Y₀) in the expanded region can be predicted by:

Y₀ = (wp - D/2)(w₀/wp)

where wp is the pinched segment width, w₀ is the expanded segment width, and D is the particle diameter (Yamada et al., 2004). This relationship enables the design of devices for specific separation applications.

In microfluidic device fabrication, SLA (stereolithography) resin printing enables rapid prototyping of molds with complex 3D geometries that would be prohibitively expensive with traditional photolithography techniques due to the specialized equipment required. These printed molds are coated with parylene before PDMS casting to prevent the SLA resin from inhibiting PDMS curing and to ensure clean separation after curing. The parylene coating creates a uniform, pinhole-free barrier that prevents any uncured resin residues from leaching into the PDMS. PDMS is chosen as the final device material because it offers several crucial advantages: it's biocompatible and non-toxic (unlike most 3D printing resins), optically transparent for microscopy, and can form strong bonds with glass (the slide material). Additionally, PDMS replicates microscale features with high fidelity and allows multiple microfluidic devices to be cast from the same printed mold.

The applications of PFF span biological/healthcare research and industrial domains. The method has been demonstrated for separation of synthetic particles, blood cells, cancer cells, and droplets. PFF devices can achieve high-throughput processing while maintaining separation resolution, making them promising for both analytical and preparative applications. However, challenges remain in optimizing designs for specific applications and scaling up throughput while maintaining separation efficiency.

## Gallery

{% include gallery caption="Original 3D render, final product, and circuit schematic." %}

## Design Constraints

### Printer Specifications
- Laser Spot Size (i.e., Minimum Feature Size): 85 μm
- Minimum XY Resolution: 25 μm
- Minimum Z Resolution: 25 μm
- Build volume: (145 × 145 × 185) mm

### Sorting Design Specifications
- The device, when molded, must be precisely 25 mm wide by 75 mm long to sit flush on a common microscope slide
- Tall and thin components are likely to break off during printing, post-processing, or demolding. Aspect ratio is the height to cross-sectional width or length (whichever is smaller) of a printed feature. Keep the aspect ratio less than 4:1
- For inlets and outlets, use a 1.5 mm post extruded above the top of the mold. This will create a hole that is compatible with the microfluidic barb
- Channels should be at least 4 mm away from the edge of the device or else leaking will occur

## Device Design

### 1. Device Specifications

The device was designed to prevent clogging, maximize particle separation resolution, and effectively collect the particles based on the final vertical position of the laminar streams. The ultimate design was for a device with two inlets (one for the particle solution and one for the buffer), a narrow pinched section (to enable particle alignment along position-based streamlines), an expansion section with a sharp expansion angle of 105 degrees (to minimize turbulence while maximizing particle separation), two collection ports (an upper one for the 165 μm particles and a lower one for the 550 μm particles), and a drain (for the buffer solution) at the bottom of the expansion area.

#### Physical Dimensions
- Pinch region cross-section: 1.375 × 1.375 mm
- Pinch region length: 5.5 mm
- Expansion region width: 17.0 mm
- Channel height maintained throughout: 1.375 mm
- Width amplification ratio: 12.36

#### Position-Based Separation in Pinched Flow Fractionation
The fundamental principle of pinched flow fractionation relies on the alignment of particles against the channel wall in the pinched segment, followed by position amplification in the expansion region. The final position of a particle (y) in the expanded region is given by Y₀ = (wp - D/2)(w₀/wp) where wp is the pinched segment width, w₀ is the expanded segment width, and D is the particle diameter. All feature sizes were selected for compatibility with the printer resolution (described under Design Constraints), and to ensure printability.

#### Particle Stream Positions

**Small Particles (DP = 165 μm):**
```
y₁ = (1.375 - 0.165/2)(17.0/1.375)
   = (1.375 - 0.0825) × 12.36
   = 1.2925 × 12.36
   = 15.98 mm from inner wall
```

**Large Particles (DP = 550 μm):**
```
y₂ = (1.375 - 0.550/2)(17.0/1.375)
   = (1.375 - 0.275) × 12.36
   = 1.100 × 12.36
   = 13.60 mm from inner wall
```

**Separation Distance:**
Δy = y₁ - y₂ = 15.98 - 13.60 = 2.38 mm

#### Collection Ports (from opposite alignment wall)
- 165 μm particle collection: 15.98 mm
- 550 μm particle collection: 13.6 mm
- Divider position: 14.79 mm
- Separation distance: 2.38 mm

#### Channel-to-Particle Ratios
- Channel width / Large particle = 1.375 mm / 0.550 mm = 2.50
- Channel width / Small particle = 1.375 mm / 0.165 mm = 8.33
- Minimum clearance (large particle): 825 μm

These ratios were selected to ensure adequate clearance and a margin of at least 2.5x to prevent clogging.

## 3D Model

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a47960462e8f3cf892?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

### 2. Operating Parameters

#### Reynolds Number Selection (Re = 10)
The Reynolds number is calculated using: Re = (ρvDₕ)/μ
where:
- ρ = 997 kg/m³ (water density)
- v = flow velocity (m/s)
- Dₕ = hydraulic diameter (m)
- μ = 0.001 Pa·s (water viscosity)

Re = 10 was chosen because:
- Maintains laminar flow (Re < 2000)
- Provides sufficient inertial effects for focusing
- Results in practical flow velocities
- Ensures stable particle trajectories

#### Flow Rate Ratio (6:1 Buffer:Sample)
Based on original Yamada et al. research, 6:1 ratio ensures:
- Particle stream width < smallest particle diameter
- Complete alignment to channel wall
- Stable particle focusing
- Sufficient buffer for separation

### 3. Flow Rate Calculations

#### Step 1: Calculate Hydraulic Diameter
```
Dₕ = (2wh)/(w+h) where w = h = 1.375 mm
Dₕ = (2 × 1.375 × 1.375)/(1.375 + 1.375)
Dₕ = 1.375 mm = 1.375 × 10⁻³ m
```

#### Step 2: Calculate Required Velocity for Re = 10
```
v = (Re × μ)/(ρ × Dₕ)
v = (10 × 0.001)/(997 × 1.375 × 10⁻³)
v = 7.27 × 10⁻³ m/s = 7.27 mm/s
```

#### Step 3: Calculate Total Flow Rate
```
Q = v × A where A = w × h
Q = 7.27 × 10⁻³ × (1.375 × 10⁻³ × 1.375 × 10⁻³)
Q = 1.377 × 10⁻⁸ m³/s
Q = 49.6 mL/hr
```

#### Step 4: Calculate Individual Flow Rates
- Buffer flow rate = (6/7)Q = 42.5 mL/hr = 0.703 mL/min
- Particle solution flow rate = (1/7)Q = 7.1 mL/hr = 0.118 mL/min

**Additional Parameters:**
- Q (flow rate): 0.821 mL/min
- Volume of device: 0.83 mL
- Time to transit: 1.01 minute

## Device Fabrication

### Printing
#### SLS Resin Printing
The bottom of the mold (i.e., the face that will contact the glass slides) must be perfectly flat. Therefore, this surface needs to be parallel to the resin vat in order to prevent layer lines.

### Post Processing
1. Wash the device for 5 minutes on the print bed in the FormWash and then remove it from the bed and wash it for another 5 minutes in fresh IPA (the stationary bath to right of the FormWash). Do not exceed 10 total minutes of wash time as the resin can absorb the IPA.

2. Let your device dry by leaning it upside down for 30 minutes before curing. Do not let the IPA pool inside the device while drying. Confirm that the inside of the mold has a homogenous sheen. Glossy areas indicate that uncured resin is still present, which will inhibit the crosslinking of PDMS.

3. **DO NOT TOUCH THE INSIDE OF UNCURED MOLD.** Using your finger or paper towel to remove uncured resin will increase the surface roughness of the mold. This roughness will transfer to the PDMS device, likely causing sealing issues.

4. Gently blow off any debris between your uFluidic's channels. With safety glasses on, use the compressed air (orange knob next to the fume hood) to dislodge any foreign particles/resin that may have been picked up during the washing step.

5. Perform a 60 second surface cure with supports on. Curing the model for long durations can cause it to warp. Further, the mold does not require robust mechanical properties to function. Therefore, we will cure either the black or high-temp resin for 10 seconds at room temperature (no heat).

6. Remove support material. Once again be careful not to touch the inside of the mold.

### Casting
1. Coating with parylene
2. Casting with PDMS
3. Bonding with glass slide
