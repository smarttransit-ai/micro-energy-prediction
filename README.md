# Micro-energy-prediction
The HDEMMA project has been collecting real-time vehicle driving and energy consumption data at 1Hz frequency for Gillig Diesel (MY2014, MY2009, MY2002, and MY1998), Hybrid (MY2014 and MY2009) and Electric (MY2016) buses. The project team developed a microscopic energy prediction model to estimate energy consumption of Gillig Diesel, Hybrid and BYD Electric buses at 1Hz frequency. Artificial Neural Network (ANN) is used as the estimation model structure. The input and output variables, specific model structure, and model convergence are discussed below. Part of this work was presented in the paper entitled "Hybrid electric buses fuel consumption prediction based on real-world driving data" https://doi.org/10.1016/j.trd.2020.102637. The contributors of this work are Ruixiao Sun and Yuche Chen, working at Department of Civil and Environmental Engineering, University of South Carolina.

## Raw Data
The raw data is 1Hz driving and energy consumption measurement recorded by on-board sensors on transit buses in year 2019 and 2020. The buses are in the transit operating fleet of Chattanooga Area Regional Transportation Authority (CARTA). The collected data include real-time location/elevation, vehicle activities (instantaneous speed, acceleration), energy related parameters (i.e. fuel rate/power). The data is retrieved at 1Hz frequency. The transit buses are running at pre-defined bus routes in Chattanooga metropolitan region. The routes represent typical mountainous terrain patterns in the region, which is surrounded by Tennessee River and ridge-and-valley Appalachians.

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
	5.	Road grade [difference of elevations devided by difference of driving distances between last second and this second]

**Target Feature (Output Variable): 

Energy Consumption: gallon/hour for diesel and hybrid classes and kWh for electric class.

The sample of the training data is shown below.

<img src="https://github.com/smarttransit-ai/micro-energy-prediction/blob/main/data_sample.png" alt="alt text" width="400" height="150">


[DrivingProfile](https://github.com/smarttransit-ai/micro-energy-prediction/tree/main/DrivingProfile) is the folder containing samples of standard driving profiles at peak hour and off-peak hour in each season.


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

**Demonstration**

See the [demonstration notebook](https://github.com/smarttransit-ai/micro-energy-prediction/blob/main/Diesel%20MY%201998/DieselMY1998_demonstration.ipynb) in each model-year folder.

## Acknowledgement

This material is based upon work supported by the Department of Energy, Office of Energy Efficiency and Renewable Energy (EERE), under Award Number DE-EE0008467 and National Science Foundation under grant 1952011. Any opinions, findings, and conclusions or recommendations expressed in this material are those of the author(s) of these papers and do not necessarily reflect the views of the National Science Foundation or the Department of Energy.
