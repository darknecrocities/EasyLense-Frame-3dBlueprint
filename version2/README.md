# Smart Glasses Prototype - Version 2 (Production & Tolerance Testing)

This directory houses the optimized production package of the smart glasses. The focus has shifted from assembly illustration to manufacturing validation, print nesting, and improved ergonomic wearability.

## 🚀 Entry Point

To compile the flat print package of production parts:
```bash
main.kcl
```
*(This loads the layout from `print_ready_parts.kcl` containing the structural printable components).*

## 🧪 ESP32 Clearance Tolerance Coupon

To ensure your 3D printer successfully prints the pocket snaps, sliding covers, screw slots, and cable pathways:
1. Compile and print:
   ```bash
   esp32_tolerance_coupon.kcl
   ```
2. Fit your ESP32-CAM and LiPo charging boards into the printed coupon.
3. Verify that cover panels slide in smoothly.
4. If adjustments are required, update variables in `parameters.kcl` and reprint the coupon before printing the full frame.

## 📁 Key File Changes vs Version 1

- **`parameters.kcl`**: Refined tolerances and added ergonomic `wearableTempleToeInAngle` (3deg) to fold temple tips slightly inward for a better head-fit.
- **`esp32_tolerance_coupon.kcl`**: The calibration tray representing a snippet of the controller pocket.
- **`print_ready_parts.kcl`**: Clean, printable component arrangement for slicing.
