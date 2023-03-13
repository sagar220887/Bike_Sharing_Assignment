# Project Name
> Bike Sharing Assignment : To build a Linear Regression model for predicting the demand of shared bikes and derive the importatnt factors affecting them


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)



## General Information
- A bike sharing system, in which the bikes are avialble to user on a rental basis. User shall pay and unlock the bike. Bikes are returned to the designated docking system. This company suffred low in revenue to the pandamic situation. The organisaion wants to find the factors so that the business can be accelaearted..

### Objective
- We want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:
Which variables are significant in predicting the demand for shared bikes.
How well those variables describe the bike demands


- We need to build a Linear Regression model on the provided data set, to predict the variables or the factors being a vital parameter for decision making.

### Acceptance Criteria

- You are required to model the demand for shared bikes with the available independent variables.
It will be used by the management to understand how exactly the demands vary with different features.
They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations.
Further, the model will be a good way for management to understand the demand dynamics of a new market.


- The data is provided in the csv file format. It contains data for 2 years 2018 and 2019
Each row represent the total number of bikes rented for a particular day



## Technologies Used
    - numpy 1.23.5
    - pandas 1.5.2
    - seaborn 0.12.1
    - matplotlib 3.6.2
    - sklearn 1.2.1
    - statsmodel 0.13.5


## Conclusions
- Insights post Data Cleaning
    - No null values present in any columns
    - Header and Footer rows are fine
    - There are no rows with all null values
    - All Columns have column header
    - Dropped the column dteday, as date information can be fetched from existing columns mnth and yr
    - Dropped the column instant as it is kind of rudundant - storing only the sequence and will not contribute anything in the analysis
    - As the target field is cnt, we require to analyse the total count ,the columns casual and registered nay not be significant in this case and can create multi-collinearity
    - Categorical column values for season, mnth, weekday and weathersit are replaced with business values
- Insight on Univariate Analysis
    - Numerical Column insights
        1. Increase in demand of bikes are seen for temperature between 10-15 degree celsius and around 25-30 degree celsius
        2. During the days where humidity is within the range of 50-75 there are more bike demands
        3. Usage of rental bikes increases from the windspeed 5-15, however there is a decrease in demand post 15.
    - Categorical columns insights
        1. The fall season observed to have a higher demand of rental bikes
        2. Clearly the year 2019 have more usage of bikes as compared to year 2018
        3. For the months may to oct the demand of bikes are more as compared to other months
        4. Bookings are more for a non-holiday as compared to holiday
        5. Equal demand can be seen for all the days of the week
        6. Books are nearly eqaual for a working and a non-working day
    - Outliers
        1. Few outliers are observed for casuals, windspeed and humidity
        2. We cannot drop the rows with outliers as the data set is too small ans removing rows might impact the analysis
- Insight on Bivariate Analysis
    - For season type "fall" the rental count has been increased
    - Year 2019 has more demands of rental bikes
    - Demand increased from the month jan to jun and then we can see a fall of demands
    - A working daya has more demand than that of an holiday
    - A clear weather has the highest demand
- Insights on Co-rrelation variables in the data set
    - cnt has a positive correlation with yr, temp, atemp
    - Spring season for month Feb and Jan seems to have high positive correlation
    - Summer season for May has high correlation
    - Winter season of Oct and Nov have positive correlation
    - Mist and Humidy have positive correlation of value - 0.48
    - High Correlation exists between temp and atemp
- MODEL building
    - Model A : Taking all the features into consideration
        - R-square value is around 0.853, which is quite a good value
        - However few of the VIF values are marked as infinite, i.e., a strong multicollinearity exits
        - Surely this model can be optimised by reducing the features
    - Model B : Taking  16 variables and bilding model
        - Model 9 showed good results
        - Model 9 stats
            - F-statistic value of 271.9
            - All p values for all the predictors are 0 showing that all fields are significant
            - F-statistic probability is also nearly equal to 0
            - r-square value is 0.830
            - adjusted r-square value is 0.827
    - Model C: Taking 8 variables
        - The model has a low r-sqaure value as compared to MODEL- 8 under MODEL-B
        - The MSE value is quite higher
        - The error terms follow some kind of pattern 
    - Final Insights
        - Model 9 is selected from MODEL-B as it has a good r-square value
        - All the feature VIF values are well within 5
        - p value of all the features are nearly 0 , all fields are significant
        - MSE is calculated 0.009840
        - Driving Features for this model - 
            - temp
            - windspeed
            - yr
            - summer
            - winter
            - Mist
            - sep
            - Light_snow
            - holiday
        - Performed the Predictions on test set and the r-square value comes nearly close.
        - Residual analysis is done, the error terms are normally distributed
        - Multicollinearity between the features does not exists
        - Model 8 is evaluated and the regression plot shows a linear relationship with y_pred and y_test

        - As the temperaturte increses the demand of bikes also increases
        - For windspeed in the range 5-15 the demand increases, however it decreases beyond the point of 15
        - Variables - Holiday, Windspeed, Light_snow and Mist have an negative impact on the demands
        - On the other hand temperature, season have a positive relationship
        - Every year the demand of the bikes are increasing


## Contact
Created by Sagar Sahoo


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->