## Phase 2 Project Description

### Business Case - ARCH

ARCH is a partnership of King County and East King County cities working to preserve and increase the supply of housing for low and moderate income households in the region. ARCH wants to expand their knowledge of the housing conditions that contribute to the sale price of a home, particularly homes priced below the median price range in King County to better serve their clients in that area.

#### This project has two primary goals:

    Develop an algorithm that predicts the sale price of a home given certain features such as square footage, condition of the home, zip code, size of lot, number of bedrooms and bathrooms, and other salient features.

    ARCH also wants to better understand how these features interact and influence the home sale price so that they can better advise their clients when searching for homes at or below the median price.

### Data 

    The dataset contains over 21,000 records of home sales in the King County area of Washington State. These homes were sold in the years 2014 and 2015 with the bulk of the sales in 2015. The data contains the home price and associated features including square footage, number of bedrooms, number of bathrooms, floors, size of the lot, zipcode location, grade of the home, and condition of the home. Many of the features are numeric and several features, such as condition of the home, are categorical features. Condition of the home include values such as "Poor" or "Very Good". 
    
    There are some significant outliers in the upper range of the home price. To minimize some of the more extreme outliers the dataset was winnowed down to within 2 standard deviations on either side of the mean. Two standard deviations above and below the mean capture 95% of the data. 
    
### Data Modeling Workflow Process

    The goal of the data modeling process is to go beyond data analysis to include statistical modeling:
    
    1. Examine the data and engage in exploratory data analysis to identify broad trends and patterns. 
    2. Clean and ready the data for Predictive modeling
    3. Build a baseline model using the most correlated feature.
    4. Build an initial and final predictive model using scikit learn
    5. Evaluate the model and apply it to the test data. Provide analysis. 
    6. Build an inferential model for further insight using statsmodel.




### Key Metrics, Limitations and Conclusions

1. The median price of a home is 440,000 USD. There are some significant home price outliers that skew the mean into the higher range of 485,000 USD

2. The baseline predictive model shows that the square footage of the home, the most correlated home feature, explains just over 40% of the variance in home price. This means that the larger the home, the higher the price. But that is only part of the explanation.

3. The final predictive model, which includes several features such as grade of home, the year the home was built, and zipcode, show that these features when added to the baseline model account for over 83% of the variance of a home's price. Zipcode in particular accounts for over 10% of the variation. 

4. Two important coefficents that emerge that help explain the model are the square living space footage and the year the home was built:

    Square footage = 103
    Year Built = -610

    This means that for every one square foot increase we can expect an increase in 103 USD on the home price.
    For the Year Built we have a negative number meaning that as the year increases, say from 1990 to 1991, the home price goes       down by 610 USD. This suggests that newer homes cost less overall. 

5. One important metric is the mean absolute error of 65,274. This error implies that the final model could be off by upwards of $65,000 when predicting home price. This could be a substantial amount given that the median home price is 440,000 USD. That error amount could be the difference in whether a moderate or low income family or individual can afford to purchase a home or not. This suggests that more work needs to be done to understand home price. Because zipcode accounts for more than 10% of the variance conducting an analysis on geographic distribution of home prices could be fruitful in pinpointing areas to look for moderately priced homes, or to identify areas to push for affordable housing developments.

6. Interestingly there is not a great difference in price effect when it comes to condition, whether the home is in fair, average, good, or very good condition. If the house is in poor condition, however, home sale price is depressed more markedly. The build grade of the home from poor towards luxury does have a positive correlation. As grade improves home price increases as well, particularly as we move from 'good' to 'better' grade values. 




### Recommendations


    1. Search for homes sizes under 1700 square feet or less. This will likely keep the home price under the median.

This was calculated by taking the sqft_living variance of 40% multiplied by the home price median of 440,000 and divided by 103 USD/per square foot (the coefficient generated by the predictive model.

        (.40 x 440,000 USD)/103 = 1708.73 square feet

    2. Newer homes tend to cost less, they bring the home price down year over year by about 610 USD. Look for newer homes being built across zipcodes and further explore why they may cost less. Build quality is important in driving up costs, homes built with lower grade quality cost less. They may have less square footage and be in higher density areas across zipcodes or further away from amenities and work locations making them less desirable and therefore less costly.

    3. Zipcodes play an important role in housing price - up to 10% variance. It would be helpful to do more zipcode analysis and break those areas down further into smaller parcels such as census tracts for more fine grained detail. It's possible that within the same zipcode there may be higher priced areas but with moderate or lower priced homes in the mix. Look for zipcodes that have a wider range of home price values.

### Navigating the repository

-Data (includes description of column names)
-Images (includes data visualizations)
-Student (jupyter notebook dsiplaying the worked code)
-kc_house_data.csv (king county housing data)
-LICENSE.MD
-README.MD




