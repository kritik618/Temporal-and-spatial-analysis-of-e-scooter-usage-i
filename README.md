# 🛴 E-Scooter Usage Analysis in Charlotte, NC (January 2024)

## 📍 Overview

This project presents a detailed **temporal** and **spatial** analysis of e-scooter usage in Charlotte, NC, using data from **January 2024**. The goal is to understand how trip behaviors vary across **weekdays vs weekends**, between providers (**Bird** and **Lime**), and across geographic space — especially in relation to public transportation infrastructure like the **LYNX Blue Line** and **bus stops**.

---

## 📅 Dataset Details

- **Source**: Public e-scooter trip data (January 1–31, 2024)
- **Key Fields**: `start_time`, `end_time`, `distance_miles`, `duration_min`, `avg_speed_mph`, `provider`, `coordinates`
- **Coverage**: Charlotte, North Carolina

> ⚠️ Note: Dataset not included in this repo due to privacy. All notebooks assume preloaded data in structured CSV or GeoJSON format.

---

## 🔁 Project Scope

This project is divided into 3 main components:

### 1. Temporal Analysis
- Analyzes hourly trip volume and average duration/speed
- Separate views for **weekdays** and **weekends**
- Comparison between providers: **Bird vs Lime**
- Highlights peak usage times:
  - **Weekdays**: 5 PM peak (commuting), smaller morning bump (7–8 AM)
  - **Weekends**: Peak around 3–4 PM (recreational use)

### 2. Spatial Analysis
- Used **GeoPandas** and **KDE (Kernel Density Estimation)** to visualize hotspots
- Overlayed trip data with:
  - LYNX Blue Line Route (GeoJSON)
  - LYNX Stations
  - Bus Stops
- Key Findings:
  - Weekday usage is **highly concentrated around the Blue Line and stations**
  - Weekend usage is **more scattered**, suggesting recreational rides

### 3. Distance-Based Trip Classification
- Trips are grouped into 4 **distance-based classes** (e.g., <0.3 mi, 0.7 mi, 1.3 mi, >3 mi)
- Separate analysis done for:
  - **Saturday, Jan 13, 2024** (weekend behavior)
  - **Wednesday, Jan 10, 2024** (weekday behavior)
- Visualized each class over city maps with route overlays

---

## 🧪 Sample Insights

### 🔸 Weekday vs Weekend

| Provider | Avg. Distance (mi) | Avg. Duration (min) | Avg. Speed (mph) |
|----------|--------------------|----------------------|------------------|
| Bird (Weekday) | 0.80 | 9.35 | 6.39 |
| Bird (Weekend) | 0.92 | 16.00 | 4.98 |
| Lime (Weekday) | 0.82 | 8.14 | 7.10 |
| Lime (Weekend) | 0.81 | 10.43 | 5.49 |

- **Bird** trips are longer and slower on weekends (leisure rides)
- **Lime** trips are faster overall, especially on weekdays

---

### 🔸 Trip Classification Example (Saturday)

| Class | Count | Avg. Distance | Avg. Duration | Avg. Speed |
|-------|-------|----------------|----------------|-------------|
| 0     | 685   | 0.23 mi        | 6.18 min       | 2.28 mph    |
| 1     | 637   | 0.74 mi        | 8.94 min       | 4.94 mph    |
| 2     | 357   | 1.36 mi        | 15.67 min      | 5.22 mph    |
| 3     | 164   | 3.08 mi        | 37.05 min      | 4.99 mph    |

---

## 🗺️ Tools & Libraries Used

- **pandas**, **numpy** – Data manipulation
- **matplotlib**, **seaborn** – Charts and plots
- **geopandas**, **shapely** – Spatial analysis and maps
- **scikit-learn** – Trip classification
- **KDE (Kernel Density Estimation)** – Heatmap generation
- **GeoJSON** – Transit system overlays (LYNX Blue Line & bus stops)

---

## 📂 Project Structure
notebooks/ ├── temporal_analysis.ipynb ├── spatial_analysis.ipynb 

