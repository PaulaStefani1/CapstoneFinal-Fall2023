# Capstone Project - Fall 2023

Overview: 
This Repository is used in order to track and save the different EDA, modeling and analysis processes, and all documentation performed during the completion of the Maverik Capstone project during the MSBA Capstone  Fall 2023 course.

## Business Problem and Project Objective:

Maverik is a leading convenience and fuel store brand known for providing an excellent customer experience and specialized ‘BonFire’ food. Maverik also strengthens their communities by impacting local hunger, education, and outdoor enrichment. Maverik, founded in 1928, has grown to 8000 employees and 400 locations. Opening 30 stores each year, Maverik faces the unique challenge of forecasting and evaluating first-year sales performance expectations for each new location. Insufficient historical data, complex sales predictors, varying trends, and market fluctuations complicate interpreting and modeling efforts. 

The benefit of the solution is that an accurate forecasting model will enable Maverik to improve financial planning and may provide more accurate initial ROI documentation. A successful model will yield cost-effective predictions that are comparatively accurate to Maverik’s existing predictive models. Specific metrics may include Adjusted R Squared, Root Mean Square Errors (RMSE), or other values determined by Maverik.

Garish Prajapat, Jade Gosar, Karson Eilers, and Paula Stefani will use store-level data provided by Maverik and macroeconomic indicators with precise metrics determined at a later point to develop a time series model to forecast store, food, gasoline, and diesel sales performance metrics for both individual and aggregate time intervals. The scope will meet several time-certain milestones. The team will first perform exploratory data analysis (EDA) by October 1st. The team will then evaluate several analytics approaches; including autoregression, weighted moving averages, vector autoregression (VAR), autoregressive integrated moving averages (ARIMA), neural networks, and simulation to determine which are most appropriate for the given dataset. The team will then develop the model using the R programming language. 

By combining time series forecasting with simulation, the final model’s performance can be validated against simulated data to assess its robustness and allows the team to better understand the uncertainties associated with its forecasts. Due to the complexity of Maverik’s industry, simulation will also help estimate the range of possible future outcomes and behavior of key variables, giving the model the opportunity to capture important interactions occurring within the data. The analysis will be completed by October 29th with the team presenting their findings on November 28th. The final product delivered will be the EDA results (including which factors contribute more to improved store performance) and the R script for the model. Automatic forecasting with new data exceeds this current scope of work, but the team will reevaluate this request as the models are constructed.

## Data & Final Deliverable:

Qualitative data was provided from recent new stores and their first few years of sales. – A network wide seasonality  pattern will was also given. The project consis of 4 main sales metrics: Diesal, Unleaded, Food sales and Inside Sales. Our team is focused providing forecasts for the different sales metrics.The desired outcome is a final deliverable of a model that produces a daily level forecast, considering seasonality for each of the sales metrics, in which the model will update the forecasts as new data comes in for the site, always ensuring the most accurate forecasts. Together with the main final deliverable model, the second most important deliverable for the project is the creaiton of a complete document containing Exploratory EDA analysis for the data provided to our team and a Final Presentaiton Document that communicates the implementaiton and main findings of the models created. 

## Modeling & Approach:
Our modeling approach had different stages and steps to get our team in a place where we felt happy with the overall model performance. Our main goal was to create a final deliverable with  a model that produces accurate forecast, considering seasonality for each of the sales metrics, in which the model would update the forecasts as new data comes in for the site ensuring accuracy. 

### Step 1: Variable Selection Using Linear Regression:
We first brainstormed and researched different possible models strategies like LSTM, Weighed moving averages, linear regressions and more complex time series models like VAR and ARIMA. We initially used more basic linear regression models and Variance Inflation Factor in order to perform variable selection and identify the predictors with better predictive power for each of the sales metrics.

### Step 2: Penalized Regression Using LASSO:
After concluding linear regression for variable selection, we decided to create our first model by using LASSO penalized regression. Our main idea behind this choice was because of how computationally effective LASSO is, and the fact of how LASSO chooses the best predictors variables for each of the sales metrics and reduces the coefficients of the less important predictors. In order to implement that we created a loop in which the sales metrics would be added as a lag from previous historical data into the model as new columns, being used as predictors for the next day forecast. 

