# Introduction
Our team decided to analyze the recent volatility in the housing market and attempt to predict where the market is heading with machine learning. After scouring the internet for datasets on the topic, we chose Realtor.com monthly data detailing monthly change in inventory from January 2016 through January 2023. Once we had our starting target data, we gathered features such as monthly weather, unemployment, and even a 'hotness' housing metric. Finally, we found a dataset showing the change in market hotness and incorporated that as an additional feature. Our goal then became to predict if the housing market will be hot or not by State.

![chart](https://user-images.githubusercontent.com/112498067/223543032-ad52825d-50c4-4225-89c1-c885494292b2.png)

![image](https://user-images.githubusercontent.com/112498067/223527623-b430a5cf-50b0-4f55-9f8f-b5f3265fc65c.png)

[Project Proposal](https://docs.google.com/document/d/1xqcCmtrioxThe1zX2F1_XzJN-4-UOv9txNYIFMb7ytQ/edit)

# Target and Features
**Target**: *Hot* or *Not Hot*
- *Hot* indicated a positive change in housing inventory.
- *Not Hot* indicated a negative or neutral change in housing inventory.

**Features**
- *median_listing_price*: 
- *median_listing_price_mm*:
- *active_listing_count*:
- *active_listing_count_mm*:
- *median_days_on_market*:
- *median_days_on_market_mm*:
- *new_listing_count*:
- *new_listing_count_mm*:
- *price_increased_count*:
- *price_increased_count_mm*:
- *price_reduced_count*:
- *price_reduced_count_mm*:
- *median_listing_price_per_square_foot*:
- *median_listing_price_per_square_foot_mm*:
- *median_square_feet*:
- *median_square_feet_mm*:
- *average_listing_price*: Average price of total listed houses.
- *average_listing_price_mm*:
- *total_listing_count*: Total number of houses available.
- *hotness_rank_mm*: Change in 'hotness' rank from last month.
- *hotness_score*:
- *temperature_F*: Temperature in Fahrenheit (F).
- *temp_change_pct*: Change in temperature (F) from last month.
- *unemployment_rate*: Unemployment rate.
- *unemployment_rate_change_pct*: Change in unemployment rate from last month.

### Extract, Transform, and Load
Once we decided on our datasets and project goal, we extracted all the data and began to transform it by State, dropping all superfluous columns that were not of interest and eliminating all NaN values. We then created columns to show the monthly change in values for all features. Once the data was transformed, we joined the datasets and loaded them into a SQL database suitable to deploy our learning models.

### Split, Train, and Test
- The goal was to train multiple supervised models (numerical prediction models) used to predict monthly inventory by state and determine which model fits best. The first step was to connect to our SQL table we created:
![image](https://user-images.githubusercontent.com/112498067/223518489-64b7c0fc-33d4-4c4c-b3b0-52563ecb4398.png)
- The second step was to preprocess the data in preparation of analysis.
- The final step was to split our data into test and train groups.

### Apply Different Models and Hyperparameterize, and Compare Results
##### Models to Train:
- Random Forest
- Logisitic Regression
- Neural Networks

##### Consider the following questions:
- What pros/cons are important to consider for each model?
- Which score(s) make sense for our scenario? Is accuracy the most important score for our model? In other words, should precision, etc. take precedence over other scores to determine the best model?
-False Positive: The model predicts a "hot" market (i.e., an increase in inventory), but in reality, it was not hot. This would negatively impact the buyer in facing stiffer competition due to lower inventory, thus potentially paying more for a home than expected or not being able to purchase a home at all.
-False Negative: The model predicts a "not hot" market (i.e., a decrease in inventory), but in reality, it was hot. This may negatively impact the buyer in missing out altogether on a housing market with higher inventory.

# Results per Model

- Random Forest Model:

![image](https://user-images.githubusercontent.com/112498067/223524398-a5c2124a-28ba-4fd4-9887-8a52f26cee92.png)

![image](https://user-images.githubusercontent.com/112498067/223579718-b4fab1f2-d800-4dff-9f62-12732c213ae3.png)

![image](https://user-images.githubusercontent.com/112498067/223524814-6f7352f7-8fde-4edd-a1ed-d9ff0176246b.png)

##### Feature Importance for Random Forest Model:
![image](https://user-images.githubusercontent.com/112498067/223579785-20810a7a-4da8-4a95-8b97-2af4d9f905e8.png)

- Logistic Regression Model:

![image](https://user-images.githubusercontent.com/112498067/223525715-5bd5775a-5aca-47a8-8018-fd590775f6a5.png)

![image](https://user-images.githubusercontent.com/112498067/223579891-a894d8f9-f78e-46be-9ca2-6a25085fe91b.png)

![image](https://user-images.githubusercontent.com/112498067/223525845-7596cbc1-483c-49a8-9b40-37685e11f024.png)

- Neural Networks Model

![image](https://user-images.githubusercontent.com/112498067/223525962-b4f64ec6-a88e-4b49-a57b-d823faa6199a.png)

#Loss:

![image](https://user-images.githubusercontent.com/112498067/223579965-ab748c1c-0d3e-4307-ba4b-3566e3722ef2.png)

#Accuracy:

![image](https://user-images.githubusercontent.com/112498067/223580006-936e991d-2795-4598-9fe7-3cc4934d7b19.png)

## Data References
- [Realtor.com](https://www.realtor.com/research/data/)
- [U.S. Bureau of Labor Statistics - Top Picks](https://data.bls.gov/cgi-bin/surveymost?la)
- [National Centers for Environmental Information (NCEI)](https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/statewide/time-series[…]/1/2016-2023?base_prd=true&begbaseyear=1901&endbaseyear=2000)

## Contributors
- Adams, Heather
- Distasi, Paul
- Han, Paul
- Ho, Justin
- Leopold, Matthew
