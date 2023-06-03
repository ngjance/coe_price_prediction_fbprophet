# COE Price Prediction using FBprophet


## Purpose of the Project
The purpose of this project is to create a model to predict the COE prices in Singapore.

The success metrics are:
1. R2 score
2. Root Mean Square Error (RMSE)
3. Mean Absolute Percentage Error (MAPE)


## Data Sets
The data sets were downloaded from https://www.singstat.gov.sg/.
 

## Data Cleaning

1. Some data manuipulation were first done in Excel.

2. This include rearranging the the second round of bidding under the same column as the first round of bidding as we want to have a sequential view.

3. As we do not have the exact date of the bidding, we simiply change first round of bidding to every first of the month and second round of bidding to every 15th of the month.

4. The datasets were then loaded into Jupyter notebook, where further cleaning such as removing null values and changing dtype is done.

5. Since we do not know some information, such as the number of successful bids and the COE premium itself on the day of bidding, we shifted these columns to lag 1.

5. All the datasets were then combined into one data frame, which is used for the base model.


## The Approach
1. For each COE category, there will be one model to make the prediction.

2. We use all the columns as the regressors to create a base model and get a base result.

3. We then only select the regressors that are at least 60% correlation with the respective category premiun for the remodel.


## Models Evaluation
|                      	| **r2** 	| **RMSE** 	| **MAPE** 	|
|:--------------------:	|:------:	|:--------:	|:--------:	|
| **Cat A Base Model** 	|  91.31 	| 6,264.72 	|   18.21  	|
| **Cat A Remodel**    	|  94.93 	| 4,785.22 	|   14.22  	|
| **Cat B Base Model** 	|  89.48 	| 8,130.42 	|   20.87  	|
| **Cat B Remodel**    	|  92.59 	| 6,823.10 	|   18.68  	|
| **Cat C Base Model** 	|  89.31 	| 8,245.02 	|   14.13  	|
| **Cat C Remodel**    	|  91.61 	| 7,306.83 	|   13.01  	|


## Conclusion
1. The models provided very good accuracy score, though the RMSE and MAPE can be improved.

2. The models do not seem to work as well from year 2022 onward, when there is a lot of global factors impacting Singapore's economy.


### Application of Model
This model only serves as a guide, and users should consider other factors that might affects people's decision to purchase new vehicles in Singapore.# coe_price_prediction_fbprophet
