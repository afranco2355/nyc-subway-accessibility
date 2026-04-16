# NYC Subway Accessibility Analysis

An equity-focused analysis of accessibility across the NYC subway system, 
combining MTA station data, elevator reliability records, and Census 
disability population data to understand who is being left behind.

## Project Status
Work in progress. Current version includes station accessibility mapping, 
borough breakdowns, and elevator reliability analysis. Disability population 
equity analysis coming next.

## Project Overview
Only 32% of NYC subway stations are fully ADA accessible, meaning two out 
of every three stations cannot be used by someone in a wheelchair. This 
project goes beyond that headline number to ask harder questions: which 
stations are officially accessible but unreliable in practice? Which 
boroughs are most underserved? And are the neighborhoods with the highest 
concentration of disabled residents also the ones with the fewest accessible 
stations?

This analysis combines three years of MTA open data with Census disability 
statistics to build an interactive map and a series of findings about where 
the system is failing the people who need it most.

## Key Findings

**Two thirds of subway stations are completely inaccessible.** Of 496 subway 
stations, 329 have no elevator access whatsoever — leaving wheelchair users, 
people with strollers, and anyone who cannot use stairs with no option at 
those stops.

**Brooklyn has the worst accessibility record of any borough despite being 
the most populous.** Only 25.4% of Brooklyn stations are fully accessible — 
the lowest rate of any borough — meaning 124 out of 169 stations are 
inaccessible to wheelchair users.

**Manhattan leads accessibility but still falls short of half.** At 40.5% 
accessible, Manhattan has the highest rate of any borough, yet still leaves 
the majority of its 153 stations unreachable for riders who cannot use stairs.

**Some of the city's busiest accessible stations have chronically unreliable 
elevators.** 42 St-Port Authority Bus Terminal, one of the most trafficked 
transit hubs in the city, has an average elevator availability of just 82.3% 
over 10 years — meaning its elevators are out of service roughly one in six 
days. Grand Central-42 St and Atlantic Av-Barclays Ctr also appear among the 
least reliable accessible stations.

**Privately managed elevators are significantly less reliable than MTA-owned 
ones.** The least reliable elevators in the system all carry an X in their 
equipment code, indicating they are maintained by third-party developers 
rather than the MTA. The worst, EL290X, has been operational only 50% of 
the time since 2015.

**Official accessibility status does not always reflect reality on the 
ground.** Several stations marked as fully accessible show zero elevators 
in the MTA equipment inventory, suggesting either street-level access or 
gaps in the data. A station that is technically ADA compliant but whose 
only elevator is broken half the time is not meaningfully accessible to 
the riders who depend on it.

## What the Project Does
This analysis loads and combines four datasets entirely from public URLs 
with no manual downloads required. Every time the notebook is run it 
reflects the most current MTA data available.

The first dataset is the MTA subway stations file, which provides the 
official ADA status, coordinates, and lines served for all 496 stations. 
The second is the MTA elevator and escalator equipment inventory, which 
details every physical elevator and escalator in the system including 
whether each one forms part of a complete accessible pathway. The third 
is the MTA elevator availability dataset covering 2015 to present, which 
provides monthly uptime records for every elevator allowing us to calculate 
long-term reliability scores. The fourth is MTA subway service line 
geometries, which draws the actual subway lines on the map in their 
official colors.

## Coming Next
The next phase of this project will add Census ACS disability population 
data by neighborhood to answer the equity question directly: are the 
neighborhoods with the highest concentration of disabled residents also 
the neighborhoods with the fewest accessible subway stations?

## Data Sources
All data is sourced from the MTA Open Data Program on data.ny.gov and 
NYC Open Data on data.cityofnewyork.us. No API keys are required.

## Tools Used
Python, pandas, geopandas, folium, plotly, and Google Colab.

## How to Run
Open the notebook in Google Colab and run all cells from top to bottom. 
All data loads automatically from public URLs with no files needed.

## Files
`nyc_subway_accessibility.ipynb` contains the full analysis notebook.
`nyc_subway_accessibility_map.html` is the interactive station map — 
download and open in any browser to explore all 496 stations colored 
by accessibility status with subway lines drawn in their official colors.
