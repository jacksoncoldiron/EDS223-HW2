# EDS223-HW2: Environmental Justice and Redlining in Los Angeles

## Overview

This project investigates the lasting impacts of historical redlining on present-day environmental justice and biodiversity sampling in Los Angeles. Using historical Home Owners' Loan Corporation (HOLC) grades from the 1930s alongside contemporary environmental and biodiversity data, this analysis examines how past discriminatory lending practices continue to shape current socioeconomic conditions, environmental exposures, and scientific data collection.

## Research Questions

- How do historical HOLC redlining grades correlate with present-day environmental and socioeconomic conditions in Los Angeles?
- Are bird observations from citizen science equally distributed across neighborhoods with different historical HOLC grades?
- What do these patterns reveal about sampling bias in biodiversity data collection?

## Key Findings

**Part 1: Environmental & Socioeconomic Conditions**
- Low-income percentages increase from ~18% in Grade A neighborhoods to ~44% in Grade D neighborhoods
- Life expectancy percentiles rise from ~23 in Grade A areas to ~59 in Grade D areas
- PM2.5 exposure increases from the 68th to 83rd percentile across the HOLC grade gradient
- Strong evidence that redlined neighborhoods continue to face disproportionate environmental and economic burdens

**Part 2: Biodiversity Observations**
- Over 51% of bird observations occur in Grade C neighborhoods
- Grade D neighborhoods account for ~31% of observations
- Grade A neighborhoods represent only ~4% of observations
- Results differ from national trends, suggesting local-scale factors influence citizen science participation patterns

## Data Sources

- **HOLC Redlining Data**: Mapping Inequality project (University of Richmond Digital Scholarship Lab)
  - Source: https://dsl.richmond.edu/panorama/redlining/
  
- **Environmental Justice Data**: EJScreen 2023 (U.S. EPA)
  - Includes census block group-level demographic and environmental variables
  
- **Biodiversity Data**: Global Biodiversity Information Facility (GBIF)
  - Bird observations in Los Angeles, 2021-2023

## Repository Structure

```
EDS223-HW2/
├── README.md
├── HW2.qmd
├── .gitignore
└── data/
    ├── ejscreen/
    │   └── EJSCREEN_2023_BG_StatePct_with_AS_CNMI_GU_VI.gdb
    ├── gbif-birds-LA/
    │   └── gbif-birds-LA.shp
    └── mapping-inequality/
        └── mapping-inequality-los-angeles.json
```

## Methods

1. **Data Preparation**: Validated spatial geometries and transformed all datasets to matching coordinate reference systems (EPSG:4326)

2. **Spatial Joins**: Used `st_join()` with `st_within()` to assign census block groups and bird observations to HOLC grades

3. **Summary Statistics**: Calculated mean values for environmental variables (low income %, PM2.5 percentile, life expectancy percentile) grouped by HOLC grade

4. **Visualization**: Created maps using `tmap` and exploratory visualizations using `ggplot2` to examine patterns across grades

## Key Visualizations

- **Figure 1**: Historical HOLC Redlining Patterns in Los Angeles
- **Figure 2**: Low-Income Percentages by Historical HOLC Grade
- **Figure 3**: Health and Pollution Burdens Across HOLC Grades
- **Figure 4**: Distribution of Bird Observations by HOLC Grade

## Usage

To reproduce this analysis:

1. Clone this repository
2. Ensure you have R and the required packages installed (see `HW2.qmd` for dependencies)
3. Download data from the provided sources and place in the `data/` folder
4. Render the Quarto document: `quarto render HW2.qmd --to pdf`

## Author

Jackson Coldiron  
Bren School of Environmental Science & Management  
UC Santa Barbara

## Academic Context

This analysis was completed for EDS 223 (Geospatial Analysis) at the University of California, Santa Barbara, instructed by Ruth Oliver. The assignment builds on foundational concepts in spatial data analysis, vector operations, and environmental justice research.

## References

Ellis-Soto, D., Chapman, M., & Locke, D. H. (2023). Historical redlining is associated with increasing geographical disparities in bird biodiversity sampling in the United States. *Nature Human Behaviour*, 1-9.

Gee, G. C. (2008). A multilevel analysis of the relationship between institutional and individual racial discrimination and health status. *American Journal of Public Health*, 98(Supplement 1), S48-S56.

Nardone, A., Rudolph, K. E., Morello-Frosch, R., & Casey, J. A. (2021). Redlines and greenspace: the relationship between historical redlining and 2010 greenspace across the United States. *Environmental Health Perspectives*, 129(1), 017006.

Nelson, R. K., Winling, L., Marciano, R., Connolly, N., et al. (2023). *Mapping Inequality*. American Panorama, ed. Robert K. Nelson and Edward L. Ayers. University of Richmond. https://dsl.richmond.edu/panorama/redlining/# EDS223-HW2
Repository containing the work for Homework Assignment #2 for EDS 223: Geospatial Analysis &amp; Remote Sensing.
