# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: AMES Housing Data project


### Overview

 ### Problem Statement:

Ames, IA has seen an increase in population of younger residents. According to the US Census, over 40% of it's residents are between the ages of 18-24 years. While this is a good thing for the city itself, as a population that young can contribute to the work force, buy homes, pay taxes and more; it has it's elderly population feeling left out.

The same Census also puts the elderly population of residents 65 or older in Ames at 8%. With more younger residents coming in and growing, the standard of living is bound to keep increasing. As they grow older in age, they feel marginalized and want to know what options they have.

Most have been considering leaving the state. Take John and Carrie Preston for instance. They've been residents for over 25 years but with the rapid changes, they feel it might be time to relocate to Florida simply because of the access to beaches, abundance of assisted living homes and close family in the area.

 They've called upon us here at Datascience-R-US to give them an idea of how much their home is currently worth. They've invited a few friends as well who are interested in relocating so we will be speaking at the local Elks Club to a few of them.
    
 In this project, we will attempt to give them a prediction of the price of houses in the Ames,Iowa area and what features contribute the most value to the price of a home. This way, they can make an informed decision on which features they can update in their home in order to capitalize off of the market.\n",
 
 ### GOALS:,
 
In this notebook, I am taking you through my steps of how I use the Ames housing data set to predict the price of homes in the Iowa area.
  
We will be exploring a few models in order to reach our goal of predicting price.

We will be looking at: -Linear Regression Models -Lasso Models -Ridge Models

After evaluating these three models, we will compare these models to our baseline score and select which model works the best in acheving our goal."
 
### Data Dictionary:,

A copy of the data dictonary used in this project can be found at the link below. This will give insight as to what each column and their values mean

 http://jse.amstat.org/v19n3/decock/DataDocumentation.txt"
 
### Next up: Data Cleaning, EDA and Modeling!

These steps can all be found in the notebook attached"
  
### Overall Findings:,

So all three models seemed to score between a range of 90-93% between the training and testing data. I did notice that my linear and lasso models made it difficult to see which variables are strongly correlated with price,

However with my Ridge Model, I can clearly see which variable is affecting price and can give recommendations as well! So Ridge is the model we will stick with."

### Recommendations!,

So after our findings we can now recommed a few things that our elderly patients can do to increase the value of their home,

In our EDA, square footage happened to be one of the biggest drivers of price. Looking at our Ridge model coefficients, we can see this proves to be true.

Lot Area, Gross Living Area, 1st and 2nd floor and total basement square footage carry added average value of over $10,000 in value.
    
Now it's completely understandable if our clients would be reluctant to accept this recommendation because it's not an easy thing to just add additional square footage!

So what other options do we have?
   
**Improving Overall condition and quality and exterior quality**
 
Keeping the overal condition and quality and exterior quality of your home can add value as well! Approximately, $7,000 to be exact! So just keeping the house in overall good condition and the quality of material that is used in the house in good shape is key!

**Misc Features**,

Adding some miscellaneous features such as a Shed or a garage can add up up to $800 on average,

**Garage**,

Add another car garage or adding some square footage to your current garage area can add a value between  2000− 4000

**Paved Driveway**

Having a paved driveway can add up to $500 dollars in value as well

**Porch**,

A screen porch, which can be added towards the rear of your home, can add up to $3000 in value!

**Fence Minimum Privacy**

Adding just a little fence privacy can increase the value.

**Kitchen quality**

Kepping your kitchen in 'Excellent' shape also carries about a $5000 increase in value of your home


**Roof Matl_CompShg**
Compound shingle roofs adds an additional $2095 in value

**Neighborhoods**

StoneBr, Nridght, NoRidge, Somertst are among some of the neighborhoods have the highest value. So if you're home falls within those areas, an additional $2-3k in value can be added to your home."

### Summary:

***While these models do provide a baseline as to understanding the Ames, IA real estate market, we cannot accurately use these models as effectively to predict price**

 As seen from our R2 results, the model was very much off on the prices it predicted.
 
This is simply because there's just information that we do not know that hasn't been included in our data. Or we may have too much data even though our Lasso, Linear and Ridge models all performed well on the test data. This was an important lesson in realizing that the scores of the model is not always the best predictor. We should focus more on the MSE or RMSE.

***As a final word of advice, we highly recommend working with local and knowledgeable Realtors in the area. Our model was a good start in obtaining value of certain features in a home, but it is not the end solution***



