# Thermal-Plant-Allocation-Project
Python-based supplier allocation and disruption risk tool for cement supply chains: Geospatial mapping, Haversine distances, and scenario analysis.
Background
Cement production is heavily dependent on thermal power plants as energy suppliers and fly ash suppliers. In the event of a supply disruption — whether due to plant shutdowns, fuel shortages, or logistics failures — production facilities need to quickly identify alternative suppliers and assess the cost and distance implications of reallocation.
This project replicates and extends a supplier risk assessment originally performed in Excel, rebuilding the allocation logic in Python and adding interactive geospatial visualization.

What This Project Does

Loads data on 33 thermal power plants across Turkey, each with geographic coordinates and fuel type (coal, natural gas, liquid fuel)
Calculates distances from each plant to two production facilities using the Haversine formula, which accounts for Earth's curvature and is more accurate than straight-line Euclidean distance
Assigns each plant to its nearest production facility
Visualizes the full supplier network on an interactive map of Turkey using Folium, with color-coding by assigned facility and markers by fuel type


Project Structure
├── data/
│   └── thermal_plants.xlsx        # Source data: plant locations and fuel types
├── notebooks/
│   └── supplier_allocation.ipynb  # Main analysis notebook
├── requirements.txt
└── README.md

Key Methodology
Haversine Distance
Rather than using straight-line distance as in the original Excel model, this project calculates great-circle distance between coordinates — a meaningful improvement for a geographically spread dataset spanning the full width of Turkey.
Proximity-Based Allocation
Each plant is assigned to whichever production facility it is closest to. The allocation logic is fully reproducible and parameterizable, meaning facility locations can be updated without reworking the underlying model.
Fuel Type Classification
Plants are categorized by fuel type (Kömür / Doğalgaz / Sıvı Yakıt) and this is reflected in the map visualization, allowing quick identification of fuel-specific supplier clusters.

Output
An interactive HTML map showing:

All 33 thermal power plants, color-coded by assigned facility
Both production facilities as distinct markers
Fuel type differentiation via marker icons
Distance and allocation details on hover


Planned Features

Disruption scenario analysis: simulate the removal of one production facility and recalculate all plant assignments, quantifying the total distance penalty of reallocation
Capacity-weighted allocation: incorporate plant output volumes into the assignment logic rather than proximity alone
Risk scoring: rank suppliers by criticality based on distance, fuel type, and replaceability


Tools & Libraries

Python 3.x
pandas
folium
openpyxl


Context
This project is based on real supply chain analysis work conducted during an internship in the cement industry. All company-identifying information has been removed. The methodology reflects standard supplier risk assessment practices aligned with international procurement frameworks.
