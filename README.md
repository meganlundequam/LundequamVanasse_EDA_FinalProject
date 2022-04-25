# LundequamVanasse_EDA_FinalProject

This repository is designed to hold all raw data, processed data, and analyses for our Final Project in EDA.

# <Energy Distribution in NC Final Project Respository>

The following sections act as a guide for navigating this repository. Please reach out to Sam, Casey or Megan with questions!

## Summary

This repository contains all of the raw and processed data used to conduct our analyses, the wrangling code we applied to refine the data to answer specific questions, the exploratory code we ran to visualize and understand the data and relationships, and the final project file which explains our research question and how we conducted an analysis with the purpose of shedding light on that research question. 

The goals of our analysis were to examine relationships between energy generation data and demographic data in the state of North Carolina to evaluate observable correlations.

## Investigators

Megan Lundequam
megan.lundequam@duke.edu
Casey Slaught
casey.slaught@duke.edu
Sam Vanasse
samuel.vanasse@duke.edu

## Keywords

environmental justice, North Carolina, fossil fuels, renewable energy, marginalized community, energy distribution, distributional impacts, energy portfolio

## Database Information

Energy Information System
R Internal Census Data

## Folder structure, file formats, and naming conventions

The folders contained in this repository include:

### Code
Contains all of the code used for different stages of our analysis.

  - Data Wrangling Casey 
    - pull census data and create the processed data set "NC_county_2020_complete.geojson" which contains the desired demographic variables used for analyses.
    - wrangle and write the sf data set "generatorsFuelType.geojson" which we used for mapping
    - wrangle the above datasets into a single data set, "generatorsCensus2020.geojson"
  - Data Wrangling Megan
    - create the data set "longlat_generators_NC.csv" which contains geographic data pulled from raw data file "2___Plant_Y2020_ready.csv" and variables of interest from raw data file "3_1_Generator_Y2020.csv"
    - wrangle generatorsCensus2020.geojson into "generatorsCensusCategoriesComplete" which contains information on fuel type and whether the fuel is renewable or a fossil fuel
    - create the processed dataset "NCGenerator&Income" which contains added demographic data (income) and original generator data
  - Data Wrangling Sam
    - create "UpdatedCensus.csv" with dropped geometry
    - create "FFEnergyDataNCcounties.csv", "RenewableEnergyDataNCcounties.csv", and "EnergyDataNCcounties.csv" by combining old and new census data and generator data and then splitting into 3 different data sets for statistical analysis
    - run statistical regressions and analysis
  - Data Exploration Megan
    - create plots to display the breakdown of number of generators ("RvFPlot_Gen") and energy capacity ("RvFPlot_Cap") of generators to show difference

### Data
- Raw
Contains the raw data imported from EIS which contains data on energy generators in NC.
- Processed
Contains all of our processed data sets used for different stages of analysis.

### Output
Contains images of two of our plots.

### Project
Contains project instruction files.


## Metadata

Data Set: EnergyDataNCcounties.csv
| Column Name           | Description                                        | Data Class | Units |
|-----------------------|----------------------------------------------------|:----------:|:-----:|
|County                 |County of Plant and demographic data                |Factor      |N/A    |
|Renewable.v.FossilFuel |Energy category of generator                        |Factor      |N/A    |
|energy.type.gen        |Total Nameplate Capacity of generators by category  |Number      |MW     |
|MedianHouseholdIncome  |Median household income of county                   |Integer     |N/A    |
|TotalPopulation        |Total population in county                          |Integer     |N/A    |
|Per.CollegeDeg         |Percent with a college degree                       |Number      |N/A    |
|Per.PovertyMobility    |Percent at or below poverty line                    |Number      |N/A    |
|Per.MinorityMobility   |Percent minority                                    |Number      |N/A    |
|Per.NoSchooling        |Percent with no schooling                           |Number      |N/A    |
|total.gen              |Total Nameplate Capacity of generators in county    |Number      |N/A    |

