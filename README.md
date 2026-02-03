# FOC
This code is  FOC algorithm based on B-G431B-ESC1 development board with A2212 13T(1000KV) BLDC motor and AS5047 magnetic encoder.

This code is refactorized version from prototype branch.

------
### File Structure
Core
- **Inc**
    - **main.h**
    - **foc_core.h**  (FOC state structure, FOC core algorithm)
    - **foc_hw.h** (HW related structure and variables)
    - **pid.h** (PID controller structure)
    - **smo.h** (Sliding Mode Observer related structure)
    - **profiler.h** (S-Curve motion profiler)
- Src
    - **main.c** (Initialization, main loop, interrupt callback)
    - **foc_core.c** (Clarke/Park Transformation, SVPWM calculation, Cascade control loop)
    - **foc_hw.c** (ADC calibration, ADC current reading, encoder calibration, encoder reading, PWM output)
    - **pid.c** (PID controller calculation function)
    - **smo.c** (SMO update functions)
    - **profiler.c** (S-Curve update functions)
    
### Included Functions
- Main FOC algorithm
  - FOC calculation (including Park, Clarke transform)
  - SVPWM (Space-Vector PWM)
- Rotor position sensing
  - SPI magnetic encoder (Bit-Banging method)
  - ~~Incremental magnetic encoder (HW supported ABZ method)~~
  - ~~Sensorless (SMO, Sliding Mode Observer)~~
- Control logic
  - Cascade (Position & Velocity)
  - ~~S-curve profile (Position & Velocity)~~

-----
### Additional Message
- Main FOC with cascade control logic is now available in the main.c file.
- SMO and S-Curve will be added in later version.
