# King County House Price Modeling 2015
## Summary and Recommendations
Data from King County, WA house sales from May 2014 to May 2015 was obtained. A multi-variate linear regression model were fit for each zipcode to obtain the best model.

![](./images/Price.PNG)

After analyzing the data from the various resources, the following conclusions and recommendations are made:
1. Expand above ground square
footage.
2. Improve condition.
3. Improve grade.

## Repository Files Organization
- presentation.pdf: the presentation slides for non-technical presentation.
- main.ipynb: the main Jupyter Notebook containing the data exploration and analysis.
- raw_data: folder containing the movie raw data.
- images: folder containing images used for README.md

## Data
**Data Columns:**
- id - unique identified for a house
- dateDate - house was sold
- pricePrice - is prediction target
- bedroomsNumber - of Bedrooms/House
- bathroomsNumber - of bathrooms/bedrooms
- sqft_livingsquare - footage of the home
- sqft_lotsquare - footage of the lot
- floorsTotal - floors (levels) in house
- waterfront - House which has a view to a waterfront
- view - Has been viewed
- condition - How good the condition is ( Overall )
- grade - overall grade given to the housing unit, based on King County grading system
- sqft_above - square footage of house apart from basement
- sqft_basement - square footage of the basement
- yr_built - Built Year
- yr_renovated - Year when house was renovated
- zipcode - zip
- lat - Latitude coordinate
- long - Longitude coordinate
- sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors
- sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors

**Vocab: Condition:**

Relative to age and grade. Coded 1-5.

1 = Poor- Worn out. Repair and overhaul needed on painted surfaces, roofing, plumbing, heating and numerous functional inadequacies. Excessive deferred maintenance and abuse, limited value-in-use, approaching abandonment or major reconstruction; reuse or change in occupancy is imminent. Effective age is near the end of the scale regardless of the actual chronological age.

2 = Fair- Badly worn. Much repair needed. Many items need refinishing or overhauling, deferred maintenance obvious, inadequate building utility and systems all shortening the life expectancy and increasing the effective age.

3 = Average- Some evidence of deferred maintenance and normal obsolescence with age in that a few minor repairs are needed, along with some refinishing. All major components still functional and contributing toward an extended life expectancy. Effective age and utility is standard for like properties of its class and usage.

4 = Good- No obvious maintenance required but neither is everything new. Appearance and utility are above the standard and the overall effective age will be lower than the typical property.

5= Very Good- All items well maintained, many having been overhauled and repaired as they have shown signs of wear, increasing the life expectancy and lowering the effective age with little deterioration or obsolescence evident with a high degree of utility.

**Vocab: Grade:**

Represents the construction quality of improvements. Grades run from grade 1 to 13. Generally defined as:

1-3 Falls short of minimum building standards. Normally cabin or inferior structure.

4 Generally older, low quality construction. Does not meet code.

5 Low construction costs and workmanship. Small, simple design.

6 Lowest grade currently meeting building code. Low quality materials and simple designs.

7 Average grade of construction and design. Commonly seen in plats and older sub-divisions.

8 Just above average in construction and design. Usually better materials in both the exterior and interior finish work.

9 Better architectural design with extra interior and exterior design and quality.

10 Homes of this quality generally have high quality features. Finish work is better and more design quality is seen in the floor plans. Generally have a larger square footage.

11 Custom design and higher quality finish work with added amenities of solid woods, bathroom fixtures and more luxurious options.

12 Custom design and excellent builders. All materials are of the highest quality and all conveniences are present.

13 Generally custom designed and built. Mansion level. Large amount of highest quality cabinet work, wood trim, marble, entry ways etc.

## Model Fit
Target:
- Price

Features:
- bedrooms
- bathrooms
- waterfront
- view 
- condition
- sqft_above
- sqft_basement
- sqft_lot,
- age (as of 2015)

The model fits pretty well considering coefficients of determination for each zipcode (note that some zipcodes are combined in the data, hence same color across someborders):
![](./images/R2.PNG)

The regression coefficients:
![](./images/Coeff1.PNG)

The waterfront coefficient is very large in comparison to the others. Here's one without waterfront:
![](./images/Coeff2.PNG)

The following features increase house sales value:
- Bathrooms
- Waterfront
- Condition
- Grade
- Square footage
The following features decrease house sales value:
- Bedrooms
- Floors
- Age

## Recommendations
- Expand above ground square
footage.
- Improve condition.
- Improve grade.

## Combined House Prices and Regression Coefficient of Determination Plot
This plot shows visually around how many data points, and water the prices are like in each zipcode and its model's coefficient of determination.

Note that some zipcodes are combined in the data, hence same color across someborders.
![](./images/Both.PNG)

## Future Work
1. Create a continuously updated model
2. Add neighborhood to features
3. Add sale type to features, i.e. foreclosure, sale by owner, sale by agent.
4. Add house type to features, i.e. co-op, condo, single family home, multi-family hole, HOA, etc.