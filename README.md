# ESP32-CAM Smart Glasses CAD Project (KCL)

An open-source, parametrically-designed, 3D-printable smart glasses frame built using **KCL (KittyCAD Language)**. This project houses two design iterations (`version1` and `version2`) of smart glasses optimized for housing an **ESP32-CAM**, rechargeable battery, charger modules, and custom routing pathways.

---

## 🕶️ Project Overview

This project provides a fully parametric CAD blueprint and print package for creating DIY smart glasses. By leveraging KCL's scripting capabilities, all clearances, frame dimensions, temple lengths, and fastener socket sizes can be customized by simply tweaking variables in the parameters file.

### Key Features
- **ESP32-CAM Integration**: Optimized compartment in the right temple to hold the microcontroller board securely.
- **Parametric Ergonomics**: Dynamic temple toe-in angle, bridge width, lens dimensions, and frame thicknesses.
- **Wire Routing & Cable Management**: Built-in strain reliefs, entry reliefs, and wiring channels for routing cables from the front frame camera to the controllers.
- **Exploded Service & Showcase Views**: Presentation layers in KCL showing how components fit together, complete with dimension annotations and fastener calls.
- **Tolerance Calibration**: Test coupons to verify printer tolerances before committing to full multi-hour temple prints.

---

## 📁 Repository Structure

The project is split into two versions, representing the evolution from a presentation-heavy assembly mockup to a print-optimized, tolerance-calibrated iteration:

```
tutorial-project/
├── version1/                      # Complete Assembly & Showcase Mockup
│   ├── main.kcl                   # Main presentation entrypoint
│   ├── parameters.kcl             # Global design variables (colors, sizes)
│   ├── front_frame.kcl            # Front glass frame CAD model
│   ├── left_temple.kcl            # Left temple arm CAD model
│   ├── right_temple.kcl           # Right temple arm (ESP32-CAM pocket)
│   ├── left_covers.kcl            # Covers for the left temple compartment
│   ├── right_covers.kcl           # Covers for the right temple compartment
│   ├── hardware.kcl               # M2 screws and heat-set insert mockups
│   ├── front_electronics.kcl      # Camera/sensor electronics model
│   ├── left_electronics.kcl       # Battery housing electronics model
│   ├── right_electronics.kcl      # ESP32-CAM board/connector models
│   ├── finished_showcase.kcl      # Closed render layout of the glasses
│   ├── dimension_blueprint.kcl    # Blueprints showing dimensional annotations
│   ├── fastener_callouts.kcl      # Assembly callouts pointing to hardware positions
│   ├── print_orientation_layout.cl# Printable parts FDM bed alignment layout
│   └── project.toml               # KCL project configuration
│
└── version2/                      # Print-Optimized & Tolerance-Calibrated Package
    ├── main.kcl                   # Minimal entrypoint showing print-ready parts
    ├── parameters.kcl             # Refined parameters with wearable toe-in angles
    ├── esp32_tolerance_coupon.kcl # Clearances test coupon for ESP32 compartment
    ├── front_frame.kcl            # Updated front frame with refined camera mounts
    ├── left_temple.kcl            # Left temple arm with refined clearances
    ├── right_temple.kcl           # Right temple arm with optimized ventilation slots
    ├── left_covers.kcl            # Left compartment covers
    ├── right_covers.kcl           # Right compartment covers
    ├── printable_assembly.kcl     # Printable part assembly references
    ├── print_ready_parts.kcl      # Flattened print layout configuration
    └── project.toml               # KCL project configuration
```

---

## 🔧 Design Iterations

### Version 1: Exploded Showcase & Assembly Blueprint
- **Focus**: Modeling the complete system architecture, assembly visualization, and presentation graphics.
- **Assembly View**: Features an exploded service view separating hardware, electronics, covers, and structural arms.
- **Dimensioning**: Contains blueprint overlays depicting model specifications.
- **Fasteners**: Includes interactive lines/annotations identifying mounting positions for M2 screws.

### Version 2: Print & Fit Calibration (Production Focus)
- **Focus**: Optimizing the design for real-world FDM 3D printing and fit comfort.
- **Wearable Fit**: Introduces ergonomic parameters like `wearableTempleToeInAngle` (defaulting to `3deg`) to curve the temples slightly inward for a secure fit on the wearer's head.
- **ESP32 Compartment Calibration**: Includes the `esp32_tolerance_coupon.kcl` test print. This creates a small compartment replica containing:
  - FDM clearance test posts.
  - Cover slide rails and M2 pilot holes.
  - Vent slot sizes and wire hooks.
  - USB charging board standoffs.
  *Use this test coupon to verify your printer's dimensional accuracy before printing the entire right temple.*
- **Print Optimization**: Simplified main assembly files to target clean `.STL`/`.STEP` output layouts.

---

## 🛠️ Usage Instructions

### 1. View & Edit in KittyCAD/KCL Editor
You can load these files into any KCL-compatible modeling viewer or the KittyCAD editor:
- Open `version1/main.kcl` to view the comprehensive presentation layout (includes showcase, exploded view, blueprints, and layouts).
- Open `version2/main.kcl` to view the final STL-ready, nested print layout.

### 2. Calibrating Tolerances (Version 2)
Prior to running a full print of the temples (which host thin walls and precise pockets):
1. Compile and print the coupon model in `version2/esp32_tolerance_coupon.kcl`.
2. Check the fitment of your ESP32-CAM board, wire routes, and sliding cover pieces.
3. If necessary, adjust tolerances in `version2/parameters.kcl` (e.g., `espFdmFitClearance`, `wallThickness`, `m2HeatSetInsertHoleDiameter`).

### 3. Slicing and Printing
- Export the parts from KCL (supports STEP, STL, and other formats).
- Recommended Slicing Settings:
  - **Layer Height**: 0.15mm - 0.2mm
  - **Infill**: 20% - 30% (gyro/grid pattern)
  - **Supports**: Required for the temple arms' internal pocket overhangs depending on orientation.
  - **Material**: PLA/PETG (recommended matte black or charcoal colors like the specified parameter HEX values).

---

## 🔩 Hardware & Bill of Materials (BOM)

- **Microcontroller**: ESP32-CAM board (approx. 43mm x 28mm).
- **USB Board**: Micro-USB or USB-C LiPo charger board (e.g., TP4056).
- **Battery**: Slim lithium-polymer rechargeable battery.
- **Screws**: M2 screws (typically 10mm length for covers).
- **Inserts**: M2 threaded heat-set inserts (3.5mm outer diameter, 4mm length).