Data Set: FFEnergyDataNCcounties.csv
| Column Name           | Description                                        | Data Class | Units |
|-----------------------|----------------------------------------------------|:----------:|:-----:|
|County                 |County of Plant and demographic data                |Factor      |N/A    |
|Renewable.v.FossilFuel |All Fossil Fuel                                     |Factor      |N/A    |
|energy.type.gen        |Total Nameplate Capacity of generators by category  |Number      |MW
|MedianHouseholdIncome  |Median household income of county                   |Integer     |N/A    |
|TotalPopulation        |Total population in county                          |Integer     |N/A    |
|Per.CollegeDeg         |Percent with a college degree                       |Number      |N/A    |
|Per.PovertyMobility    |Percent at or below poverty line                    |Number      |N/A    |
|Per.MinorityMobility   |Percent minority                                    |Number      |N/A    |
|Per.NoSchooling        |Percent with no schooling                           |Number      |N/A    |
|total.gen              |Total Nameplate Capacity of generators in county    |Number      |N/A    |

Data Set: generators.geojson (sf of longlat_generators_NC)
| Column Name                 | Description                                        | Data Class | Units |
|-----------------------------|----------------------------------------------------|:----------:|:-----:|
|Utility.ID.x                 |EIA-assigned ID for company                         |Integer     |N/A    |
|Utility.Name.x               |Legal name of the company                           |Factor      |N/A    |
|Plant.Code                   |EIA-assigned plant code                             |Integer     |N/A    |
|Plant.Name.x                 |Plant Name                                          |Factor      |N/A    |
|State.x                      |Plant State                                         |Factor      |N/A    |
|County.x                     |Plant County                                        |Factor      |N/A    |
|Technology                   |Technology used by generator to produce electricity |Factor      |N/A    |
|Energy.Source.1              |Code representing energy that fuels generator       |Factor      |N/A    |
|Utility.ID.y                 |EIA-assigned ID for company                         |Integer     |N/A    |
|Utility.Name.y               |Legal name of the company                           |Factor      |N/A    |
|Plant.Name.y                 |Plant Name                                          |Factor      |N/A    |
|City                         |Plant City                                          |Factor      |N/A    |
|State.y                      |Plant State                                         |Factor      |N/A    |
|County.y                     |Plant County                                        |Factor      |N/A    |
|Primary.Purpose..NAICS.Code. |NAICS code - describes purpose of plant             |Integer     |N/A    |
|geometry                     |The coordinates of the plant's location             |'XY' Number |N/A    |

Data Set: generatorsCensus2020.geojson
| Column Name                 | Description                                        | Data Class | Units |
|-----------------------------|----------------------------------------------------|:----------:|:-----:|
|Utility.ID                   |EIA-assigned ID for company                         |Integer     |N/A    |
|Utility.Name                 |Legal name of the company                           |Character   |N/A    |
|Plant.Code                   |EIA-assigned plant code                             |Integer     |N/A    |
|Plant.Name                   |Plant Name                                          |Character   |N/A    |
|County.Short                 |Plant County                                        |Character   |N/A    |
|Technology                   |Technology used by generator to produce electricity |Character   |N/A    |
|Energy.Source.1              |Code representing energy that fuels generator       |Character   |N/A    |
|City                         |Plant City                                          |Character   |N/A    |
|Primary.Purpose..NAICS.Code. |NAICS code - describes purpose of plant             |Integer     |N/A    |
|FuelType                     |Fuel type based on code from Energy.Source.1        |Character   |N/A    |
|GEOID                        |Zip Code                                            |Character   |N/A    |
|NAME                         |County, State                                       |Character   |N/A    |
|County                       |Plant County                                        |Character   |N/A    |
|State                        |Plant State                                         |Character   |N/A    |
|MedianHouseholdIncome        |Median household income of county                   |Number      |N/A    |
|Year                         |EIA-assigned ID for company                         |Number      |N/A    |
|geometry                     |The coordinates of the plant's location             |sfc_POINT   |N/A    |

