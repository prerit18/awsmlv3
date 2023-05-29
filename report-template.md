# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME HERE

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
When I tried to submit the predictions, realised there were predictions and count below 0 which I had to convert them to 0. As count cant be below 0. Also when I was created new features and hyerparameters, I had to do the same.

### What was the top ranked model that performed?
WeightedEnsemble_L3 was the best model out of the 13 models including Light GBM, etc. This was same across when fitted the model without new features or hyperparameters as well.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
As this is Bike sharing data, I analysed it is important that we concentrate the and break the time at granular level to understand the demand better at what time therefore I first converted datetime into datetime and then extracted year, month, day, hour as sepearate features just to ensure we understand and give these features to the models to do the prediction.

### How much better did your model preform after adding additional features and why do you think that is?
After adding the new features that is granular level details, the score significantly improved, this is due to the fact the during office hours or during daytime (morning hours) the demand is quite high which is expected as many people would want the bike during the same time to commute to office, universities, etc.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After adding hyperparameters the model performance dipped a bit but the test score became better, may be with the features the model was overfitting but with hyperparameters model and predictions became a bit stable.

### If you were given more time with this dataset, where do you think you would spend more time?
I would like to do more feature engineering with features like Holiday to understand if there is any relation, also in EDA will perform multivariate and bivariate analysis to understand the corealtion of the columns better. more tuning of hyperparameter as we know hyperparameters play a critical role in model performance.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
model	hpo1	hpo2	hpo3	score
0	initial	default_vals	default_vals	default_vals	1.79653
1	add_features	default_vals	default_vals	default_vals	0.67810
2	hpo	GBM: num_leaves: lower=26, upper=66	NN: dropout_prob: 0.0, 0.5	GBM: num_boost_round: 100	0.48190

### Create a line plot showing the top model score for the three (or more) training runs during the project.

[model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

[model_test_score.png](img/model_test_score.png)

## Summary
Overall autoglue helped massively in model comparison to give the best performing model to be used to predict the values for a column or a label, in the current problem statement we saw teh importance of frature engineering and exploratory data analysis as it enhances the model performance, but we also need to do more analysis like bivariavte and multivariate analysis to understand the corelation between the models, create confusion matrix to understand the model performance better.
