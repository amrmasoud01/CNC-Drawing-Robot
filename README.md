# CNC-Drawing-Robot
A low-cost, Arduino-powered drawing machine for converting vector graphics to physical artwork. Developed for university computer graphics studies with full documentation.
📜 Project Overview
This repository documents the design and implementation of a CNC drawing robot similar to the AxiDraw, featuring:

CoreXY kinematic system with NEMA 17 stepper motors

GRBL firmware on Arduino Uno + CNC Shield

3D-printed mechanical components (Thingiverse models)

Modular pen holder with SG90 servo control

Under $100 build cost with common maker components

Designed for computer graphics applications:
SVG Design → G-code Conversion → Physical Rendering

📊 Technical Specifications
Electronics

Arduino Uno + CNC Shield v3.0

2x A4988 Stepper Drivers

SG90 Servo (Z-axis simulation)

12V 2A Power Supply

Mechanical

Motion System:

X/Y: M8 linear rods (450mm/350mm) + LM8UU bearings

GT2 belt + 16T pulleys

Z-Axis:

3mm linear rods (salvaged from CD-ROM)

Spring-loaded pen mechanism

Software

GRBL 1.1h firmware

Inkscape G-code extensions

Custom Processing control scripts

🛠️ Assembly Highlights
3D Printing Requirements
markdown
- **Printer Settings**:  
  - 0.10-0.20mm layer height  
  - 75% infill (minimum)  
  - Hatchbox Red PLA recommended  
  - Critical parts: Penholder, Slider, X/Y Supports  

- **Print Times**:  
  - Longest part: ~9 hours  
  - Shortest part: ~30 minutes  
Mechanical Assembly
X-Axis Construction:

Threaded M8 rod (470mm) + linear rods

LM8UU bearing alignment with rubber mallet

GT2 belt tensioning with needle-nose pliers

Y-Axis Integration:

350mm linear rod installation

624zz bearing placement for smooth motion

Z-Axis Mechanism:

CD-ROM-derived linear rods

Spring tension adjustment for pen lift

