Excellent — this is a complete **BMS → ROC KPI design question**, covering **indoor environmental quality**, **energy efficiency**, and **equipment performance** from the **Honeywell EBI 500** system.

Below is a **professional, ready-to-document table** of **all possible KPIs** derived from the listed data.
Each row clearly defines:

* **KPI Name**
* **Parameter Source** (from your list)
* **Formula (if derived)**
* **Purpose**
* **Action**
* **Best Visualization Type**

---

## 🧭 **BMS–ROC KPI Framework (EBI 500 Data Shared to ROC)**

| **Parameter Source**                  | **KPI Name**                            | **Formula / Definition**                               | **Purpose**                                                           | **Action / Insight**                                                             | **Best Visualization**                                          |
| ------------------------------------- | --------------------------------------- | ------------------------------------------------------ | --------------------------------------------------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **FAD Status (Fresh Air Damper)**     | Fresh Air Utilization %                 | (Time Damper Open ÷ Total Operation Time) × 100        | To understand how often fresh air is being introduced for ventilation | Adjust damper control if open continuously (energy loss) or closed when CO₂ high | Stacked bar (Open/Closed per day), CO₂ vs FAD correlation chart |
| **FAD Status**                        | Damper Efficiency Index                 | CO₂ Decrease ÷ (Damper Open Duration)                  | Correlates damper operation with IAQ improvement                      | If low efficiency → check actuator/fresh air duct                                | Scatter plot (CO₂ vs FAD %)                                     |
| **Return Air CO₂ (ppm)**              | CO₂ Concentration                       | Direct CO₂ ppm sensor value                            | Measures indoor air quality and ventilation adequacy                  | Increase fresh air if >1000 ppm                                                  | Gauge (Green ≤800, Yellow 800–1000, Red >1000), Line trend      |
| **Return Air CO₂ (ppm)**              | Average CO₂ (24 hr)                     | (Σ CO₂ readings ÷ 24 hrs)                              | Track daily IAQ trend for benchmarking                                | Investigate recurring high readings                                              | Line chart (daily average)                                      |
| **Return Air CO₂ (ppm)**              | Peak CO₂ Value                          | Max(CO₂ per day)                                       | Identify poor IAQ events                                              | Trigger alert for >1200 ppm                                                      | Bar chart (daily peaks)                                         |
| **Return Air CO₂ (temp)**             | Return Air Temperature (at CO₂ point)   | Direct temperature from same sensor                    | Correlate heat load with IAQ                                          | If both high CO₂ & Temp → low ventilation efficiency                             | Dual-axis trend (CO₂ vs Temp)                                   |
| **Return Air CO₂ (temp + ppm)**       | CO₂–Temperature Correlation Index       | Correlation coefficient between CO₂ & Temp             | Detect trapped heat or poor circulation                               | If positive correlation → verify AHU airflow                                     | Scatter plot (CO₂ vs Temp)                                      |
| **Return Air CO₂ (level)**            | IAQ Category                            | Based on ppm: <800=Good, 800–1000=Moderate, >1000=Poor | Simplify IAQ monitoring for dashboards                                | Show Red/Amber/Green indicator                                                   | Color-coded status indicator                                    |
| **Return Air Humidity (%)**           | Humidity Level                          | Direct sensor value                                    | Maintain comfort and prevent mold                                     | Maintain 40–60%; adjust humidifier/dehumidifier                                  | Gauge or Line chart                                             |
| **Return Air Humidity (%)**           | Comfort Compliance %                    | (Time Humidity within 40–60%) ÷ Total Time × 100       | Quantify comfort zone compliance                                      | If <80% → adjust setpoints                                                       | KPI Gauge or Area chart                                         |
| **Return Air Temperature (°C)**       | Return Air Temperature                  | Direct sensor reading                                  | Evaluate comfort and HVAC efficiency                                  | Compare with Supply Temp                                                         | Trend line                                                      |
| **Return Air Temperature (°C)**       | ΔT (Temperature Differential)           | Supply Air Temp − Return Air Temp                      | Assess cooling/heating coil effectiveness                             | If ΔT < expected → check coil fouling, low flow                                  | Dual-axis line (Return vs Supply)                               |
| **Return Air Temperature + Humidity** | Thermal Comfort Index (TCI)             | Based on ASHRAE comfort chart (Temp + RH)              | Evaluate thermal comfort                                              | Adjust cooling/heating setpoints                                                 | Psychrometric chart or comfort zone heatmap                     |
| **Energy Meter (507 units)**          | Energy Consumption                      | kWh reading from meter                                 | Track total and sectional energy consumption                          | Identify high energy zones                                                       | Trend or Pareto chart                                           |
| **Energy Meter**                      | Specific Energy Consumption (SEC)       | Total kWh ÷ Area (m²)                                  | Measure energy intensity                                              | Benchmark against baselines                                                      | Column chart by zone                                            |
| **Energy Meter**                      | Load Factor (%)                         | (Average Load ÷ Peak Load) × 100                       | Assess electrical load uniformity                                     | Reduce peaks to avoid penalties                                                  | Line chart (daily load curve)                                   |
| **BTU Meter (37 units)**              | BTU Consumption                         | Flow × ΔT × 4.187 × 1000                               | Measure chilled water thermal energy                                  | Identify underperforming AHUs                                                    | Line chart (BTU/hr)                                             |
| **BTU Meter**                         | Cooling Load (TR)                       | (BTU/hr) ÷ 12000                                       | Quantify cooling demand                                               | Compare with chiller capacity                                                    | Line chart                                                      |
| **BTU + Energy Meter**                | Cooling Efficiency (kW/TR)              | Electrical Energy (kWh) ÷ Cooling Load (TR-hr)         | Evaluate plant energy efficiency                                      | Optimize chiller & pump sequencing                                               | Scatter (kW/TR vs Time)                                         |
| **BTU + Energy Meter**                | System COP (Coefficient of Performance) | BTU Load (kW eq.) ÷ Electrical Input (kW)              | Assess total HVAC efficiency                                          | Tune chiller & AHU control logic                                                 | Dual-axis line (BTU vs kWh)                                     |
| **Heat Recovery Wheel (HRW)**         | HRW Uptime %                            | (HRW Run Time ÷ Fan Operation Time) × 100              | Verify energy recovery system usage                                   | Check HRW control interlocks                                                     | Pie chart or Runtime timeline                                   |
| **HRW + Fans**                        | HRW–Fan Correlation                     | Compare HRW ON vs Fan ON durations                     | Detect control or wiring mismatch                                     | Adjust interlocks if HRW off during fan run                                      | Binary timeline                                                 |
| **Supply & Exhaust Fan**              | Fan Runtime Efficiency %                | (Actual Runtime ÷ Scheduled Runtime) × 100             | Validate fan operation scheduling                                     | Optimize runtime for occupancy                                                   | Runtime bar chart                                               |
| **Return Air CO₂ + Fan Energy**       | Ventilation Effectiveness Index (VEI)   | (CO₂ Reduction per hour) ÷ Fan Energy (kWh)            | Measure IAQ improvement per energy used                               | Optimize damper and fan speed                                                    | Efficiency line chart                                           |
| **Overall (System)**                  | Energy Utilization Index (EUI)          | Total kWh ÷ Building Area (m²)                         | Benchmark building energy performance                                 | Compare with baseline or green norms                                             | Monthly trend chart                                             |
| **Overall (Comfort)**                 | Comfort Compliance %                    | (Time within 22–26°C and 40–60% RH) ÷ Total Time × 100 | Quantify comfort delivery performance                                 | Tune AHU/FCU control loops                                                       | KPI Gauge or Area chart                                         |