Data Set: generatorsCensusCategoriesComplete.csv
| Column Name                 | Description                                        | Data Class | Units |
|-----------------------------|----------------------------------------------------|:----------:|:-----:|
|Utility.ID                   |EIA-assigned ID for company                         |Integer     |N/A    |
|Utility.Name                 |Legal name of the company                           |Factor      |N/A    |
|Plant.Code                   |EIA-assigned plant code                             |Integer     |N/A    |
|Plant.Name                   |Plant Name                                          |Factor      |N/A    |
|County.Short                 |Plant County                                        |Factor      |N/A    |
|Technology                   |Technology used by generator to produce electricity |Factor      |N/A    |
|Energy.Source.1              |Code representing energy that fuels generator       |Factor      |N/A    |
|City                         |Plant City                                          |Factor      |N/A    |
|Primary.Purpose..NAICS.Code. |NAICS code - describes purpose of plant             |Integer     |N/A    |
|FuelType                     |Fuel type based on code from Energy.Source.1        |Factor      |N/A    |
|GEOID                        |Zip Code                                            |Integer     |N/A    |
|NAME                         |County, State                                       |Factor      |N/A    |
|County                       |Plant County                                        |Factor      |N/A    |
|State                        |Plant State                                         |Factor      |N/A    |
|MedianHouseholdIncome        |Median household income of county                   |Integer     |N/A    |
|Year                         |EIA-assigned ID for company                         |Integer     |N/A    |
|FuelType                     |Fuel type based on code from Energy.Source.1        |Factor      |N/A    |
|Renewable.v.FossilFuel       |Energy category of generator                        |Factor      |N/A    |

Data Set: longlat_generators_NC.csv
| Column Name                 | Description                                        | Data Class | Units |
|-----------------------------|----------------------------------------------------|:----------:|:-----:|
|Utility.ID.x                 |EIA-assigned ID for company                         |Character   |N/A    |
|Utility.Name.x               |Legal name of the company                           |Character   |N/A    |
|Plant.Code                   |EIA-assigned plant code                             |Integer     |N/A    |
|Plant.Name.x                 |Plant Name                                          |Character   |N/A    |
|State.x                      |Plant State                                         |Character   |N/A    |
|County.x                     |Plant County                                        |Character   |N/A    |
|Technology                   |Technology used by generator to produce electricity |Character   |N/A    |
|Energy.Source.1              |Code representing energy that fuels generator       |Character   |N/A    |
|Utility.ID.y                 |EIA-assigned ID for company                         |Integer     |N/A    |
|Utility.Name.y               |Legal name of the company                           |Character   |N/A    |
|Plant.Name.y                 |Plant Name                                          |Character   |N/A    |
|City                         |Plant City                                          |Character   |N/A    |
|State.y                      |Plant State                                         |Character   |N/A    |
|County.y                     |Plant County                                        |Character   |N/A    |
|Latitude                     |The latitude of a plant's coordinates               |Number      |N/A    |
|Longitude                    |The longitude of a plant's coordinates              |Number      |N/A    |
|Primary.Purpose..NAICS.Code. |NAICS code - describes purpose of plant             |Integer     |N/A    |

Data Set: NC_CountyComplete.geojson
| Column Name           | Description                                        | Data Class | Units |
|-----------------------|----------------------------------------------------|:----------:|:-----:|
|GEOID                  |Zip Code                                            |Character   |N/A    |
|NAME                   |County, State                                       |Character   |N/A    |
|County                 |Plant County                                        |Character   |N/A    |
|County.Short           |Plant County                                        |Character   |N/A    |
|State                  |Plant State                                         |Character   |N/A    |
|MedianFamilyIncome     |Median household income of county                   |Number      |N/A    |
|Year                   |EIA-assigned ID for company                         |Number      |N/A    |
|TotalPopulation        |Total population in county                          |Number      |N/A    |
|Per.NoSchooling        |Population  with no schooling                       |Number      |N/A    |
|Mobility               |Population at or below poverty line                 |Number      |N/A    |
|Mobility2              |Minority Population                                 |Number      |N/A    |
|RaceAllocation         |Minority Population                                 |Number      |N/A    |
|DetiledRace            |Minority Population                                 |Number      |N/A    |
|geometry               |The coordinates of the plant's location             |sfc_MULTIPOLYGON|N/A|

