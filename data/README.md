# Data 

This folder contains various data sets used during the lectures and workshops.

## Files

-   `ames_houses.csv`: Simplified Ames housing data with 2,930 observations,
    18 predictors, and the sale price. The houses were sold in Ames, Iowa, from
    January 2006 through July 2010. Prices are nominal USD, without a price-index
    adjustment. The original data contain about 80 explanatory variables.

    See [https://jse.amstat.org/v19n3/decock/DataDocumentation.txt](https://jse.amstat.org/v19n3/decock/DataDocumentation.txt)
    for detailed documentation of the original data set.

    *Variables:*

    1. `LotArea`: Lot size in square meters
    2. `Neighborhood`: Physical locations within Ames city limits
    3. `OverallQuality`: Rates the overall material and finish of the house
        (1 = very poor, 10 = excellent)
    4. `OverallCondition`: Rates the overall condition of the house
        (1 = very poor, 10 = excellent)
    5. `ExteriorQuality`: Quality of exterior materials, stored as ordered string
        labels: `Poor`, `Fair`, `Average`, `Good`, and `Excellent`. The observed
        data contain all these labels except `Poor`.
    6. `YearBuilt`: Original construction date
    7. `YearRemodeled`: Remodel date (same as construction date if no remodeling or additions)
    8. `BuildingType`: Type of dwelling
    9. `CentralAir`: Central air conditioning (string, Y/N)
    10. `LivingArea`: Above grade (ground) living area in square meters; excludes
        all basement space
    11. `BasementArea`: Total basement area in square meters, including finished
        and unfinished space; converted from the original `Total Bsmt SF`
    12. `FinishedBasementArea`: Finished basement area in square meters; the sum
        of the original `BsmtFin SF 1` and `BsmtFin SF 2`, which record areas with
        different types of finish
    13. `Bathrooms`: Full bathrooms above grade
    14. `Bedrooms`: Bedrooms above grade (does not include basement bedrooms)
    15. `Fireplaces`: Number of fireplaces
    16. `SalePrice`: Sale price in thousands of nominal USD
    17. `YearSold`: Year sold
    18. `MonthSold`: Month sold
    19. `HasGarage`: Flag whether property has a garage

    All area variables are rounded to one decimal place. Zero basement area
    denotes no corresponding basement space. One observation has missing values
    for `BasementArea` and `FinishedBasementArea`.

-   `ames_houses_synthetic.csv`: Synthetic prices for the lecture 1 examples,
    calibrated to the observed Ames data. It contains `SalePrice`, `LivingArea`,
    `LotArea`, `YearBuilt`, and `BuildingType`. Prices are in thousands of USD,
    and areas are in square meters. The sample includes complete observations
    with living area at most 300 m² and lot area at most 2,500 m².
