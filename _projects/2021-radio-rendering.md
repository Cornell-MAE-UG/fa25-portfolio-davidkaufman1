---
layout: project
title: Torque Wrench Design
description: Applied Materials Design Problem
technologies: [Analysis, FEM, 3D Modelling]
image: /assets/images/radio-machine-cad.jpg
---

5.2.1.1
The torque wrench design includes a slotted cross section which increases the moment of inertia in the bending direction. Flats are incorporated on the handle near the drive to integrate the strain gauge. Fillets from the handle to the strain gauge flats help mitigate possible stress concentration at this corner. A circular head with a greater area moment of inertia was included to minimize stress on the fixed end due to the larger bending moment. The design includes a large fillet from the circular head to the wrench handle to prevent stress concentrations. The length from the free end to the drive is 16 inches. 

<img src="{{"/assets/images/spaceship-design.jpg" | relative_url }}" width ="50%">

![TW Iso View]({{"/assets/images/TW_iso_view.png" | relative_url}})

<p align="center">
    <img src="../assets/images/TW_iso_view.png" width="50%">
</p>

<p align="center">
    <img src="../assets/images/TW_top_ZI.png" width="50%">
</p>

<p align="center">
    <img src="../assets/images/TW_side_ZI.png" width="50%">
</p>

<p align="center">
    <img src="../assets/images/TW_low_iso.png" width="50%">
</p>

5.2.1.2

<p align="center">
    <img src="../assets/images/materials_plot.png" width="50%">
</p>

<p align="center">
    <img src="../assets/images/material_options.png" width="50%">
</p>



Found several samples with different material compositions to optimize for compliance while maintaining a good fracture toughness, as that was a parameter that was the closest to the safety factor limit in the base case. 
After much analysis and iteration, our final design utilizes Titanium alpha-beta alloy (Ti-6Al-4V). This alloy’s relatively low Young’s Modulus allows for the required strain at the strain gauge, while at the same time possessing a great enough tensile strength, fracture toughness, and fatigue strength to satisfy our factors of safety (see above chart for values). 

5.2.1.3


