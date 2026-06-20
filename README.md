# HealthStat: New York State Elective Hip Replacement Analytics

## 📋 Project Overview
HealthStat is an advanced Power BI dashboard designed to analyze and benchmark **Elective Hip Replacement Surgical Inpatient Stays** across New York State. The project focuses on optimizing healthcare delivery by evaluating two critical hospital performance metrics: **Length of Stay (LOS)** and **Average Cost Per Discharge**. 

By establishing statewide baselines, this dashboard allows hospital administrators and healthcare analysts to identify cost outliers, efficiency bottlenecks, and the core drivers behind extended inpatient stays.

---

## 🚀 Key Features & Layout

The interactive report consists of 4 core views designed for seamless navigation:

### 1. Home Page
![Home Page](Visuals/Home_Page.png)
* Minimalist, professional landing page featuring an intuitive navigation bar to guide users across different analysis modules.

### 2. LOS Comparison
![LOS Comparison](Visuals/LOS_Comparison.png)
* Evaluates efficiency across **151 hospitals** and **627 surgeons**.
* Employs the **Key Influencers AI visual** to reveal what factors (such as a 'Major' or 'Extreme' risk of mortality) drive up patient length of stay.
* Tracks the top 15 hospitals by discharge volume alongside their corresponding average LOS.

### 3. Cost Comparison
![Cost Comparison](Visuals/Cost_Comparison.png)
* Dissects the **$21K statewide average cost per discharge** across **26K total discharges**.
* Features a scatter plot analysis comparing *Average LOS vs. Average Cost per Discharge* to isolate high-cost, low-efficiency regional facilities.
* Highlights the top and bottom performing hospitals based on cost variance against the state baseline.

### 4. Hospital Profile
![Hospital Profile](Visuals/Hospital_Profile.png)
* A granular, single-facility deep dive (e.g., University Hospital) utilizing dynamic Gauge charts.
* Compares the specific hospital's performance directly against the **Statewide Average (ALL)** for both cost and LOS.
* Categorizes clinical profiles by severity of illness, risk of mortality, primary diagnosis descriptions, and post-discharge patient disposition.

---

## 🛠️ Data Modeling & DAX Measures

To create dynamic benchmarks that adapt to user filtering while preserving global state averages, advanced DAX logic was implemented.

### Core DAX Measures Included:

* **Statewide Benchmarking (Ignoring Filters):**
```dax
  Average Cost per Discharge ALL = 
  CALCULATE(
      [Average Cost per Discharge],
      ALL()
  )
