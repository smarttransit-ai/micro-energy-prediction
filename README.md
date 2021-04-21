# micro-energy-prediction

## Training Data:
For each vehicle class (model year), download data of all seasons in 2020, each season contains 2-week data.

**Features for Training

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

For *Diesel Bus in Model Year 2014*, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 6 neurons and 6 neurons, respectively 	
		- The first layer has ‘sigmoid’ activation function 
		- The second layer has ‘rectified linear’ activation function 
	•	One output layer.  	
		- Linear activation function 

The model is optimized using 'adam' optimizer with a default learning rate 0.001

