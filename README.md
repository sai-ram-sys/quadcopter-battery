# 🚁 Quadcopter Battery Pack Design & Optimization

> **CIA 3 – Project Report | Drone Technologies & Transformative Applications**  
> Batch 2024–25 | LNT Construction Internal Submission

---

## 📋 Project Overview

This project delivers a complete engineering design and optimization of a **LiPo battery pack** for a standard **F450-class hobby quadcopter**. It covers cell-level design, series/parallel configuration analysis, thermal management, trade-off evaluation, and Python-based simulation with visualizations.

| Detail | Value |
|---|---|
| **Project Title** | Quadcopter-Specific Battery Pack Design and Optimization |
| **Subject** | Drone Technologies & Transformative Applications |
| **Submission** | CIA 3 – Group Project |
| **Batch** | 2024–25 |
| **Platform** | F450 Quadcopter Frame (450mm diagonal) |

---

## 👥 Team Members

| S.No. | Name | Register Number | Contribution |
|---|---|---|---|
| 1 | Member 1 – [Name] | REG/001 | Voltage design, Series/Parallel config, System requirements |
| 2 | Member 2 – [Name] | REG/002 | Capacity calculations, Flight endurance analysis |
| 3 | Member 3 – [Name] | REG/003 | Thermal management, Safety protocols, BMS design |
| 4 | Member 4 – [Name] | REG/004 | Trade-off analysis, Chemistry comparison |
| 5 | Member 5 – [Name] | REG/005 | Simulation code, Documentation, BOM |

---

## 🎯 Project Objectives

- **A.** Design a battery pack based on required capacity (mAh), voltage (V), and discharge rate (C-rating)
- **B.** Evaluate trade-offs between weight, efficiency, and flight duration
- **C.** Document the final design and prepare for Viva Voce

---

## ✅ Final Design: 3S2P LiPo Battery Pack

| Parameter | Specification |
|---|---|
| Configuration | **3S2P** (3 Series × 2 Parallel) |
| Cell Chemistry | Lithium Polymer (LiPo) |
| Cell Spec | 3.7V / 5,000 mAh / 35C |
| Total Cells | 6 |
| Pack Voltage | **11.1V** nominal / 12.6V max |
| Pack Capacity | **10,000 mAh (10 Ah)** |
| Stored Energy | **111 Wh** |
| Max Continuous Current | 350A (35C × 10Ah) |
| Pack Weight | ~320g |
| Main Connector | XT90 |
| Practical Flight Time | **11–17 minutes** |

---

## 🗂️ Repository Structure

```
quadcopter-battery/
│
├── battery_simulation.py              # ← Main Python simulation source code
├── README.md                          # ← This file
│
├── Quadcopter_Battery_Pack_Design_CIA3.docx   # ← Full project report
├── Screenshots_Consolidated_LMS.pdf           # ← LMS submission PDF
│
└── charts/
    ├── chart1_discharge_curve.png     # LiPo discharge & power delivery curves
    ├── chart2_tradeoff.png            # Configuration trade-off analysis
    ├── chart3_thermal.png             # Thermal analysis & voltage sag
    ├── chart4_pack_diagram.png        # 3S2P cell arrangement diagram
    └── chart5_chemistry.png          # Chemistry comparison charts
```

---

## 🐍 Running the Simulation

### Prerequisites

```bash
pip install matplotlib numpy
```

### Run

```bash
python battery_simulation.py
```

### Output

The script will:
1. Print a full design summary to the terminal
2. Generate 5 charts saved to `./charts/`

**Sample terminal output:**
```
============================================================
  QUADCOPTER BATTERY PACK — DESIGN SUMMARY
============================================================
  config                   : 3S2P
  total_cells              : 6
  voltage_nominal          : 11.1
  voltage_max              : 12.6
  capacity_mah             : 10000
  stored_energy_wh         : 111.0
  max_cont_current         : 350.0
  weight_pack_g            : 316

------------------------------------------------------------
  FLIGHT TIME ESTIMATES (80% usable capacity)
------------------------------------------------------------
  Hover only  (35A)  : 13.71 min
  Cruise      (50A)  : 9.6 min
  Aggressive  (70A)  : 6.86 min
============================================================
```

---

## 📊 Simulation Charts

### Chart 1 – Discharge Curve
Models open-circuit and loaded voltage vs. discharged capacity for hover, cruise, and aggressive throttle scenarios.

### Chart 2 – Configuration Trade-Off
Compares 3S1P / 3S2P / 3S3P / 3S4P / 4S2P packs on flight time, pack weight, and stored energy.

### Chart 3 – Thermal Analysis
Shows cell temperature rise over 20-minute flights at different throttle levels, and voltage sag vs. current at different temperatures.

### Chart 4 – Pack Diagram
Visual layout of the 3S2P cell arrangement showing series (orange) and parallel (green) connections with terminal positions.

### Chart 5 – Chemistry Comparison
Bar chart of specific energy (Wh/kg) and radar chart comparing LiPo, Li-Ion, and LiFePO4 across 6 criteria.

---

## 🔑 Key Engineering Formulas

**Voltage (Series):**
```
V_pack = N_series × V_cell = 3 × 3.7V = 11.1V
```

**Capacity Required:**
```
C = I_avg × t_hours × 1000 = 35A × 0.25h × 1000 = 8,750 mAh (+20% margin → 10,000 mAh)
```

**C-Rating Check:**
```
C_min = I_burst / C_Ah = 80A / 10Ah = 8C  →  Selected: 35C (4.4× safety margin)
```

**Flight Time:**
```
T = (C_Ah × 0.80) / I_avg × 60 minutes
```

**Voltage Under Load (Sag):**
```
V_load = V_nominal - (I × R_internal)
```

---

## ⚠️ Safety Guidelines

- Never discharge below **3.5V/cell** (use a voltage alarm)
- Always charge at **1C rate** (10A for this pack) with a balance charger
- Store at **3.85V/cell** if unused for > 24 hours
- Maximum operating temperature: **60°C**
- Use **LiPo-safe charging bags** during all charging and storage
- Use **XT90 anti-spark connectors** to prevent inrush current damage

---

## 📚 References

1. Tattu Battery Technical Specifications – https://www.gensace.de
2. Emax MT2213 Motor Datasheet – https://www.emaxmodel.com
3. Andrea, D. – *Battery Management Systems for Large Lithium Ion Battery Packs* – Artech House, 2010
4. Mahony, R. et al. – *Multirotor Aerial Vehicles* – IEEE Robotics & Automation Magazine, 2012
5. FAA – *UAS Battery Safety* – Advisory Circular, 2022

---

## 📄 License

This project is submitted for academic evaluation under CIA 3 guidelines.  
Open access as required per submission instructions.

---

*Drone Technologies & Transformative Applications | CIA 3 | Batch 2024–25*
