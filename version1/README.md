# Smart Glasses Prototype - Version 1 (Mockup & Blueprint Assembly)

This directory contains the initial architectural mockup of the ESP32-CAM smart glasses. It is structured to generate an informative, multi-panel CAD presentation containing:
1. **Assembled View**: The fully built glasses frame with electronics nested inside.
2. **Exploded View**: Displaced components (temples, covers, electronics, screws) showing how the assembly fits together.
3. **Blueprint Panels**: Projected dimensions and annotation blueprints.
4. **Fastener Callouts**: Visual callouts illustrating screw and insert targets.
5. **Showcase Shell**: A render-ready closed configuration.
6. **Print Layout**: Parts nested onto a standard 220mm x 220mm FDM bed.

## 🚀 Entry Point

To render the full design presentation, run or compile:
```bash
main.kcl
```

## 📁 File Structure

- **`main.kcl`**: The master orchestration script compiling all assemblies and displacement panels.
- **`parameters.kcl`**: Design parameters (e.g., lens size, frame width, color codes).
- **`front_frame.kcl`**: Front glasses frames.
- **`left_temple.kcl` / `right_temple.kcl`**: Side arms.
- **`left_covers.kcl` / `right_covers.kcl`**: Sliding compartment covers.
- **`front_electronics.kcl` / `left_electronics.kcl` / `right_electronics.kcl`**: Volumes representing the physical sensors, boards, and batteries.
- **`hardware.kcl`**: Screws, washers, and insert fasteners.
- **`dimension_blueprint.kcl`**: Dimensions overlays.
- **`fastener_callouts.kcl`**: Connector annotation panel.
- **`print_orientation_layout.kcl`**: Nested printable configuration.
