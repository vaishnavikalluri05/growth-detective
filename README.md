# Growth Detective: US, Brazil and Ghana

Project 1 for MS Applied Economics, University of Cincinnati.
Author: Vaishnavi Kalluri

This project compares economic growth across three countries at different
stages of development (United States, Brazil, Ghana), looks at how US growth
changed over time, and explores what drives growth across OECD countries.

## Project structure

All code is in one R script, `proj_1_kalluri.R`, organized in steps:

| Step | What it does | Assignment part |
|------|--------------|-----------------|
| 1 | Downloads and loads Penn World Table 11.0 | Part 1 |
| 2 | Keeps the US, Brazil and Ghana and selected variables | Part 1 |
| 3 | Checks for and handles missing values | Part 1 |
| 4 | Calculates GDP per capita and annual growth rates | Part 2 |
| 5 | Graphs GDP per capita and growth rates | Part 2 |
| 6 | Compares investment, population growth and human capital by era | Part 2 |
| 7 | Splits US growth into three periods (pre-1990, 1990-2007, 2008-2023) | Part 3 |
| 8 | Builds 1991-2023 averages for all 38 OECD countries + correlation matrix | Part 4 |
| 9 | Scatterplots and correlation heatmap for OECD countries | Part 4 |

## Data source

Penn World Table 11.0 (Feenstra, Inklaar and Timmer, 2015), covering 185
countries from 1950 to 2023. https://www.rug.nl/ggdc/productivity/pwt/

The data file is **not** included in this repository. The script downloads
it automatically from the official source the first time it runs.

Variables used:
- `rgdpna`: real GDP at constant national prices (used for growth rates)
- `rgdpe`: real GDP at chained PPPs (used for comparing income levels)
- `pop`: population
- `hc`: human capital index
- `csh_i`: investment share of GDP

## Preprocessing

- Ghana has no data for 1950-1954, before its independence in 1957. Because
  the gap is at the start of the series, interpolation was not possible, so
  these years were dropped. Ghana's analysis covers 1955-2023.
- The US and Brazil have complete data for 1950-2023.
- For the OECD analysis, the period is 1990-2023 because six members
  (Czechia, Slovakia, Estonia, Latvia, Lithuania, Slovenia) have no data
  before 1990. All 38 countries have complete data over this period.

## How to replicate

1. Install R and RStudio.
2. Install the required packages by running this once in the R console:
   `install.packages(c("haven", "dplyr", "ggplot2", "tidyr", "scales"))`
3. Download `proj_1_kalluri.R` and open it in RStudio.
4. Set the working directory to the script's folder:
   Session > Set Working Directory > To Source File Location
5. Run the whole script (Source button). It will download the data,
   print all tables, and save the graphs as PNG files in the same folder.
