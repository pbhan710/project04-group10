# Introduction
Our team decided to analyze the recent volatility in the housing market and attempt to predict where the market is heading with machine learning. After scouring the internet for datasets on the topic, we chose Realtor.com monthly data detailing monthly change in inventory from January 2016 through February 2023. Once we had our starting target data, we then added monthly weather, unemployment, and mortgage interest rate data as additional features. Finally, we found a dataset showing the change in market hotness and incorporated that as an additional feature. Our goal then became to predict if the housing market will be hot or not by State.

   ![gettyimages-1219272291-612x612](https://user-images.githubusercontent.com/112498067/222026789-b7866f2f-778b-43fa-9b1a-8205f689249b.jpg)

[Project Proposal](https://docs.google.com/document/d/1xqcCmtrioxThe1zX2F1_XzJN-4-UOv9txNYIFMb7ytQ/edit)

### Extract, Transform, and Load
Once we decided on our datasets and project goal, we extracted all the data and began to transform it by State, dropping all superfluous columns that were not of interest and eliminating all NaN values. Once the data was transformed, we joined the datasets and loaded them into a SQL database suitable to deploy our learning models.

### Split, Train, and Test


# Appendix
This section will capture references and additional information applicable to this project.

## Data References
- [Zillow Housing Data](https://www.zillow.com/research/data/)
- [U.S. Bureau of Labor Statistics - Top Picks](https://data.bls.gov/cgi-bin/surveymost?la)
- [Realtor.com](https://www.realtor.com/research/data/)
- [United States Census Bureau](https://www.census.gov/data.html)
- [National Alliance for Public Charter Schools](https://data.publiccharters.org/) 

![gettyimages-1303100759-612x612](https://user-images.githubusercontent.com/112498067/222028641-f8ac4cde-a3c3-48f3-a818-6d7f6753a32e.jpg)


## Contributors
- Adams, Heather
- Distasi, Paul
- Han, Paul
- Ho, Justin
- Leopold, Matthew
