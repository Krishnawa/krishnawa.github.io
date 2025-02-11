---
title: Component Selection
date: 2023-10-17 10:39:00 +530
categories: [Homelab,review]
tags: [review,layout,schematic]
comments: true
mermaid: true
math: true
image:
    path: assets/img/Component_Selection/Componentes.jpeg
    lqip: assets/img/Component_Selection/Componentes.jpeg
    alt: Components

---
How to choose a component?

First why we need to do a protocol to make components selections?
Because if you don't have only the value and doesn't have any about the component which will make you more complication in the later stage of design so yo need a better understanding about your components, This will be mainly divided into two ways 

1. Software/Tool perspective
2. Hardware/Physical perspective


1. Software

1. Symbol - Library for schematic and layout

Which ever tool you are using it doesn't matter you definitely need the library for the components which you are using in the design, if the library is not available you can do two things 

a. Create a library 
  use a the datasheet of the component to make assure all the pins are correctly configured or mapped
  do the same for the footprint library 
b. Download the Library 
  Even if you are using the download library, Please ensure all the pin mapping are correct with datasheet of the component
  same for the Footprint also otherwise you will mess up with your design

2. Grid/ alignment
  Make sure that your all symbols are in the same grid if there's any mismatch between the symbols grid alignment probably you can't complete the design or that particular component will project differently and it will affect the esthetics of the schematic 
3. 3d model
  This is not mandatory but if you have a 3D model of the component then you will get an idea of how your design looks when it is completed, so you can render your board to get the real board



2. Hardware
coming to hardware, 
a. The size of the component
b. footprint
c. Application - Temperature, Grade (industrial), .
d. Tolerance acceptance
e. Range (Voltage)
f. specific details (eg: Capacitor- X7R, C0G, de-rating, )

1. Resistor
To choose a resistor the main things are the size and wattage of the component,
the first for the application and cost of the p
there's trade of between size and cost