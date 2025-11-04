Excellent — this is a very real-world BMS–ROC (Building Management System → Remote Operations Center) KPI definition scenario.
Let’s define **Key Performance Indicators (KPIs)** for the parameters you listed from the EBI 500 server, organized by category (Air Quality, Energy, and Equipment Performance).
Each KPI includes:

* **Purpose** – why it’s tracked
* **Action** – what operations/maintenance teams should do based on it
* **Formula (if derived)** – how it’s calculated
* **Visualization** – recommended chart or dashboard element

---

## 🧩 1. Air Quality and Comfort KPIs

### 1.1 **Return Air CO₂ Level (ppm)**

* **Purpose:** Monitor indoor air quality and ventilation effectiveness.
* **Action:**

  * If CO₂ > 1000 ppm → increase fresh air intake or inspect dampers/fans.
  * If < 400 ppm → excessive ventilation → energy waste.
* **Formula:** Direct sensor value.
* **Visualization:**

  * **Line chart (trend over 24 hrs)** per zone
  * **Gauge indicator** (green ≤ 800, yellow 800–1000, red >1000)

---

### 1.2 **Return Air Humidity (%)**

* **Purpose:** Track occupant comfort and prevent mold/corrosion.
* **Action:**

  * Maintain between 40–60%.
  * If high → check dehumidifier/coil temperature.
  * If low → verify humidifier.
* **Formula:** Direct sensor value.
* **Visualization:**

  * **Dual-axis line chart** (Humidity vs Return Air Temp)
  * **Gauge chart** with comfort band

---

### 1.3 **Return Air Temperature (°C)**

* **Purpose:** Maintain thermal comfort and detect HVAC issues.
* **Action:**

  * Compare with supply air temperature.
  * Sudden rise → possible coil or damper issue.
* **Formula:** Direct sensor value.
* **Derived KPI:**

  * **Temperature Differential (ΔT)** = Supply Air Temp − Return Air Temp
  * Indicates cooling or heating effectiveness.
* **Visualization:**

  * **Line chart** for Return, Supply, and ΔT
  * **Heatmap** (floor vs time of day)

---

### 1.4 **Fresh Air Damper (FAD) Status**

* **Purpose:** Verify ventilation system control and IAQ compliance.
* **Action:**

  * If CO₂ high and FAD closed → control fault.
  * If CO₂ low and FAD open continuously → energy waste.
* **Formula:** Binary (0=Closed, 1=Open) or % opening.
* **Derived KPI:**

  * **Fresh Air Utilization %** = (Time FAD Open ÷ Total Operation Time) × 100
* **Visualization:**

  * **Stacked bar** (Open/Closed durations per day)
  * **Correlation chart** (FAD % vs CO₂ ppm)

---

## ⚡ 2. Energy and Efficiency KPIs

### 2.1 **Energy Meter (507 meters)**

* **Purpose:** Track total and sectional electrical consumption.
* **Action:**

  * Identify high-load areas.
  * Compare daily, weekly, monthly trends.
* **Formula:** Direct meter readings.
* **Derived KPIs:**

  1. **Specific Energy Consumption (SEC)** = Total kWh ÷ Area (m²)
  2. **Energy Intensity** = Total kWh ÷ Cooling Load (TR-hours)
  3. **Load Factor (%)** = (Average Load ÷ Peak Load) × 100
* **Visualization:**

  * **Stacked bar chart** (Energy by floor/system)
  * **Trend chart** for kWh over time
  * **Pareto chart** for top 10 consuming meters

---

### 2.2 **BTU Meter (37 units)**

* **Purpose:** Quantify chilled water/thermal energy usage.
* **Action:**

  * Identify underperforming AHUs or zones.
  * Optimize chilled water distribution.
* **Formula:**

  * **BTU Consumption** = Flow (m³/hr) × ΔT (°C) × 4.187 × 1000
  * **Cooling Load (TR)** = (BTU/hr) ÷ 12000
* **Derived KPI:**

  * **Cooling Efficiency (kW/TR)** = Electrical Energy (kWh) ÷ Cooling Load (TR-hours)
* **Visualization:**

  * **Line chart** (Cooling Load vs Power Consumption)
  * **Scatter plot** (ΔT vs Flow) to detect imbalance

---

### 2.3 **Energy vs BTU Correlation**

