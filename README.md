# RSCL_CUBESAT_EPS
# CubeSat Electric Power System (EPS) – Senior Design Project

**Author:** Antonuos Kerollos  

## Overview
This repository contains the design files for a high-efficiency Electric Power System (EPS) intended for CubeSat missions.  
The EPS is engineered to:
- Harvest solar energy efficiently.
- Manage and protect power distribution.
- Extend battery life through intelligent switching.
- Operate reliably under harsh thermal and radiation conditions in space.

The project implements:
- Maximum Power Point Tracking (MPPT) charging.
- Custom analog automatic battery switching.
- Regulated power outputs for satellite subsystems.
- Real-time monitoring of voltage, current, and power.
- Radiation-tolerant, microcontroller-minimized control.

---

## System Architecture

**Key Subsystems:**
1. **Solar Energy Harvesting:**  
   - Monocrystalline solar panels arranged in deployable arrays for up to **5.5 W** generation under full sunlight.
   - Series pairs configuration for optimal efficiency.

2. **Battery Management:**  
   - Two battery banks (20 Ah total) with alternating charge/discharge cycles to avoid overcharging and extend lifespan.
   - Custom switching circuit using ideal diodes and comparators.

3. **Power Regulation & Distribution:**  
   - 3.3 V and 5 V regulated rails for different CubeSat loads.
   - High-side power switch for load control and protection.

4. **Monitoring & Fault Protection:**  
   - INA219 sensors for voltage, current, and power telemetry.
   - Temperature sensors for solar charger compensation.
   - Reverse current protection from solar panel transients.

5. **Deployment & Thermal Management:**  
   - Burn wire deployment for antennas and solar panels.
   - Battery heater circuit to maintain optimal operating temperature.

---
<img width="2724" height="1333" alt="eps_block_diagram" src="https://github.com/user-attachments/assets/831d38fd-ddaa-4bf9-a6d9-41fa69f4dce5" />

## Component List & Circuit Roles

| Component | Type | Purpose in EPS |
|-----------|------|----------------|
| **SM401K08L** | Monocrystalline Solar Cell | High-efficiency power generation (702 mW @ 5.53 V each). |
| **LT3652** | MPPT Charger IC | Tracks solar panel maximum power point and charges battery efficiently. |
| **LTC4415** | Ideal Diode Power Path Controller | Switches between battery banks with minimal loss. |
| **TLV3012B** | Comparator | Monitors solar panel voltage to control battery switching logic. |
| **LTC3113** | DC-DC Converter | Regulates output to stable 3.3 V for CubeSat electronics. |
| **TPS61023** | Boost Converter | Regulates output to 5 V for specific subsystems. |
| **TPS1HC30** | High-Side Power Switch | Controls and protects loads from overcurrent events. |
| **INA219** | Power Monitor | Measures voltage, current, and power for real-time telemetry. |
| **TCAL9539** | I²C Expander | Extends microcontroller I/O for deployment and thermal systems. |
| **LM74610** | Ideal Diode | Prevents reverse current from solar panels. |
| **Battery Heater Circuit** | Custom | Maintains battery temperature in optimal range. |
| **Burn Wire Deployment Circuit** | Custom | Releases antennas and solar panels on command. |

---
## File Structure

