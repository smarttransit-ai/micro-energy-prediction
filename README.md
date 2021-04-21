# micro-energy-prediction
CARTA has been collecting real-time vehicle driving and energy consumption data at 1Hz frequency for Gillig Diesel (MY2014) bus. The project team develops a microscopic energy prediction model to estimate energy consumption of Gillig Diesel (MY2014)at 1Hz frequency. Artificial Neural Network (ANN) is used as the estimation model structure. The input and output variables, specific model structure, and model convergence are discussed below. 

## Training and Cross-validation Data:
2-weeks of data in each of the following season in year 2019 and 2020: 
        Spring  (March-May)
        Summer  (June-August)
        Fall    (September-November)
        Winter  (December-Febuary) 

**Features for Training (Input)

For diesel and hybrid vehicles:

	1.	Vehicle trajectory (Speed, acceleration)
	4.	Weather features (Humidity, temperature)
	5.	Road gade

For electric vehicles:

 	1.	Vehicle trajectory (Speed, acceleration, speed^2, speed^3, speed_acceleration)
	4.	Weather features (Humidity, temperature)
	5.	Road gade

**Target Feature: 

Energy Consumption Rate (gal/h for diesel and hybrid, and kW for electric)

## Prediction model (ANN):

Based on our experiments, we found that different network structures work best for different vehicle classes.

For **Diesel Bus in Model Year 2014**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 6 neurons and 6 neurons, respectively 	
		- The first layer has ‘sigmoid’ activation function 
		- The second layer has ‘rectified linear’ activation function 
	•	One output layer.  	
		- Linear activation function 

The model is optimized using 'adam' optimizer with a default learning rate 0.001

