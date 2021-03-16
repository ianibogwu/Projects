# PROJECT 2: AMES,IA HOUSING DATA PROJECT

## Problem Statement:
With a population of about 67,000 people and the 7th most populated city in Iowa, Ames is quickly becoming home to lots of individuals and familes alike. That being said, many sellers are looking to take advantage of the market and sell their homes while demand is high.

Our realty firm, Coco Realty has decided to host a seller's seminar to show homeowners, how much their properties can sell for in this market. Using information from the county assesors office, I will attempt build a model that can predict the price of homes in the Ames, IA area.

- I will be exploring a few regression models such as Linear, Lasso and Ridge models for predicting sales price.
- In addition to this, I will make note of features that can be improved in the home to increase its sale price.
- After evaluating these three models, I will select which model works the best in giving the best predictions of home prices in Ames, IA.

# Data Dictionary:

A copy of the data dictonary used in this project can be found at the link below. This will give insight as to what each column and their values mean

http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

# Next up: Data Cleaning, EDA and Modeling!

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
