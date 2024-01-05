![ReadMe header](images/readme_header.png)
# Building a Predictive Model of COVID-19 Vaccinations

## Background
Vaccinating a large percentage of the community is an essential portion of the response to the COVID-19 pandemic. 
Three years from the vaccine roll-out, we  now have a more complete picture of the disparity in vaccination rates among certain populations. One area of concern is the effect of partisan alignment on vaccination hesitance, especially in an increasingly polarized political sphere. The extensive discourse regarding medical misinformation and demographic-specific institutional distrust highlights a crucial area of research: what determines the likelihood of vaccination? 

Examples of media covering this topic:
- (Kaiser Family Foundation: The Red-Blue Divide in COVID-19 Vaccination Rates Update)[https://www.kff.org/policy-watch/the-red-blue-divide-in-covid-19-vaccination-rates-continues-an-update/]
- (NPR: There's A Stark Red-Blue Divide When It Comes To States' Vaccination Rates)[https://www.npr.org/2021/06/09/1004430257/theres-a-stark-red-blue-divide-when-it-comes-to-states-vaccination-rates]

## Research Question
While we are inspired by and will pay particular attention to party-specific differences in vaccination rates, we have gathered data on a multitude of factors that might affect vaccination rates, in order to build a more robust model. 
Our research question is this: What factors best predict the rate of vaccination on a county-by-county level? 
The stakeholders here are numerous: the federal government wants to direct its efforts to the appropriate counties; local governments want to make sure they have necessary resources; businesses want to ensure healthy employees and customers; the public benefits from lower rates of disease and mortality.

## Data Understanding
We began with six datasets total, all providing data at the county-level. These datasets are provided below and in our data folder. 
Our target variable is the latest (as of May 2023) available cumulative data on completed primary series vaccinations by county, from the CDC. 
Our **six** predictors are county-level demographic data: 2020 Presidential election results from a github repository; race and age from the Census; poverty, median household income, and educational attainment from the USDA Economic Research Service. 
- [CDC: COVID-19 Vaccinations by County](https://data.cdc.gov/Vaccinations/COVID-19-Vaccinations-in-the-United-States-County/8xkx-amqh/about_data) (468.8MB)
- [Census Datasets](https://www.census.gov/data/tables/time-series/demo/popest/2020s-counties-detail.html)
- [USDA Datasets](https://www.ers.usda.gov/data-products/county-level-data-sets/)
- [County-Level Election Results](https://github.com/tonmcg/US_County_Level_Election_Results_08-20)
- [MIT Election Lab](https://electionlab.mit.edu/data)
  - [County Presidential Election Returns, 2000-2020](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VOQCHQ)

## Data Preparation
We compiled our six datasets into one cleaned dataset (again provided in our data folder) containing 3,113 rows -- one for almost every county in the US. We dropped data from Alaska because it administers its presidential elections by districts. These were drawn differently from its counties, so the mismatch between the datasets resulted in significant missing information across the board. We also dropped data from Puerto Rico, Guam, and the Virgin Islands, because no data was available for them in our predictors datasets.
We prepped our variables of interest in the following ways:
- Target (Vaccinations): We created a binary column where a county was assigned 1 if they had achieved a 70% primary series vaccination rate. This 70% threshold is based on Johns Hopkins University's estimate of the percentage of the population that would need to be vaccinated in order to achieve herd immunity.
- 

## Modelling

why we chose this metric!! importance of false posives

## Results

## Impact
Public health efforts need to be informed by accurate data on heterogenous vaccination results so that providers can shape outreach to maximize positive outcomes. 



## Next Steps


## Repo Structure
```
├── data
│   ├── cleaned_data.csv
│   ├── COVID-19_Vaccinations_in_the_United_States_Jurisdiction_20240103
│   ├── cc-est2022-agesex-all.csv
│   ├── Provisional_COVID-19_Deaths_by_County__and_Race_and_Hispanic_Origin_20240102.csv
│   ├── Education.xlsx
│   ├── PovertyEstimates.xlsx
│   ├── COVID-19_Vaccinations_by_County.csv
│   ├── 2020_US_County_Level_Presidential_Results.csv
├── Images
│   ├── readme_header.png
│   ├── pair_plot.png
├── Notebooks
│   ├── data_cleaning_scratch.ipynb
│   ├── modelling_scratch.ipynb
│   ├── nate_models_scratch.ipynb
│   ├── __pycache__
│   ├── nate_scratch.ipynb
│   ├── shelley_scratch.ipynb
├── presentation.pdf
├── .gitignore
├── Final.ipynb
├── LICENSE
├── README.md
```
