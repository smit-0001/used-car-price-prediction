# Car Price Prediction 

In this project we try predict price of used cars using various machine learning models

## Apendix

- Part 1 - EDA - Visuals
    - Cast light on Cars Manufacturer , Fuel type , seller type of cars in our dataset
    - Average selling price of car wrt Fuel type , Transmission type and Owner rank.
    - Manufacturer and their average Price
    - how much cars is used based on km driven
- Part 2 - Model Building
    - Build Different Models.
    - Compare accuracy
    - select best model (we get maximum accuracy for random forest model)
    - Make Predictions

## A beirf Info On dataset

The original dataset (car_detail_v3.csv) was downloaded from kaggle which consisted of cars selling information from droom.com

The dataset consisted of the following columns

- name
- year
- selling_price
- km_driven
- fuel
- seller_type
- transmission
- owner
- mileage
- engine
- max_power
- torque
- seats

To Predict Selling Price

1) We make a proper dataset with important parameters.
    
The name were almost all unique even though we had around 150-200 different cars only

So Using Excel - 

- we remove the extra text from name and then split the name into two parts - cars manufacturer and cars model.

2) The cars details such as engine , max power , torque , seats we removed and intead we add a new column cpm - current market price of the car which is more powerful in predicting the current price instead of those parameters (engine , max power , torque , seats)

3) This was done by assigning cmp to each car using VLOOPUP function in EXCEL

-  The CMP - current market price of new model of that car was seached from google and added into the datasheet

## Part 1 _ visualization

We then Perform EDA on this.
Some key visualizations include
1) Histogram and Countplot showing Cars Manufacturer , Fuel Type and Seller Type 
2) Barplot showing average selling price of car wrt Fuel type (petrol / diseal / cng) , 
   Transmission type ( automatic / manual ) and Owner rank ( First owner / second / etc).
3) Bagraph of cars manufaturer and its average price 
4) Histplot showing Km driven of each car

## Part 2 - Model Building 

### Models used
We build different model 
( Linear Regression , Random Forest , 
K-Nearest Neighbour , Decision Tree ) 
and compare their accuracy.

### Accuracy comparision table

	Model	        	|  Accuracy 	| Cross Validation Score
	________________________|_______________|_______________________
	Linear Regression       |   z   54.1 %  |  54.23
	K-Nearest Neighbour	|  80.3 %       |  78.64
	Decision Tree	        |  96.4 %       |  94.18
	Random Forest	        |  97.4 %       |  96.02

### Selecting best model

we use Random forest since it gives maximun accuracy 

- Then we perform gridsearch 

- And then make a hyperparameter tuned rf model

For This :

    Score of Hyper Parameter Tuned Ranfom Forest Regressor is: 0.99
    Accuracy for predicting price of car is 97.21 %
    MSE of Hyper Parameter Tuned Random Forest Regressor: 13839643321.412754
    RMSE of Hyper Parameter Tuned Random Forest Regressor: 117642.01341958049

- Lastly we make predictions using this model

- We save the model using pickel
