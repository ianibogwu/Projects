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

# Data Cleaning:
For the training set, we have 2051 rows of data and 81 columns, including our target variable, SalePrice.
I first checked for null values in the data set to know how much "missing data" we are working with. Now, missing is subjective as a null value doesn't always indicate missing data. For example, a home without a fence can be recorded as 'N/A' but it is a data point as it indicates the home does not have a fence.

Total null values are below:

![Null_Values](../01-Ames-housing/photos/null_values.png)

Knowing these values, I went ahead and featured engineered some of the variables in the null table and other variables in the dataset to make them more useful for analysis. Note: This is only a sample of features engineered not the full list

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

#### Correlation of dependent variables to SalePrice
![correlation](../01-Ames-housing/photos/Saleprice_correlation)

These show how all the independent variables correlate with the dependent. **Overall Quality** takes the number one spot with a correlation of 80 percent . The better a home's overall quality is, the higher the sale price and vice versa, holding all other factors constant.

#### Dwelling Type (MS Subclass)

![Mssubclass](../01-Ames-housing/photos/Mssubclass)

As listed in the county files, an MS Sub class identifies the dwelling type of the home. An MS Sub Class of 75 means that the house is a 2 1/2 story structure. This would mean that the most expenisve homes in Ames, IA tend to be the 2 1/2 story houses, signifying that the town is oriented more towards families.

#### Neighborhoods

![neighborhood](../01-Ames-housing/photos/neighborhood)
The most expensive neighborhood by Saleprice is *StoneBr*. On average, houses in this neighborhood sell for just above $350,000.

#### Garage Finishing

![Garage Finish](../01-Ames-housing/photos/garage_finish)

- A fully finished garage interior (3.0) in the Ames, IA area garners a sales price of about \\$250,000 on average; A \\$40,000 increase compared to a roughly finished garage (2.0)

#### Overall Quality

![Overall Quality](../01-Ames-housing/photos/overall_qual)

- There is a very linear relationship between overall quality and sale price. The better the material and finish of the house, the higher the selling price. Thus can be a point to make to sellers looking to sell their homes for top dollar








# Overall Findings:

So all three models seemed to score between a range of 90-93% between the training and testing data. I did notice that my linear and lasso models made it difficult to see which variables are strongly correlated with price

However with my Ridge Model, I can clearly see which variable is affecting price and can give recommendations as well! So Ridge is the model we will stick with.

# Recommendations!

So after our findings we can now recommed a few things that our elderly patients can do to increase the value of their home

In our EDA, square footage happened to be one of the biggest drivers of price. Looking at our Ridge model coefficients, we can see this proves to be true.

Lot Area, Gross Living Area, 1st and 2nd floor and total basement square footage carry added average value of over $10,000 in value.

Now it's completely understandable if our clients would be reluctant to accept this recommendation because it's not an easy thing to just add additional square footage!

So what other options do we have?

Improving Overall condition and quality and exterior quality

-Keeping the overal condition and quality and exterior quality of your home can add value as well! Approximately, $7,000 to be exact! So just keeping the house in overall good condition and the quality of material that is used in the house in good shape is key!

Misc Features

Adding some miscellaneous features such as a Shed or a garage can add up up to $800 on average
Garage

Add another car garage or adding some square footage to your current garage area can add a value between  2000− 4000
Paved Driveway

Having a paved driveway can add up to $500 dollars in value as well
Porch

A screen porch, which can be added towards the rear of your home, can add up to $3000 in value!
Fence Minimum Privacy

Adding just a little fence privacy can increase the value
Kitchen quality

-Kepping your kitchen in 'Excellent' shape also carries about a $5000 increase in value of your home

Roof Matl_CompShg

Compound shingle roofs adds an additional $2095 in value
Neighborhoods

StoneBr, Nridght, NoRidge, Somertst are among some of the neighborhoods have the highest value. So if you're home falls within those areas, an additional $2-3k in value can be added to your home.

# Summary:


#Directory
├── Ames\ Housing\ Data\ Project.pdf
├── Cleaning_EDA.ipynb
├── Modeling_final.ipynb
├── ReadME.md
├── datasets
│   ├── lasso_results.csv
│   ├── test.csv
│   └── train.csv
├── modeling_notebook.ipynb
└── project_2-EDA.ipynb