* **Purpose:** Verify that electrical energy consumption aligns with thermal load.
* **Action:**

  * High kWh but low BTU → inefficiency in chillers or pumps.
* **Formula:**

  * **System COP** = BTU Load (kW equivalent) ÷ Electrical Input (kW)
* **Visualization:**

  * **Dual-axis line** (BTU vs kWh)
  * **Efficiency trend** over time

---

## 🔁 3. Equipment & Process KPIs

### 3.1 **Heat Recovery Wheel (HRW) Run Status**

* **Purpose:** Ensure energy recovery during ventilation operation.
* **Action:**

  * If HRW OFF while both supply & exhaust fans ON → energy loss.
  * Monitor HRW uptime vs fan runtime.
* **Formula:**

  * **HRW Uptime %** = (HRW Run Time ÷ Fan Operation Time) × 100
* **Visualization:**

  * **Stacked time graph** (Fan vs HRW status)
  * **Pie chart** for uptime %

---

### 3.2 **Supply and Exhaust Fan Runtime**

* **Purpose:** Validate fan operation schedules and detect failures.
* **Action:**

  * Deviations → inspect control logic or actuator issues.
* **Formula:** Direct runtime logs.
* **Derived KPI:**

  * **Runtime Efficiency %** = (Actual Runtime ÷ Scheduled Runtime) × 100
* **Visualization:**

  * **Timeline view** or **bar chart** (hours per day)

---

## 🌡️ 4. Combined Environmental Efficiency KPIs

| KPI                                       | Formula                                                    | Purpose                                    | Action                    | Visualization                               |
| ----------------------------------------- | ---------------------------------------------------------- | ------------------------------------------ | ------------------------- | ------------------------------------------- |
| **Ventilation Effectiveness Index (VEI)** | (CO₂ Reduction per hour) ÷ Fan Energy (kWh)                | Evaluate air exchange efficiency vs energy | Tune damper and fan speed | Line chart                                  |
| **Thermal Comfort Index (TCI)**           | Based on Return Air Temp + Humidity vs ASHRAE comfort zone | Occupant comfort evaluation                | Adjust setpoints          | Psychrometric chart or comfort zone heatmap |
| **Energy Utilization Index (EUI)**        | Total kWh ÷ Building Area (m²)                             | Benchmark energy intensity                 | Compare with baseline     | Monthly trend chart                         |

---

## 📊 Recommended Dashboard Layout (for ROC)

| Section                  | KPIs                                   | Visualization Type                |
| ------------------------ | -------------------------------------- | --------------------------------- |
| **Air Quality**          | CO₂, Humidity, Temperature, FAD Status | Gauges, Trend lines               |
| **Energy**               | Energy Meters, BTU Meters, kW/TR       | Trend lines, Pareto bars          |
| **Equipment Health**     | HRW, Fans, Dampers                     | Status timelines                  |
| **Efficiency & Comfort** | COP, ΔT, VEI, TCI                      | Combined trend + comfort zone map |

---

Would you like me to structure this into a **tabular Excel format** (KPI | Description | Formula | Purpose | Action | Visualization)?
That’s the format typically used for BMS–ROC handover documentation.
Here’s the structured **tabular format** version of all KPIs related to the parameters from your BMS (EBI 500) → ROC data.
This table is formatted so you can directly convert or export it to Excel or Power BI.

---

### 🧭 **BMS–ROC KPI Framework**

