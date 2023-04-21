# CA COVID-19 Forecasting Accuracy
Repository that contains code for evaluation of California county level COVID-19 forecasts for the manuscript: "Assessing the accuracy of California county level COVID-19 hospitalization forecasts to inform public policy decision making" *BMC Public Health*

Pre-print: https://www.medrxiv.org/content/10.1101/2022.11.08.22282086v1

## Code Workflow

1) `CA-baseline.Rmd` creates "baseline" CA model based on prior 7-day rolling average projected forward over 28 days

2) `Generate_score_cards.Rmd`- Code to generate tournament ranking cards that are used for pairwise ranking in `Pairwise_ranking.Rmd`

3) `Pairwise_ranking.Rmd`- Conducts pairwise ranking tournament using "score card" results from `Generate_score_cards.Rmd`

4) `County_ranking_analysis.Rmd` - Creates figures comparing MAE and standardized rank scores across different forecast horizons and periods of variant predominance (Fig 2); Random forest analysis


## Results

* `baseline.csv` and `calcathosp_baseline.csv`- produced via `CA-baseline.Rmd` to create baseline models for comparison to other forecast predictions

* `score_cards_2021Jan1_2022Feb1_allMAE_baseline.csv`- "score card" generated via `Generate_score_cards.Rmd` used for plotting figures in `Pairwise_ranking.Rmd` and `County_ranking_analysis.Rmd`

## Data

* `CalCAT_hosp_forecasts.csv` - archived CalCAT model forecasts for the period of Jan 1. 2021- February 1, 2022; also available from https://calcat.covid19.ca.gov/cacovidmodels/

* `CAregions.csv`- data frame for mapping CA counties to public health officer regions, also includes county population size

* `cnty_reff.csv`- CA county R-effective estimates; available from https://calcat.covid19.ca.gov/cacovidmodels/

* `counties.geojson`- geojson containing spatial plotting information including county FIPS

* `COVID_hospital_census.csv`- COVID-19 hospital census at the county level for CA also available from the CA Open Data Portal: https://data.ca.gov/dataset/covid-19-hospital-data1/resource/8f989799-b959-46ca-b3c5-0e67e95b584e

* `hosp_capacity`- county level non-surge hospital capacity for CA

* `region_variants_summary.csv` - summary of variant prevalence by region for CA; fractions are based on calculating the proportion for each WHO SARS-CoV-2 variant category ("Alpha", "Gamma", "Delta", "Omicron", or "Other") of the total of specimens collected and successfully sequenced in the preceding 7 days for each given day.

* `state_reff.csv` - summary of state R-effective estimates; also available from https://calcat.covid19.ca.gov/cacovidmodels/

* COVID-19 vaccination coverage- pulled from the CA Open Data Portal: https://data.ca.gov/dataset/covid-19-vaccine-progress-dashboard-data/resource/eef88868-0cfc-4655-8a5a-3d1af1d23498


### CA county data sets from USDA Economic Research Service (https://www.ers.usda.gov/data-products/county-level-data-sets/)

* `EducationReport.xlsx`- Education (2015-2019): 2015-2019 5-yr average percentage completing college (university degree); 2013 Rural-urban Continuum code

* `PovertyReport.xlsx` - Poverty (2019): All people in poverty (2019) %

* `UnemploymentReport.xlsx` - Unemployment(annual average 2020 unemployment and 2019 median income latest): Unemployment rate (%) from 2019; Median Household Income



