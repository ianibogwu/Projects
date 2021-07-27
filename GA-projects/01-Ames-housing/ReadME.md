# AMES,IA HOUSING DATA PROJECT

## Problem Statement:
With a population of about 67,000 people and the 7th most populated city in Iowa, Ames is quickly becoming home to lots of individuals and families alike. That being said, many sellers are looking to take advantage of the market and sell their homes while demand is high.

Our realty firm, Coco Realty has decided to host a seller's seminar to show homeowners, how much their properties can sell for in this market. Using information from the county assessors office, I will attempt build a model that can predict the price of homes in the Ames, IA area.

- I will be exploring a few regression models such as Linear, Lasso and Ridge models for predicting sales price.
- After evaluating these three models, I will select which model works the best in giving the best predictions of home prices in Ames, IA.
- In addition to this, I will make note of features that can be improved in the home to increase its sale price.

# Data Dictionary:

A copy of the data dictionary used in this project can be found at the link below. This will give insight as to what each column and their values mean. This also includes an explanation of feature engineered variables

http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

| Feature | Description |   
| :---    |   :----:    |
| PID     | Parcel Identification number|
| MS SUB CLASS| 020	1-STORY 1946 & NEWER ALL STYLES|
                030	1-STORY 1945 & OLDER
                040	1-STORY W/FINISHED ATTIC ALL AGES
                045	1-1/2 STORY - UNFINISHED ALL AGES
                050	1-1/2 STORY FINISHED ALL AGES
                060	2-STORY 1946 & NEWER
                070	2-STORY 1945 & OLDER
                075	2-1/2 STORY ALL AGES
                080	SPLIT OR MULTI-LEVEL
                085	SPLIT FOYER
                090	DUPLEX - ALL STYLES AND AGES
                120	1-STORY PUD (Planned Unit Development) - 1946 & NEWER
                150	1-1/2 STORY PUD - ALL AGES
                160	2-STORY PUD - 1946 & NEWER
                180	PUD - MULTILEVEL - INCL SPLIT LEV/FOYER
                190	2 FAMILY CONVERSION - ALL STYLES AND AGES


# Data Cleaning:
For the training set, we have 2051 rows of data and 81 columns, including our target variable, SalePrice.
I first checked for null values in the data set to know how much "missing data" we are working with. Now, missing is subjective as a null value doesn't always indicate missing data. For example, a home without a fence can be recorded as 'N/A' but it is a data point as it indicates the home does not have a fence.

Total null values are below:

![Null_Values](../01-Ames-housing/photos/null_values.png)

Knowing these values, I went ahead and featured engineered some of the variables in the null table and other variables in the dataset to make them more useful for analysis.
**Note**: This is only a sample of features engineered not the full list

![featured engineered variables](../01-Ames-housing/photos/feat_eng_var.png)

I also normalized the dependent variable(**SalePrice**) by using a log function which allows our data to closely resemble a normal distribution. This allows for more accurate calculation as the models being used make the assumption that the data is already normalized.

Here's a before and after:

![Original Sale Price](../01-Ames-housing/photos/Saleprice_original.png)

![Log Sale Price](../01-Ames-housing/photos/Log_Saleprice.png)

**Hetroskadacity transformed to homoskedacity**:

Now that our dependent variable has been normalized, we see a transformation from hetroskedacity to homoskedacity. This means our errors or residuals(difference between our true and predicted values) now have a constant value rather than fluctuating values with every increase in the independent variable. Here's what it looks like now using one of the independent variables *Gross living Area*

![residuals](../01-Ames-housing/photos/residuals.png)

# Exploratory Data Analysis:
Here I will be describing some of the findings of our data.

#### Correlation of dependent variables to SalePrice:

![correlation](../01-Ames-housing/photos/Saleprice_correlation.png)

- Correlations tell us how closely related the values we put in (independent variables) affect the outcome we are trying to figure out (dependent variables).
- For this particular problem, we are trying tp figure out how the features of a home, including the neighborhood it's in affect how much it will sell for.
- These show how all the independent variables correlate with the dependent. **Overall Quality** takes the number one spot with a correlation of 80 percent . The better a home's overall quality is, the higher the sale price and vice versa, holding all other factors constant.

#### Gross living Area:

![gross living area](../01-Ames-housing/photos/gr_liv_area.png)

- There's a positively linear relationship between gross living area and Sale price. The greater the gross living area, the higher the sale price and vice versa.

#### Dwelling Type (MS Subclass):

![Mssubclass](../01-Ames-housing/photos/Mssubclass.png)

- As listed in the county files, an MS Sub class identifies the dwelling type of the home. An MS Sub Class of 75 means that the house is a 2 1/2 story structure. This would mean that the most expensive homes in Ames, IA tend to be the 2 1/2 story houses, signifying that the town is oriented more towards families.

#### Neighborhoods:

![neighborhood](../01-Ames-housing/photos/neighborhood.png)

- The most expensive neighborhood by Saleprice is *StoneBr*. On average, houses in this neighborhood sell for just above $350,000.

#### Garage Finishing:

![Garage Finish](../01-Ames-housing/photos/garage_finish.png)

- A fully finished garage interior (3.0) in the Ames, IA area garners a sales price of about \\$250,000 on average; A \\$40,000 increase compared to a roughly finished garage (2.0)

#### Overall Quality:

