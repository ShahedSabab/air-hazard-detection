# PhenomDetect: Detection of Air Hazards in the U. S.

This project utilizes a ML algorithms to detect air quality conditions in parts of the United Stated based on satellite data. A Tableau dashboard is included to visualize the predicted Air Quality Index (AQI) in different regions. The visualization tool also includes ancillary data to access the impact of the detection.

For interactive visualizations visit the following link:
https://public.tableau.com/profile/shahed.anzarus.sabab#!/vizhome/AirHazardDetection/StoryofAirHazard?publish=yes

![](dashboard.PNG?raw=true)

# Motivation:
Our team took on the challenge of the air hazard detection because we were inspired by the idea of building a tool that could potentially save many lives just by automatically analyzing data from a variety of sources and putting this analysis into the hands of key decision-makers, as well as the general public. 

Our approach in solving the problem involved investigating several machine learning models to automate the detection of hazards, building a dashboard to visualize the detections and incorporating ancillary data in an attempt to show the scope and impact of the detected hazards. 

To develop the machine learning model, we utilized popular python libraries like scikit-learn and TensorFlow, which allowed us to explore the data, construct new features and evaluate several machine learning models. Throughout the hackathon we tried the following models: Linear Regression, Support Vector Regression, Random Forest Regression, Gradient Boosting Regression, XGBoost Regression, K-Nearest Neighbour, Bidirectional LSTM network, Bidirectional GRU Network, Multilayer Perceptron Network and 1-D Convolutional Network. We utilized Google Colab to train and evaluate these models. We used the R2 value as the primary evaluation metric. After many attempts at optimizing the models, our highest performing model was the Random Forest Regression model, which achieved an R2 value of 0.56. 

We utilized Tableau to create a dashboard for visualizing the detections. Since our model is not very accurate, we attempted to demonstrate the impact of the solution by visualizing an aggregation of the detections. We also included ancillary data such as the population density of U. S. states (2019) and an estimate of the forest cover in each state. These ancillary data are intended as supplementary information for accessing the impacts of the detection. 

The main problems we faced while working on this challenge are related to the data itself. Firstly, none of our team members had domain expertise in geological and meteorological data, so we did not have clear idea of the importance of the features of the dataset or how to combine them into more meaningful features. Secondly, the data had an inconsistent temporal resolution (data points are not consistently sampled every hour from each station), which made it especially difficult for our machine learning models. Finally, we also struggled while deciding which ancillary data to include in the visualization tool to create a more impactful solution. 

Despite the challenges, our team put together a tool that we think will become useful as more development time goes into it.

# How to run:
Please check the following files:

1. airqualityPredictionML.ipynb: This notebook includes our data investigation and model generion strategies. We used SVM, Random Forest, Gradient Boost. <br>
2. airqualityPredictionANN.ipynb: This notebook includes our model genertion using LSTM, MLP. <br>
3. Air Hazard Detection.twb: This file is the visualization of the best model using Tableau. <br>
4. DataPreprocessing&FeatureEngineering.ipynb: This notebook includes the feature engineering steps. <br> 

