# Kaggle-Competition---Predicting-CO2-emissions-with-Gradient-Boosting-Regression-Model
A short Kaggle competition with the goal of creating a **Machine Learning predictive model** that **predicts Rwanda's CO2 emission levels based on satellites' information**.
For this competition I had **only 24 hours** (since I discovered the last day) so I decided to build a single Machine Learning model and improve it as much as possible in the little time I had.
On this occasion, there'll be only one jupyter notebook and the EDA will be very brief: it's only purpose will be choosing the right data to train the model.

## Introducing the case
Tracking carbon emissions is fundamental when it comes to deciding on measures against climate change. For this challenge, the objective was to create a predictive model (using Machine Learning) trained on open-source CO2 emissions **data from Sentinel-5P sattelite** observations.

The training data ranged from 2019 to 2021, and the **goal** was to **predict 2022 carbon emissions** based on it. 
Approximately 497 unique locations were selected from multiple areas in Rwanda.

*For more detailed information on this competition, click the following link:* https://www.kaggle.com/competitions/playground-series-s3e20/overview

## Competition's Rules
Each person/team would have **unlimited submissions** (although there was a daily limit) and would have **around 3 weeks** to create a model. 
We could decide to not use some of the information provided in the dataset, *however*, we were **not allowed** to use any **external data**. 
The **evaluation metric** for this competition was the **RMSE** (Root Mean Square Error).

## Dataset available
The dataset had **79023 entries** and **76 columns**, but the **main features** (without breaking them down) are:
  - ID (consists on a label made from the Latitude, Longitude, Year and Week of the measurement).
  - Sulphur Dioxide measures.
  - Carbon Monoxide measures.
  - Nitrogen measures.
  - Formaldehyde measures.
  - UV Aerosol Index measures.
  - Ozone measures.
  - Cloud measures.

## Model Selection
I decided to go with a **Gradient Boosting Regression** model since it tends to be more accurate than other type of models and, because the training dataset was so large and my time was limited, I wouldn't have much time to analyze the results and iterate over a model.

## 1st iteration: Creating a basic model
First things first: I wanted to have a *working model* *ready to submit*, even if it wasn't that good from the start. The first model was build very quickly but performed relatively poorly when it came to the predictions: the **initial RMSE score** on this one was close to **82** when submitted (RMSE Score should be as close to 0 as possible, and the best models for this competition where close to a score of 10).

## 2nd iteration: Tuning the parameters
Having built a working model I decided to **focus on the parameters** (since the ones I initially used provided a very shallow analysis on the data). For this model, I decided to make **deeper trees**, **increase the number of estimators** (trees used to create the model) and **reduce the learning rate** of each one. 
This resulted in a very long training time but the reward was significant: the initial **RMSE score** for this one when submitted was around **41**. The **performance for this model** was basically **doubled in a single iteration**.

## 3rd iteration (Incomplete): Hyper-tuning the parameters
I tried to get cross-validated parameters for this model on time but it's a very lengthy process and sadly I wasn't able to pull this one off before the deadline.
However, hyper-tuning the parameters would've probably improved the model's performance significantly (since defining good parameters for the trees is key in this type of model).

## Results
The model did pretty decently, and having participated only for *a single day* (in a competition where many people submitted dozens of entries) I got **#891** out of **#1442**.

**The resulting dataset** was just numbers and values that were relatively **difficult to picture**, so here's a **heatmap with the results**:

![Heatmap for Rwanda CO2-2_pages-to-jpg-0001](https://github.com/DataGuti/Kaggle-Competition---Predicting-CO2-emissions-with-Gradient-Boosting-Regression-Model/assets/57073572/f42f640d-66fe-491e-bf48-bcc2c0c429c5)

## Future lines of work
**A more detailed and time-consuming EDA** would provide better insights when it comes to selecting the appropiate metrics to use and, ultimately, deciding on the most adequate model for this challenge.
Also, **hyper-tuning the parameters** would significantly boost this model's performance. 
Finally, some **environmental research** probably could help to filter some of the metrics and provide insightful relations across different variables (e.g: check for *multicollinearity*, *redundance*, *causation*, etc.)

