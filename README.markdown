# Arduino CNC Plotter

A DIY CNC plotter built with an Arduino Uno, CNC Shield v3.0, and 3D-printed parts. This project uses GRBL firmware to control stepper motors for X/Y motion and a servo for Z-axis pen lifting, enabling precise 2D plotting from G-code generated in Inkscape.

![CNC Plotter](images/cnc_plotter.jpg) <!-- Replace with your actual image path -->

## Table of Contents
- [Features](#features)
- [Hardware](#hardware)
- [Software](#software)
- [3D Printing Requirements](#3d-printing-requirements)
- [Mechanical Assembly](#mechanical-assembly)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Features
- **Precise 2D Plotting**: Draws vector designs using GT2 belts and linear rods.
- **Pen Lift Mechanism**: SG90 servo for Z-axis control with spring-loaded pen.
- **Open-Source**: Uses GRBL 1.1h firmware and Inkscape for G-code generation.
- **Customizable**: Modular design with 3D-printed components.
- **Affordable**: Built with salvaged and low-cost parts.

## Hardware
- **Microcontroller**: Arduino Uno
- **CNC Controller**: CNC Shield v3.0
- **Stepper Drivers**: 2x A4988 stepper drivers
- **Servo**: SG90 (Z-axis pen lift simulation)
- **Power Supply**: 12V 2A
- **Motion System**:
  - **X-Axis**: 450mm M8 linear rods, LM8UU bearings, GT2 belt, 16T pulleys
  - **Y-Axis**: 350mm M8 linear rods, LM8UU bearings, GT2 belt, 16T pulleys
  - **Z-Axis**: 3mm linear rods (salvaged from CD-ROM), spring-loaded pen mechanism

## Software
- **Firmware**: [GRBL 1.1h](https://github.com/gnea/grbl) for Arduino
- **G-code Generation**: [Inkscape](https://inkscape.org/) with G-code extensions
- **G-code Sender**: [Universal G-code Sender (UGS)](https://winder.github.io/ugs_website/)
- **Control Scripts**: Custom Processing scripts for manual control

### Software Setup
1. **GRBL Firmware**:
   - Upload GRBL 1.1h to the Arduino Uno using the Arduino IDE.
   - Configure GRBL settings (e.g., steps/mm, feed rates) via UGS or a terminal.
2. **Inkscape**:
   - Install Inkscape and the G-code extension (e.g., [Gcodetools](https://github.com/cnc-club/gcodetools)).
   - Convert vector designs to G-code paths.
3. **UGS**:
   - Connect to the Arduino via USB.
   - Load and send G-code files to the CNC plotter.
4. **Processing Scripts**:
   - Use custom Processing scripts for manual jogging and testing.

## 3D Printing Requirements
### Printer Settings
- **Layer Height**: 0.10–0.20mm
- **Infill**: Minimum 75%
- **Material**: Hatchbox Red PLA (recommended)
- **Critical Parts**:
  - Penholder
  - Slider
  - X/Y Supports

### Print Times
- **Longest Part**: ~9 hours (X/Y Supports)
- **Shortest Part**: ~30 minutes (Penholder)

### STL Files
Find the STL files in the [`stl/`](stl/) directory. Ensure proper bed adhesion and support settings for complex parts.

## Mechanical Assembly
### X-Axis Construction
1. Mount 470mm M8 threaded rod and 450mm linear rods to the frame.
2. Align LM8UU bearings using a rubber mallet for smooth motion.
3. Tension the GT2 belt with needle-nose pliers, securing it to the 16T pulley.

### Y-Axis Integration
1. Install 350mm linear rods and secure them to the frame.
2. Place 624zz bearings for smooth Y-axis motion.
3. Tension the GT2 belt and verify alignment with the X-axis.

### Z-Axis Mechanism
1. Attach 3mm linear rods (salvaged from CD-ROM) to the penholder.
2. Integrate the SG90 servo for pen lifting.
3. Adjust spring tension for consistent pen pressure and lift.

### Tips
- Use a level to ensure the frame is flat.
- Lubricate linear rods with light machine oil for smoother motion.
- Double-check belt tension to avoid skipping.

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/arduino-cnc-plotter.git
   cd arduino-cnc-plotter
   ```
2. **Upload GRBL Firmware**:
   - Open the Arduino IDE, load the GRBL 1.1h firmware, and upload it to the Arduino Uno.
3. **Assemble Hardware**:
   - Follow the [Mechanical Assembly](#mechanical-assembly) instructions.
4. **Install Software**:
   - Install Inkscape, UGS, and the Processing IDE.
   - Add G-code extensions to Inkscape.
5. **Test the Setup**:
   - Connect the Arduino to UGS.
   - Send a test G-code file to verify motion.

## Usage
1. **Create a Design**:
   - Use Inkscape to draw or import a vector design.
   - Export the design as G-code using the G-code extension.
2. **Send G-code**:
   - Open UGS and connect to the Arduino.
   - Load the G-code file and start the plotting process.
3. **Manual Control**:
   - Use the custom Processing scripts for jogging and calibration.
4. **Monitor**:
   - Ensure the pen lifts correctly and the X/Y axes move smoothly.
   - Adjust GRBL settings if needed (e.g., `$100` and `$101` for steps/mm).

Example G-code for a simple square:
```gcode
G21 ; Set units to mm
G90 ; Absolute positioning
G0 Z5 ; Lift pen
G0 X0 Y0 ; Move to origin
G1 Z0 ; Lower pen
G1 X50 Y0 ; Draw line
G1 X50 Y50 ; Draw line
G1 X0 Y50 ; Draw line
G1 X0 Y0 ; Complete square
G0 Z5 ; Lift pen
M5 ; End program
```

## Contributing
Contributions are welcome! Please:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit changes (`git commit -m 'Add your feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

Report issues or suggest improvements via the [Issues](https://github.com/yourusername/arduino-cnc-plotter/issues) tab.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Built with ❤️ by [Your Name](https://github.com/yourusername)