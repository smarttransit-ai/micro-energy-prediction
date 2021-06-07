# micro-energy-prediction
CARTA has been collecting real-time vehicle driving and energy consumption data at 1Hz frequency for Gillig Diesel (MY2014, MY2009, MY2002, and MY1998) and Hybrid (MY2014 and MY2009) buses. The project team develops a microscopic energy prediction model to estimate energy consumption of Gillig Diesel and Hybrid at 1Hz frequency. Artificial Neural Network (ANN) is used as the estimation model structure. The input and output variables, specific model structure, and model convergence are discussed below. 

## Raw Data
The raw data is 1Hz driving and energy consumption measurement recorded by on-board sensors on transit buses in year 2019 and 2020. The buses are in the transit operating fleet of Chattanooga Area Regional Transportation Authority (CARTA). The collected data include real-time location/elevation, vehicle activities (instantaneous speed, acceleration), energy related parameters (i.e. fuel rate). The data is retrieved at 1Hz frequency. The transit buses are running at pre-defined bus routes in Chattanooga metropolitan region. The routes represent typical mountainous terrain patterns in the region, which is surrounded by Tennessee River and ridge-and-valley Appalachians.

## Training and Cross-validation Data:
2-weeks of data in each of the following season in year 2019 and 2020: 
        Spring  (March-May)
        Summer  (June-August)
        Fall    (September-November)
        Winter  (December-Febuary) 

**Features for Training (Input Variables)

	1.	Vehicle instantaneous speed (kilometer per hour)
	2.	Vehicle instantaneous acceleration (meter per second^2)
	3.	Relative humidity (0-1)
	4.	Temperature (F)
	5.	Road gade (%)

**Target Feature (Output Variable): 

Energy Consumption Rate (gallon/hour)

The sample of the training data is shown below.

<img src="https://github.com/smarttransit-ai/micro-energy-prediction/blob/main/data_sample.png" alt="alt text" width="400" height="150">


## Prediction model selection(ANN):
5-folds cross-validation is implemented to compare and select ANN structure. 

Based on our experiments, we found that different network structures work best for different vehicle classes.

For **Diesel Bus in Model Year 2014**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 11 neurons and 11 neurons, respectively 	
		- The first layer has ‘tanh’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 
		
For **Diesel Bus in Model Year 2009**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 10 neurons and 10 neurons, respectively 	
		- The first layer has ‘tanh’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 
		
For **Diesel Bus in Model Year 2006**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 10 neurons and 10 neurons, respectively 	
		- The first layer has ‘relu’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 
		
For **Diesel Bus in Model Year 2002**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 11 neurons and 11 neurons, respectively 	
		- The first layer has ‘tanh’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 
		
For **Diesel Bus in Model Year 1998**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 11 neurons and 11 neurons, respectively 	
		- The first layer has ‘tanh’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 

For **Hybrid Bus in Model Year 2014**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 11 neurons and 11 neurons, respectively 	
		- The first layer has ‘tanh’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 
		
For **Hybrid Bus in Model Year 2009**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 10 neurons and 10 neurons, respectively 	
		- The first layer has ‘tanh’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 

For **Electric Bus in Model Year 2016**, the best model has 

	•	One input layer 	
		- Has one neuron for each predictor variable 
	•	Two hidden layers  	
		- Have 11 neurons and 11 neurons, respectively 	
		- The first layer has ‘tanh’ activation function 
		- The second layer has ‘relu’ activation function 
	•	One output layer.  	
		- Linear activation function 
		

All the model are optimized using 'adam' optimizer with a default learning rate 0.001