![Overall Quality](../01-Ames-housing/photos/overal_qual.png)

- There is a very linear relationship between overall quality and sale price. The better the material and finish of the house, the higher the selling price. This can be a point to make to sellers looking to sell their homes for top dollar

#### Pool:

![Pool](../01-Ames-housing/photos/pool.png)

- Having a pool significantly increases Sale price. On average, sellers can expect at least \\$42,421 more in Sale price if their home includes a pool, holding all other values constant.


#### Year Remodeled and Year Built:

![year remod](../01-Ames-housing/photos/year_remod.png)

- This visual shows that homes built and or remodeled in later years (especially after 2000) command the highest price in this market.

#### Driveway:

![Driveway](../01-Ames-housing/photos/driveway.png)

- On average, having a fully paved driveway results in. a 68.49% increase in Sale Price from a partial driveway, holding all other factors constant. Another selling point to get clients to fully pave their driveways rather than doing a partial or dirt driveway.

#### Central Air:

![central air](../01-Ames-housing/photos/central_air.png)

- Homes in Ames, IA with central air sell for over $60000 more than homes without one, holding all other values constant. Another selling point for clients. Further analysis will be needed to know the actual value of central air in each neighborhood in Ames, IA.


# Modeling
For this section, I focused on using regression models as finding predictive values of homes is the major goal of this project. The three models I will use in this section are **Linear, Lasso and Ridge regression**.

Something worth noting is that all three models above focus on reducing the errors between the true and predicted values; Their methods however vary.

#### Linear Regression:

- The linear regression model is focused on the least squared objective, that is reducing errors between true and predicted values. For this particular project, the model scored a whopping 94.8% on the training set and 91.5% on the testing set. Since the testing set is the true capability of the model, it is safe to say that according to the Linear model, 91.5% of variance in the Sale price is caused by the independent variables such as (gross living area, overall quality, all 220 independent features).

#### Lasso Regression:

- Lasso follows the same objective as linear regression of reducing errors between the true and predicted values but does so by adding what is called a "penalty". It also has a cool addition called "feature selection" that reduces variables that aren't contributing very much to the model to zero. This allows us to find which variables are really doing the work in adding to the model.

- The lasso model gives us a training score of 94.4% and 92% testing. This means that 92% of the variance in sales price is caused by the independent variables. As mentioned before, feature selection is one of the model's caveat. Here are a list of the top 10 features that affected the model's score the most.


#### Ridge Regression:

- Ridge also follows the same objective as lasso and linear and also using a penalty scale that is decided based on the data we input. The ridge model a 94.8 % in training and 91.7% in testing.


# Model Selection:

All three models had a healthy range in testing scores between 91 - 92%. However in the end, **Lasso model** appeared to have the least variance in its training and testing score by a very slight margin so therefore it is our chosen model.

# Recommendations!

![lasso coefficients](../01-Ames-housing/photos/lasso_coefs.png)

- After our findings we can now recommend a few things that the homeowners in order to increase the value of their homes.
- As shown above, Gross living area, the year built, Basement SF, Garage area and proximity to various conditions (Condition_1 Normal) are all things that affect the price but are outside of a homeowner's control. On the other hand, **'overall quality' and overall condition** are something within the owner's purview. Here are a few more:

 **Driveway**: As mentioned above, homes with a paved drive way saw a 68.49% increase in Sale price compared to driveways that were partially paved. Clients are fully advised to pave their driveways if within their budget.

 **Kitchen Quality**: While the data makes it difficult to classify what is considered 'excellent' when it comes to kitchen quality, it is safe to say that aiming for the excellence (5) standard will draw in far more dollars than any of the other categories. Homes with an 'excellent' rating for the kitchen tend to sell over $100000 higher on average than homes with a good (4) rating.

 ![kitchen Qual](../01-Ames-housing/photos/kitchen_qual.png)

 **Sale Type**: In Ames, IA the market is ruled by buyers who come in with low interest contracts, such as an FHA loan. It would be in the seller's best interest to look out for buyers with this type of financing, as the properties they're interested in tend to sell for higher prices.

 ![Sale Type](../01-Ames-housing/photos/sale_type.png)

# Shortcomings of this project:
- As outlined above, these are a few improvements a home owner can make to increase the likelihood of their homes selling for a higher price. It is important to not that while our model can predict accurately 92% of the time, working with a knowledgable licensed real estate agent is the best way to get the most accurate value of your home as they have first hand information on what a particular market is like.

- For instance, it was previously noted that the best neighborhood or the highest selling neighborhoods were **StoneBr**, **Nridght** , **Noridge , and Grnhill**.  But why were these Neighborhoods the most expensive? We are missing valuable information on what amenities are close to these neighborhoods that can affect the price. Things such as proximity to grocery stores, public parks and schools are just a few of those amenities but not an extensive list.

- Also, the real estate market it self tends to have sub markets even within a particular town. Homes that appeal to a particular buyer may not appeal to another so more specialized knowledge is required to know how different features in a home affect a specific submarket within Ames, IA.


# Conclusion:
- Overall, our firm was able to get a 92% prediction accuracy of home prices in Ames, IA based on the information we were given by the county's assessors office. We would also be thrilled to offer our services for homeowners looking to sell their properties. We have some of the most qualified and leading agents in the industry who are well informed about the Ames,IA market and can further assist in getting an even more accurate price. We look forward to working with you!
