# Lab Testing Plan for Adaptive-Neuromorphic-E-Skin-Readout-IC

## Testbench Setup
Testing will use a breadboard or custom PCB powered by a 3.3V DC supply. The campus Signal Generator will provide the sensor inputs and clock signals, while a 4-Channel Oscilloscope will be used to record signal dynamics in real-time.

## Pins & Equipment

| Pin | Direction | Type | Testbench Source / Measurement |
| :--- | :--- | :--- | :--- |
| **vdd!** | In | Power | 3.3V DC Power Supply |
| **gnd!** | In | Ground | Lab Common Ground |
| **clk** | In | Digital | Signal Generator (Square Wave) |
| **SenseA** | In | Analog | Signal Generator or Physical MEMS Sensor |
| **Vbiadapt**| In | Analog | Precision DC Source / Potentiometer |
| **Vleak** | In | Analog | Precision DC Source / Potentiometer |
| **Vmem** | Out | Analog | Oscilloscope (Channel 1) |
| **Vadapt** | Out | Analog | Oscilloscope (Channel 2) |
| **ST** | Out | Digital | Oscilloscope (Channel 3) / Logic Analyzer |
| **Vout** | Bidir | Analog | Oscilloscope (Channel 4) / Multimeter |

## Testing Steps
1. **Bring-up:** Apply 3.3V and monitor the initial current draw to detect any potential short-circuits.
2. **Synthetic Test & Sweeping:** Feed the Signal Generator into `SenseA` and perform a ~15-point voltage sweep on the `Vleak`/`Vbiadapt` pins. Monitor the resulting spike frequency changes on the Oscilloscope.
3. **Real Sensor Integration:** Connect `SenseA` to the actual physical MEMS E-Skin sensor, apply real physical pressure, and record the circuit's response.

## Final Validation
Export the raw Oscilloscope capture data into a CSV format, then plot and compare the curve shapes and Mean Squared Error (MSE) against your Xschem simulation results.