### Step 3: Vector Autoregressive (VAR):
After creation of the LASSO model, our team decided together with the Professor’s advising to try to develop a more comprehensive time series model in order to use lag values from previous days for the different sales metrics and being able to increase accuracy and decrease RMSE values. With this in mind, we tried two different time series models that per our research have been shown to be effective in time series forecasting analysis: VAR and ARIMA. We chose Vector Autoregressive because of its capacity of capturing the dynamic interactions and feedback effects among multiple variables. 

### Step 4: ARIMA model:
While building the VAR model, we decided to also create an ARIMA model because of how it accounts for various patterns, such as linear or nonlinear trends, constant or varying volatility, and seasonal or non-seasonal fluctuations. We believed both models could provide us good insights, and ARIMA could be really helpful considering the nature and fluctuations of our data.  

## Challenges and difficulties faced by the team:

Some of the difficulties faced by our team during the creation of the Capstone project were:
- Making sure the forecast is taking into account that stores will grow in revenue since opening and how to make sure seasonality and cyclical trends are being taken into consideration.
- We wanted to make sure we were creating the model based on what day of the year it is, for example “ the first Friday of the year, etc. – Making sure to account the holidays and which week of the year it will be – Like 50th week of the year for Christmas. Also taken into account weekends. Up to this moment Maverik was using a Naïve Baies Model in which they use week days instead of date in order to make the analysis, for example, the first Monday of the year,  the 32 Wednesday of the year, etc. 
- Making sure to be able to evaluate the model metrics and also identify what is the average percentage of contribution for total annual revenue and ROI.

## My contribution to the project:

I believe my main contribution to this project was through the creation of important EDA processes and graphs representing the interactions between data variables, creation of the business problem stetatement for our initial steps of the project, researching all the possible models fom impementating while identifying which model would be more beneficial for our group to use and identifying the strengths and weaknesses of each model used, and lastly by creating the final presentation that would be used to show our project findings and demonstrate data visualization skills and implementation for our stakeholders. 

## Learnings:

Overall I learned so much with this on hands project and it was very interesting opportunity to work and learn with different individuals in the area of data analytics. I not only think it was a great opportunity for me to develop my analytical skills but also to understand more about how they are applicable to real-world scenarios and context challenges, while also learning how to better communicate and use data knowledge exchange tools to support the efficiency and communication/collaboration of the work project. It was also really important for me to learn how to better organize presentations in order to communicate effectively with stekaholders and create data visuzalizations that express the main points our team was trying to deliver with the project.


## Business Value of Solution / Project 
I personally believe that the main business value of our solution is the analysis and creation of different models that can be used by Maverik in real life in order to support better initial ROI documentaiton andbusinesss forecasting analysis when openinng a new store. We believe that the creation of these different models was really helpful in identifying the weaknesses and strengths of each of them and how each of the models caa affect the 4 main sales metrics provided by Maverik. The ARIMA model implemented was valable since it test whether features that were engineered actually improved model performance while the LASSO and VAR models were used to test predictions on the holdout set, using important features determined in the linear regression and ARIMA with external regressor models. 

Another important valuale solution of our project was the findings of our Exploratory Data Analysis, for example by identifying that major holidays may negatively affect business at Maverik, at least on the actual day of the holiday and some other sales metrics insights. This can be used by Maverik to better support business strategies while imple,enting the models created during the project.

Lastly, we believe that the our models provided better RMSE values in specific categories than in comparison to the ebnchmark RMSE values provided to us in the initial statges of the project. One example of tha is how our ARIMA models performed better for the diesel metric, in which benchmark values were 482976 for Threee Week Pred and 558546 for 2 Week Pred. while our ARIMA model had RMSE values of 445735 for Three Week Pred and 447000 for 2 Week Pred. This is valuable as it provides insights to the stakeholders on how each sales metrics is better evaluated when using one specific model instead of the other. The models created for the project,  LASSO, ARIMA, and VAR, all offer various strengths in identifying important relationships in the data as well as capturing the seasonality present in each stores data. Overall we believe our project provided imporant insights to our stakeholders and possible useful implementations and models that can be used to support ROI and forecasting. 





