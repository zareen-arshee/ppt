Here’s the **detailed table** for your next set of KPIs —
(**Performance Degradation Ratio, Transmission Line Loss, Reactive Power Loss, Power Curve Analysis, and Active Power vs Irradiance Chart**) —
formatted exactly like your earlier tables:

---

### 🌞 **Renewable Asset Management – Advanced Performance KPIs**

| **Visual Component** | **KPI**                                 | **Description**                                                                                                                                                                             | **Unit** | **Raw Data Required**                                                                                      | **Calculation Logic**                                                                                 | **Analytics Granularity**       | **Benefit**                                                                                                          |
| -------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **KPI**              | **Performance Degradation Ratio (PDR)** | Measures the long-term decline in plant performance (e.g., module degradation) by comparing actual generation with expected generation under similar irradiance and temperature conditions. | %        | Historical energy generation data, irradiance, temperature, expected generation                            | PDR = [(Expected Generation − Actual Generation) / Expected Generation] × 100                         | Monthly / Yearly / Plant Level  | Detects long-term efficiency loss in modules or inverters; helps plan preventive maintenance and module replacement. |
| **KPI**              | **Transmission Line Loss**              | Quantifies energy loss that occurs during transmission from the plant to the grid substation due to resistance and distance in cables/lines.                                                | %        | Export meter reading (at substation), inverter output meter, line parameters (resistance, length, voltage) | Transmission Loss (%) = [(Inverter Output − Export Meter Reading) / Inverter Output] × 100            | Daily / Monthly / Line Level    | Identifies transmission inefficiencies; supports optimization of evacuation systems and loss minimization.           |
| **KPI**              | **Reactive Power Loss**                 | Indicates the amount of reactive power consumed or lost in maintaining voltage stability in the electrical network.                                                                         | kVAr / % | Reactive power (Q) from inverter, apparent power (S) from meter                                            | Reactive Power Loss (%) = (Q² / S²) × 100                                                             | Inverter / Feeder / Plant Level | Helps maintain grid power factor compliance; reduces penalties and improves grid stability.                          |
| **KPI**              | **Power Curve Analysis**                | Compares actual power output vs expected theoretical power curve (based on irradiance and module efficiency) to identify underperforming assets.                                            | —        | Active power output, irradiance, temperature, wind speed (if hybrid), module specs                         | Compare actual vs expected power curve under standard test conditions (STC)                           | Inverter / String / Plant Level | Detects early-stage faults in modules, strings, or inverters by comparing deviations from expected curve.            |
| **KPI**              | **Active Power vs Irradiance Chart**    | Correlates active power generation with incident irradiance to visualize performance trends and detect shading, soiling, or equipment faults.                                               | —        | Active power (P), irradiance (GHI/POA), timestamp                                                          | Scatter plot of Active Power (Y-axis) vs Irradiance (X-axis); trend line fitted for expected behavior | Real-time / Daily               | Visual diagnostic tool for identifying mismatch, shading, or degradation; supports soiling and fault analytics.      |

---

✅ **Notes:**

* All “power-based” KPIs (Reactive, Active, Transmission Loss) are typically **derived from SCADA / inverter / energy meter data**.
* Performance degradation and curve analyses rely on **historical trend data** for accurate benchmarking.
* Power curve and active power vs irradiance charts are usually **visual diagnostics** in UI dashboards, not standalone numeric KPIs.

---

Would you like me to continue with **efficiency- and yield-based KPIs** next (like Specific Yield, CUF, PR by string, and Energy Loss Segregation)?