| **Parameter**                     | **KPI Name**                          | **Formula / Definition**                             | **Purpose**                                         | **Action**                                                       | **Best Visualization**                                           |
| --------------------------------- | ------------------------------------- | ---------------------------------------------------- | --------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Return Air CO₂**                | CO₂ Level (ppm)                       | Direct sensor value                                  | Monitor indoor air quality and ventilation adequacy | Increase fresh air if >1000 ppm; optimize ventilation if too low | Gauge (Green ≤800, Yellow 800–1000, Red >1000), Line trend       |
|                                   | Fresh Air Utilization %               | (Time FAD Open ÷ Total Time) × 100                   | Assess ventilation control responsiveness           | Adjust damper control logic if FAD open continuously             | Stacked bar (Open/Closed duration), CO₂ vs FAD correlation chart |
| **Return Air Humidity**           | Humidity Level (%)                    | Direct sensor value                                  | Ensure occupant comfort and prevent mold/corrosion  | Maintain 40–60%; check dehumidifier/humidifier if outside range  | Line chart (Humidity vs Time), Gauge                             |
|                                   | Thermal Comfort Index (TCI)           | Based on Return Air Temp & RH vs ASHRAE comfort zone | Evaluate thermal comfort conditions                 | Adjust temperature/humidity setpoints                            | Psychrometric chart or comfort zone heatmap                      |
| **Return Air Temperature**        | Return Air Temperature (°C)           | Direct sensor value                                  | Monitor comfort and detect HVAC inefficiency        | Compare with supply temp; check coil/damper issues if abnormal   | Trend line (Return vs Supply Temp)                               |
|                                   | ΔT (Temperature Differential)         | Supply Air Temp − Return Air Temp                    | Assess cooling/heating effectiveness                | Low ΔT → check coil fouling or low flow                          | Dual line chart                                                  |
| **Fresh Air Damper (FAD) Status** | Damper Open Ratio (%)                 | (Damper Open Time ÷ Total Operation Time) × 100      | Ensure correct ventilation scheduling               | Adjust damper actuator/fresh air settings                        | Stacked time chart, CO₂ vs FAD scatter                           |
| **Energy Meter (507)**            | Energy Consumption (kWh)              | Meter reading over time                              | Track electrical energy usage                       | Identify high-load areas, schedule load optimization             | Trend line, Pareto bar chart                                     |
|                                   | Specific Energy Consumption (SEC)     | Total kWh ÷ Area (m²)                                | Benchmark energy performance per area               | Reduce by improving lighting/HVAC efficiency                     | Column chart by building/zone                                    |
|                                   | Load Factor (%)                       | (Average Load ÷ Peak Load) × 100                     | Assess load distribution                            | Flatten peaks via scheduling                                     | Line chart (Daily/Weekly load pattern)                           |
| **BTU Meter (37)**                | BTU Consumption                       | Flow × ΔT × 4.187 × 1000                             | Quantify thermal energy usage                       | Identify high load or low ΔT zones                               | Trend line (BTU/hr)                                              |
|                                   | Cooling Load (TR)                     | (BTU/hr) ÷ 12000                                     | Calculate refrigeration tonnage                     | Match against chiller performance                                | Trend or real-time gauge                                         |
|                                   | Cooling Efficiency (kW/TR)            | Electrical Energy ÷ Cooling Load                     | Assess chiller plant efficiency                     | Optimize setpoints, check VFD or pumps                           | Scatter or line chart (Efficiency vs Time)                       |
| **Energy vs BTU**                 | System COP                            | BTU Load (kW equivalent) ÷ Electrical Input (kW)     | Measure overall system performance                  | Tune chiller/HRW operations                                      | Dual-axis line (kWh vs BTU)                                      |
| **Heat Recovery Wheel (HRW)**     | HRW Uptime %                          | (HRW Run Time ÷ Fan Operation Time) × 100            | Ensure energy recovery system utilization           | Check control logic if HRW off during fan operation              | Pie chart or stacked runtime graph                               |
|                                   | HRW-Fan Correlation                   | Binary comparison (HRW ON vs Fan ON)                 | Detect bypass or control failure                    | Verify interlocks                                                | Status timeline                                                  |
| **Supply & Exhaust Fans**         | Fan Runtime Efficiency %              | (Actual Runtime ÷ Scheduled Runtime) × 100           | Validate fan operation schedules                    | Adjust control timing to save energy                             | Runtime bar chart (hours/day)                                    |
|                                   | Ventilation Effectiveness Index (VEI) | (CO₂ Reduction per hr) ÷ Fan Energy (kWh)            | Measure air exchange efficiency per energy used     | Optimize fan speed and damper logic                              | Line trend                                                       |
| **Overall System**                | Energy Utilization Index (EUI)        | Total Energy (kWh) ÷ Building Area (m²)              | Benchmark building energy intensity                 | Compare with baseline or green standards                         | Monthly trend chart                                              |
|                                   | Comfort Compliance %                  | (Time within Comfort Band ÷ Total Time) × 100        | Evaluate operational comfort performance            | Recalibrate control loops if below target                        | Area chart or KPI gauge                                          |

---

Would you like me to generate this table as a **downloadable Excel (.xlsx)** file so you can import it into your BMS–ROC documentation or dashboard setup?