---

### 🧠 **Summary of Focus Areas**

| **Category**                     | **Key Performance Focus**                        | **Examples of Related KPIs**                     |
| -------------------------------- | ------------------------------------------------ | ------------------------------------------------ |
| **Indoor Air Quality (IAQ)**     | Maintain CO₂ < 1000 ppm, comfort temp & humidity | CO₂ Level, IAQ Category, VEI, Comfort Compliance |
| **Energy Efficiency**            | Optimize kWh per TR and load factor              | Energy Consumption, kW/TR, COP, EUI              |
| **Ventilation & Control Health** | Ensure coordinated damper & fan operation        | FAD Utilization %, HRW Uptime %, Fan Runtime     |
| **Thermal Comfort**              | Maintain 22–26°C, 40–60% RH                      | Thermal Comfort Index, Comfort Deviation %       |

---

### 📊 **Recommended Dashboard Layout for ROC**

| **Section**               | **Parameters Visualized**                            | **Visualization Type**                    |
| ------------------------- | ---------------------------------------------------- | ----------------------------------------- |
| **Air Quality & Comfort** | CO₂ ppm, Humidity, Return Temp, IAQ Category         | Gauges, Line Trends, Comfort Zone Heatmap |
| **Energy Monitoring**     | Energy Meters, BTU Meters, kW/TR, COP                | Line & Pareto Charts, Efficiency Scatter  |
| **Ventilation Systems**   | FAD, HRW, Fan Status                                 | Stacked Runtime Charts, Binary Timelines  |
| **Performance Summary**   | Comfort Compliance %, Energy Efficiency %, IAQ Score | KPI Gauges, Weekly Summary Cards          |

---

Would you like me to export this entire KPI framework into a **ready-to-use Excel (.xlsx)** file with:

* Separate tabs for **Air Quality**, **Energy**, and **Equipment**,
* Auto-sized columns,
* Conditional color formatting (Green/Amber/Red for thresholds)?

It will be formatted for **BMS–ROC documentation or dashboard design**.