Data Set: NCGenerator&Income.csv
| Column Name                 | Description                                        | Data Class | Units |
|-----------------------------|----------------------------------------------------|:----------:|:-----:|
|Utility.ID                   |EIA-assigned ID for company                         |Integer     |N/A    |
|Utility.Name                 |Legal name of the company                           |Factor      |N/A    |
|Plant.Code                   |EIA-assigned plant code                             |Integer     |N/A    |
|Plant.Name                   |Plant Name                                          |Factor      |N/A    |
|County.Short                 |Plant County                                        |Factor      |N/A    |
|Technology                   |Technology used by generator to produce electricity |Factor      |N/A    |
|Energy.Source.1              |Code representing energy that fuels generator       |Factor      |N/A    |
|City                         |Plant City                                          |Factor      |N/A    |
|Primary.Purpose..NAICS.Code. |NAICS code - describes purpose of plant             |Integer     |N/A    |
|FuelType                     |Fuel type based on code from Energy.Source.1        |Factor      |N/A    |
|GEOID                        |Zip Code                                            |Integer     |N/A    |
|NAME                         |County, State                                       |Factor      |N/A    |
|County                       |Plant County                                        |Factor      |N/A    |
|State                        |Plant State                                         |Factor      |N/A    |
|MedianHouseholdIncome        |Median household income of county                   |Integer     |N/A    |
|Year                         |EIA-assigned ID for company                         |Integer     |N/A    |
|FuelType                     |Fuel type based on code from Energy.Source.1        |Factor      |N/A    |
|Renewable.v.FossilFuel       |Energy category of generator                        |Factor      |N/A    |
|Nameplate.Capacity           |Nameplate Capacity of generator                     |Factor      |N/A    |
|Nameplate.Capacity1          |Nameplate Capacity of generator                     |Number      |MW     |

Data Set: NPCapByFuelType.csv
| Column Name                 | Description                                        | Data Class | Units |
|-----------------------------|----------------------------------------------------|:----------:|:-----:|
|County                       |Plant County                                        |Factor      |N/A    |
|Renewable.v.FossilFuel       |Energy category of generator                        |Factor      |N/A    |
|FuelType                     |Fuel type based on code from Energy.Source.1        |Factor      |N/A    |
|total.np.cap                 |Total Nameplate Capacity of generators in category  |Number      |MW    |

Data Set: RenewableEnergyDataNCcounties.csv
| Column Name           | Description                                        | Data Class | Units |
|-----------------------|----------------------------------------------------|:----------:|:-----:|
|County                 |County of Plant and demographic data                |Factor      |N/A    |
|Renewable.v.FossilFuel |All Renewable                                       |Factor      |N/A    |
|energy.type.gen        |Total Nameplate Capacity of generators by category  |Number      |MW
|MedianHouseholdIncome  |Median household income of county                   |Integer     |N/A    |
|TotalPopulation        |Total population in county                          |Integer     |N/A    |
|Per.CollegeDeg         |Percent with a college degree                       |Number      |N/A    |
|Per.PovertyMobility    |Percent at or below poverty line                    |Number      |N/A    |
|Per.MinorityMobility   |Percent minority                                    |Number      |N/A    |
|Per.NoSchooling        |Percent with no schooling                           |Number      |N/A    |
|total.gen              |Total Nameplate Capacity of generators in county    |Number      |N/A    |

## Scripts and code

See wrangling files.

## Quality assurance/quality control

<describe any relevant QA/QC procedures taken with your data. Some ideas can be found here:>
<https://www.dataone.org/best-practices/develop-quality-assurance-and-quality-control-plan>
<https://www.dataone.org/best-practices/ensure-basic-quality-control>
<https://www.dataone.org/best-practices/communicate-data-quality>
<https://www.dataone.org/best-practices/identify-outliers>
<https://www.dataone.org/best-practices/identify-values-are-estimated>
