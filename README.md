# Satellite-Based Analysis of Water Surface Dynamics
## Ria de Aveiro Lagoon, Portugal · 2017–2024

**Portfolio Project** · Master's Application Environmental Engineering  

---

## Overview

This project investigates changes in the open water surface area of the 
Ria de Aveiro coastal lagoon using freely available Sentinel-2 satellite 
imagery processed through Google Earth Engine.

**Key findings:**
- Mean lagoon water surface: **5,395 ha** (2017–2024)
- Net change 2017→2024: **+1,027 ha** (R²=0.06, not statistically significant)
- Spatial change detection: **+338 ha** net new water surface
- 2018 drought anomaly: **+605 ha** above mean

---

## Repository Structure
```
├── Aveiro_Lagoon_Analysis.ipynb              # Full analysis notebook
├── README.md                                 # Project documentation
├── Ria_De_Aveiro_Paper.pdf                   # Written portfolio report
├── aveiro_lagune_plot.png                    # Water surface time series chart
├── change_map_2017_2024.png                  # Spatial change detection map
└── aveiro_water_surface_area_2017_2024.csv   # Annual water surface data
```

---

## Methodology

| Step | Tool | Detail |
|------|------|--------|
| Data source | Sentinel-2 SR Harmonized | June–August, 2017–2024 |
| Cloud masking | SCL pixel mask | Classes 4, 5, 6 retained |
| Water index | NDWI (B3–B8) | Threshold: −0.1445 (Otsu) |
| Validation | JRC Global Surface Water v1.4 | Seasonality ≥ 9 months |
| Ocean masking | JRC occurrence ≥ 99% | Excludes Atlantic pixels |
| Platform | Google Earth Engine | Python · geemap · pandas |

---

## Key Outputs

### Water Surface Time Series (2017–2024)
![Time Series](figures/water_surface_timeseries.png)

### Spatial Change Detection 2017 → 2024
*Cyan = new water · Red = new land · Blue = stable water*
![Change Map](figures/change_map_2017_2024.png)

---

## How to Run

1. Requires a Google Earth Engine account  
   → [Sign up here](https://earthengine.google.com)

2. Install dependencies:
```bash
conda create -n aveiro_lab python=3.10
conda activate aveiro_lab
pip install earthengine-api geemap pandas matplotlib numpy
```

3. Authenticate GEE:
```bash
earthengine authenticate
```

4. Open the notebook:
```bash
jupyter notebook Aveiro_Analytics.ipynb
```

> **Note:** Replace `'aveiro-coastal-research'` in Cell 1 with your  
> own GEE project ID.

---

## References

Key references – full list in the PDF report.

- Gorelick et al. (2017). Google Earth Engine. *Remote Sensing of Environment*
- Pekel et al. (2016). Global Surface Water. *Nature*, 540, 418–422
- Xu (2006). NDWI. *International Journal of Remote Sensing*, 27(14)
- Otsu (1979). Threshold selection. *IEEE Trans. Systems*, 9(1)

---

## Author

**Tim Cichon** · Berlin, 2026  
Portfolio project for M.Sc. Environmental Engineering application
