# PhenomDetect: Detection of Air Hazards in the U. S.

This project utilizes a ML algorithms to detect air quality conditions in parts of the United Stated based on satellite data. A Tableau dashboard is included to visualize the predicted Air Quality Index (AQI) in different regions. The visualization tool also includes ancillary data to access the impact of the detection. For interactive visualizations [visit this](https://public.tableau.com/profile/shahed.anzarus.sabab#!/vizhome/AirHazardDetection/StoryofAirHazard?publish=yes) link:

![](Figures/dashboard.PNG?raw=true)

# Motivation:
This project is a team effort of Team 'Vesper' participated in the [NASA International Space Apps Challenge'20](https://2020.spaceappschallenge.org/challenges/inform/automated-detection-hazards/teams/vesper/project). Our team took on the challenge of the automatic air hazard detection because we were inspired by the idea of building a tool that could potentially save many lives just by automatically analyzing data from a variety of sources and putting this analysis into the hands of key decision-makers, as well as the general public. 

Our approach in solving the problem involved investigating several machine learning models to automate the detection of hazards (e.g., air hazards), building a dashboard to visualize the detections and incorporating ancillary data in an attempt to show the scope and impact of the detected hazards. 

To develop the machine learning model, we utilized popular python libraries like scikit-learn and TensorFlow, which allowed us to explore the data, construct new features and evaluate several machine learning models. The following strategies are considered:

• Exploratory data analysis has been performed.<br>
• 2 new features (i.e., wind_direction, wind_speed) are engineered.<br>
• Other demographics (i.e., population density, COPD patients, forest percentage, number of registered vehicles) of specific regions are also integrated as features.<br>
• Correraltion heatmap is generated to investigate inter feature correlation.<br>
• Different models have been built e.g., Linear Regression, SVM, Random Forest, Gradient Boosting Regression, XGBoost Regression, K-Nearest Neighbour, Bidirectional LSTM network, Bidirectional GRU Network, Multilayer Perceptron Network and 1-D Convolutional Network. <br>
• The highest performance is achieved from Random Forest, R2 = 0.56.<br>
• A dashboard is created to visualize the best model's predicted air quality index (AQI) in 2019.
• Analyzing the predicted data uncovered factors related to health impacts (e.g., Chronic obstructive pulmonary disease) and environmental issues (e.g., number of vehicles) because of air hazard. 

# Data
The data initially collected from s3://impact-datashare/pm2.5-labeled which has the following features: 

1. station_id: Unique identifier of the PM 2.5 monitors stationed across US <br>
2. stime: Time and date of sample recorded <br>
3. air_data_value: EPA air data PM2.5 readings <br>
4. RH: relative humidity from HRRR <br>
5. UGRD, VGRD: Wind speed vectors from HRRR <br>
6. HPBL: Height of Planetary Boundary Layer from HRRR <br>
7. TMP: Temperature recorded from HRRR <br>
8. goes_measurement: AOD reading from GOES R <br>

This data has been integrated with other engineered features for the modeling. The data we used for modeling has the following features:

1. lat: Latitude collected from the location of the station_id <br>
2. lon: Longitude collected from the location of the station_id <br>
3. RH: relative humidity from HRRR <br>
4. HPBL: height of Planetary Boundary Layer from HRRR <br>
5. RH: relative humidity from HRRR<br>
6. TMP: temperature recorded from HRRR <br>
7. goes_measurement: AOD reading from GOES R <br>
8. wind_direction: engineered from the initial features i.e., UGRD, VGRD<br>
9. wind_speed: engineered from the initial features i.e., UGRD, VGRD<br>
10. pop_density: Population density collected from the state of the (latitude, longitude) <br>
11. forest_perc: Forest Percentage indicating total amount of timberland in different states <br>
12. copd_heart: Chronic obstructive pulmonary disease (COPD) patients in different states <br>
13. air_data_value: EPA air data PM2.5 readings <br>

Please check the data directory which includes the following files:
1. air_data_master.csv - This data is used for modeling.<br>
2. air_data_viz_master.csv - This data inccludes the predicted results from the model.<br>

# Model Prediction
Before feeding the data to the model, the data was shuffled randomly and splitted into 70:30 as training and testing. The later 30 percent data were used for testing and the predicted results were visualized using tableau.

# Model Performance
![](Figures/performance.PNG?raw=true)
![](Figures/impFeatures.PNG?raw=true)

# How to run:
Please check the following files:

1. airqualityPredictionML.ipynb: This notebook includes our data investigation and model generation strategies. We used SVM, Random Forest, Gradient Boost. <br>
2. airqualityPredictionANN.ipynb: This notebook includes our model genertion using LSTM, MLP. <br>
3. Air Hazard Detection.twb: This file is the visualization of the best model using Tableau. <br>
4. DataPreprocessing&FeatureEngineering.ipynb: This notebook includes the feature engineering steps. <br> 

