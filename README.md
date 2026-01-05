# InfoVisProjectGroup6

# NL Tourism Dashboard (2015–2020)

[![Preview of the NL tourism dashboard](./preview.png)](./preview.png)

Interactive D3.js visualization of tourism in the Netherlands (2015–2020).  
Use the year slider to switch datasets, hover provinces to drill down, and compare national vs. provincial patterns. 

The page renders three coordinated views for the selected year:

1. **Choropleth map (provinces)**
   - Provinces are colored by **total guests** (property: `All`).
   - Hover a province to update all charts + the “Area / Total Guests” labels.

2. **Accommodation types (vertical bar chart)**
   - National default: guest totals by accommodation type.
   - On province hover: switches to that province’s accommodation breakdown.

3. **Visitor origins (horizontal bar chart)**
   - National default: guest totals by country/region of origin (sorted descending).
   - On province hover: switches to that province’s origin breakdown (sorted descending).

4. **Monthly guests (vertical bar chart)**
   - National default: foreign guests per month.
   - On province hover: switches to monthly values for that province.

## Features

- **Year slider** (default: **2019**) triggers a full redraw:
  - Removes existing SVG(s)
  - Loads `nldataset<YEAR>.json`
  - Rebuilds map + charts with the new year’s data
- **Province hover**
  - Tooltip with province name
  - Updates all charts + labels dynamically
- **Legend**
  - Color gradient legend for province guest totals

## Data

### Geo/topo data
Each year is stored as:

- `nldataset2015.json`
- `nldataset2016.json`
- `nldataset2017.json`
- `nldataset2018.json`
- `nldataset2019.json`
- `nldataset2020.json`

These files contain:
- A **TopoJSON** object (`nl.objects.provinces`)
- Per-province tourism properties (e.g., `All`, `Germany`, `Hotelboardinghouseyouthhostel`, `Jan`, `Feb`, ...)

### National totals
National (“Netherlands as a whole”) totals are embedded in `index.js` as a JSON string (`country_data`) 

## Acknowledgements
The team consists of Katriel Ester Amanda(@katrielester), Runnan Fu (@runnanfu), and Jing Zhou(@jiczhou). Also, many thanks to the work done by @adboy316, we have learned a lot from his project and are inspired by it.
