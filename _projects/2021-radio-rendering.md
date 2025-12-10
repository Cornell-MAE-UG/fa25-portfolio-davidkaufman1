---
layout: project
title: Torque Wrench Design
description: Applied Materials Design Problem
technologies: [Analysis, FEM, 3D Modelling]
image: /assets/images/radio-machine-cad.jpg
---




## **5.2.1.1**

The torque wrench design includes a slotted cross section which increases the moment of inertia in the bending direction. Flats are incorporated on the handle near the drive to integrate the strain gauge. Fillets from the handle to the strain gauge flats help mitigate possible stress concentration at this corner. A circular head with a greater area moment of inertia was included to minimize stress on the fixed end due to the larger bending moment. The design includes a large fillet from the circular head to the wrench handle to prevent stress concentrations. The length from the free end to the drive is 16 inches. 

<img src="{{"/assets/images/TW_iso_view.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/TW_top_ZI.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/TW_side_ZI.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/TW_low_iso.png" | relative_url }}" width ="75%">


5.2.1.2

<img src="{{"/assets/images/materials_plot.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/material_options.png" | relative_url }}" width ="75%">


We found several samples with different material compositions to optimize for compliance while maintaining a good fracture toughness, as that was a parameter that was the closest to the safety factor limit in the base case. 

After much analysis and iteration, our final design utilizes Titanium alpha-beta alloy (Ti-6Al-4V). This alloy’s relatively low Young’s Modulus allows for the required strain at the strain gauge, while at the same time possessing a great enough tensile strength, fracture toughness, and fatigue strength to satisfy our factors of safety (see above chart for values). 

5.2.1.3

The 600 lb-in torque (Tag B - Red) was applied to the free end face using component scope in the x - direction. A zero displacement boundary condition (Tag A - Yellow) was applied to the four side faces and top face of the drive. See images below. 

<img src="{{"/assets/images/BCs_ss.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/BC_force_ss.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/BC_displ_ss.png" | relative_url }}" width ="75%">

5.2.1.4

Below are plots of the normal strain as scoped in the y - direction. We achieve a magnitude of normal strain of 1.9209E-3 at the gauge locations. Note that there are singularities in the strain contours near the corners of the strain gauge flats. These singularities can be considered a breakdown in the model as the normal strain magnitude decreases with distance from the corner of the flat along a constant thickness. So, this strain singularity can be ignored as it is simply a manifestation of a corner/fillet concentration.

<img src="{{"/assets/images/zoomedOut_normal_strain.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/zoomedIn_normal_strain.png" | relative_url }}" width ="75%">


5.2.1.5

In the max principal stress contours below, we see the design satisfies the factor of safety in yield and fatigue stress. For an upper limit set by the FOS in yield: 0.25 * 138 ksi = 34.5 ksi. For an upper limit set by the FOS in fatigue: 92 ksi. So, to satisfy our stress FOS’s we take 34.5 ksi as the max allowable stress.
Similar to the strain contours above, there are two regions of elevated stress that exceed this limit. From the close-up of the drive region, we see a stress concentration on a line separating the drive from the drive fillet. This singularity is a result of the zero displacement boundary condition, and can be ignored as stated by Prof. Zehnder and Dr. Bhaskaran. Four other concentrations are seen on the corners of the strain gauge flats on each side of the wrench. Since the stress decreases when analyzing an element adjacent to the corner in any direction, we can assume these singularities are a result of the corner/fillet, and are nonphysical so they can be ignored. 
Ignoring these singularities, the max principle stress we see in the model is approximately 32 ksi, less than our max allowable stress. A convergence mesh feature was used to iterate through mesh sizing on the principle and normal stress until the change in stress was less than 5% from one iteration to the next. Using this convergence mesh, we can reference these stresses with high confidence.

<img src="{{"/assets/images/ZO_max_principle.png" | relative_url }}" width ="75%">

<img src="{{"/assets/images/ZI_max_principle.png" | relative_url }}" width ="75%">

5.2.1.6

Normal Stress Contour

<img src="{{"/assets/images/normal_stress.png" | relative_url }}" width ="75%">

Deflection in X-Dimension

<img src="{{"/assets/images/directional_deflection.png" | relative_url }}" width ="75%">

Normal Strain at Gauge

<img src="{{"/assets/images/zoomedIn_normal_strain.png" | relative_url }}" width ="75%">

Equivalent Strain at Gauge

<img src="{{"/assets/images/equivalent_strain_at_sg.png" | relative_url }}" width ="75%">

Equivalent Stress

<img src="{{"/assets/images/Z_VM_stress.png" | relative_url }}" width ="75%">


5.2.1.7

According to the strain at the strain gauge flat in the probe below, the torque wrench sensitivity is 1.9 mV/V. This satisfies the minimum sensitivity of 1mV/V. 

<img src="{{"/assets/images/zoomedIn_normal_strain.png" | relative_url }}" width ="75%">

5.2.1.8

<img src="{{"/assets/images/straingauge.png" | relative_url }}" width ="75%">

Vishay CEA-05-125UNA-375 Strain Gauge

The strain gauge is essentially one resistive element with two terminals, so it is a quarter-bridge strain gauge. It has an overall length of just 0.275” x 0.125”, with the longer side meant to lie parallel to the axis of the handle. This fits comfortably on the flat sections of the sides torque wrench near the drive. (There is a flat spot on either side so that we can include two gauges for redundancy.) The strain gauge has a relatively high resistance compared to the other gauges in the family, 375 Ohms as opposed to 275 or 120, but this model has the lowest uncertainty at just 0.2%. 

It has a strain range of 5%, which is more than 25 times the strain we expect to see with the given force we’re applying. This allows for good definition and accuracy within the scope of the measurement but also a good factor of safety to avoid failure of the strain gauge. (Based on the material properties of the titanium and the factor of safety for tensile strength, the torque wrench would actually fail before the strain gauge.)

It is reasonably priced, with each gauge costing about $14 on Digikey. 





