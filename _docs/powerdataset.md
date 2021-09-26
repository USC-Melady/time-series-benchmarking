---
title: Power Dataset
permalink: /datasets/power/
---
### Minute-level Load and Renewable ###
- File Name
  - ISO_zone_#.csv: `CAISO_zone_1.csv` contains minute-level load, renewable and weather data from 2018 to 2020 in the zone 1 of CAISO.
- Field Description
  - Field `time`: Time of minute resolution.
  - Field `load_power`: Normalized load power.
  - Field `wind_power`: Normalized wind turbine power.
  - Field `solar_power`: Normalized solar PV power.
  - Field `DHI`: Direct normal irradiance.
  - Field `DNI`: Diffuse horizontal irradiance.
  - Field `GHI`: Global horizontal irradiance.
  - Field `Dew Point`: Dew point in degree Celsius.
  - Field `Solar Zeinth Angle`: The angle between the sun's rays and the vertical direction in degree.
  - Field `Wind Speed`: Wind speed (m/s).
  - Field `Relative Humidity`: Relative humidity (%).
  - Field `Temperature`: Temperature in degree Celsius.

### Minute-level PMU Measurements ###
- File Name
  - case #: The `case 0` folder contains all data of scenario setting #0.
    - pf_input_#.txt: Selected load, renewable and solar generation for the simulation.
    - pf_result_#.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
- Filed Description
  - Field `time`: Time of minute resolution.
  - Field `Vm_###`: Voltage magnitude (p.u.) at the bus ### in the simulated model.
  - Field `Va_###`: Voltage angle (rad) at the bus ### in the simulated model.
  - Field `P_#_#_#`: `P_3_4_1` means the active power transferring in the #1 branch from the bus 3 to 4.
  - Field `Q_#_#_#`: `Q_5_20_1` means the reactive power transferring in the #1 branch from the bus 5 to 20.

### Millisecond-level PMU Measurements ###
- File Name
  - Forced Oscillation: The folder contains all forced oscillation cases.
    - row_#: The folder contains all data of the disturbance scenario #.
      - dist.csv: Three-phased voltage at nodes in the distribution system via T+D simualtion.
      - info.csv: This file contains the start time, end time, location and type of the disturbance.
      - trans.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
  - Natural Oscillation: The folder contains all natural oscillation cases.
    - row_#: The folder contains all data of the disturbance scenario #.
      - dist.csv: Three-phased voltage at nodes in the distribution system via T+D simualtion.
      - info.csv: This file contains the start time, end time, location and type of the disturbance.
      - trans.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
- Filed Description
  > trans.csv
  - Field `Time(s)`: Time of millisecond resolution.
  - Field `VOLT ###`: Voltage magnitude (p.u.) at the bus ### in the transmission model.
  - Field `POWR ### TO ### CKT #`: `POWR 151 TO 152 CKT '1 '` means the active power transferring in the #1 branch from the bus 151 to 152.
  - Field `VARS ### TO ### CKT #`: `VARS 151 TO 152 CKT '1 '` means the reactive power transferring in the #1 branch from the bus 151 to 152.
  > dist.csv
  - Field `Time(s)`: Time of millisecond resolution.
  - Field `####.###.#`: `3005.633.1` means per-unit voltage magnitude of the phase A at the bus 633 of the distribution grid, the one connecting to the bus 3005 in the transmission system.