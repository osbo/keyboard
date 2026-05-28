# Handwired Keyboard

A wireless, modular handwired mechanical keyboard with a laser-cut bent-acrylic chassis, integrated trackpad, and rotary encoders wired into the switch matrix.

![Render 1](Render%201.png)

## Hardware

The body is a single sheet of acrylic, cut on a laser cutter and heat-bent into the keyboard's compound angle. The switch matrix is handwired with 16 AWG enamelled copper magnet wire — heavy enough that the matrix lines double as structural support behind the plate. Magnetic-pogo connectors latch the numpad, trackpad, and battery modules to the main board, so they hot-swap without re-pairing the host.

Rotary encoders share columns with regular switches by exploiting matrix scan timing: an encoder's two phases are wired to adjacent rows of the same column, and the firmware reads phase transitions inside the normal scan cycle. The result is full encoder support without burning extra GPIO. Guitar-style detented knobs supply the tactile resolution.

The trackpad is a custom dual-axis resistive panel, read through the MCU's ADC and integrated to a relative pointer in firmware.

## Modules

- **Main** — alpha block + thumb cluster, handwired matrix
- **Numpad** — detachable, magnetically aligned, joins the same composite USB HID device
- **Trackpad** — dual-axis resistive panel, pogo-connected
- **Battery** — wireless power, hot-swappable

## Software

Firmware is built on **QMK**, customised for the encoder-in-matrix scan and the resistive-trackpad analog frontend. The host sees a single composite HID device regardless of which modules are attached.

## Files

- `SVGs/` — laser-cut paths for the main plate, numpad plate, trackpad plate, fasteners, and feet
- `Final Renders.blend` — Blender file for the renders above
- `Handwired Keyboard.xlsx` — bill of materials

![Render 2](Render%202.png)
![Render 3](Render%203.png)

## License

MIT — see [LICENSE](LICENSE).
