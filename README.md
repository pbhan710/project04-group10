# Introduction
Our team decided to analyze the recent volatility in the housing market and attempt to predict where the market is heading with machine learning. After scouring the internet for datasets on the topic, we chose Realtor.com monthly data detailing monthly change in inventory from January 2016 through January 2023. Once we had our starting target data, we then added monthly weather, unemployment, and mortgage interest rate data as additional features. Finally, we found a dataset showing the change in market hotness and incorporated that as an additional feature. Our goal then became to predict if the housing market will be hot or not by State.

![chart](https://user-images.githubusercontent.com/112498067/223543032-ad52825d-50c4-4225-89c1-c885494292b2.png)

[Project Proposal](https://docs.google.com/document/d/1xqcCmtrioxThe1zX2F1_XzJN-4-UOv9txNYIFMb7ytQ/edit)

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

# Results per model

- Random Forest Model:

![image](https://user-images.githubusercontent.com/112498067/223524398-a5c2124a-28ba-4fd4-9887-8a52f26cee92.png)

![image](https://user-images.githubusercontent.com/112498067/223524717-a65751e8-ef42-4120-9856-2209a8b05e52.png)

![image](https://user-images.githubusercontent.com/112498067/223524814-6f7352f7-8fde-4edd-a1ed-d9ff0176246b.png)

##### Feature Importancs for Random Forest Model:
![image](https://user-images.githubusercontent.com/112498067/223525245-0605c066-e730-4a0e-ac5f-fe86a0382766.png)

- Logistic Regression Model:

![image](https://user-images.githubusercontent.com/112498067/223525715-5bd5775a-5aca-47a8-8018-fd590775f6a5.png)

![image](https://user-images.githubusercontent.com/112498067/223525800-40648cf4-ff51-4287-a244-26421be5469b.png)

![image](https://user-images.githubusercontent.com/112498067/223525845-7596cbc1-483c-49a8-9b40-37685e11f024.png)

- Neural Networks Model

![image](https://user-images.githubusercontent.com/112498067/223525962-b4f64ec6-a88e-4b49-a57b-d823faa6199a.png)

#Loss:
![image](https://user-images.githubusercontent.com/112498067/223526147-b89600e6-7cd9-463a-92f4-ac74d929f1c6.png)
![image](https://user-images.githubusercontent.com/112498067/223526266-21ad0b7e-53e0-40d6-a430-4893a3c34e76.png)
![image](https://user-images.githubusercontent.com/112498067/223526625-99657e49-153a-4f2c-ae23-1f3e066e4be4.png)

#Accuracy:
![image](https://user-images.githubusercontent.com/112498067/223526845-791087d0-28b0-4540-b4bb-07e81d2d9ca4.png)
![image](https://user-images.githubusercontent.com/112498067/223526927-cdb588cb-9463-47c3-91fe-c33d9b0b44ab.png)
![image](https://user-images.githubusercontent.com/112498067/223527032-cdcae337-f005-43e4-90f5-588d11f4eb73.png)
![image](https://user-images.githubusercontent.com/112498067/223527230-a17c63a2-9838-4305-9b48-a8e507067e47.png)

# Appendix
This section will capture references and additional information applicable to this project.

## Data References
- [Realtor.com](https://www.realtor.com/research/data/)
- [U.S. Bureau of Labor Statistics - Top Picks](https://data.bls.gov/cgi-bin/surveymost?la)
- [National Centers for Environmental Information (NCEI)](https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/statewide/time-series[…]/1/2016-2023?base_prd=true&begbaseyear=1901&endbaseyear=2000)

![image](https://user-images.githubusercontent.com/112498067/223527623-b430a5cf-50b0-4f55-9f8f-b5f3265fc65c.png)

## Contributors
- Adams, Heather
- Distasi, Paul
- Han, Paul
- Ho, Justin
- Leopold, Matthew
