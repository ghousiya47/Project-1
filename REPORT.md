# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### GHOUSIYA BEGUM

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
When attempting to submit predictions, I realized that the output of the predictor needed to be in a specific format to match the submission requirements. This involved ensuring that the predictions were aligned with the test dataset and formatted correctly before submission.


### What was the top ranked model that performed?
The top ranked model that performed was the hpo_model that used WeightedEnsemble_L3. It resulted in a validation RMSE score of -30.546908 and the best submission score for Kaggle at 0.49.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The feature "datetime" was hourly information so I added data for "year", "month", "day", and "hour as distinct features from "datetime". 
Additionally, "season" and "weather" were transformed to categorical type.

### How much better did your model preform after adding additional features and why do you think that is?
My model's performance improved by 58 points, from the initial model of 76.65 to the model with additional features of 19. It resulted in a RMSE score of 1.80608 to 0.703. Ideally, we want our RMSE score to be within 0 and 1. I think the additional features which changed data types into true categorical datatypes and the feature of ignoring the "casual" and "registered" columns helped with reducing multicolinearity and improved interpretability.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After trying different parameters, the model's kaggle score improved by 0.21 points, from 0.703 to an improved score at 0.49. However, the RMSE score decreased from 19.79 to 18.58.

### If you were given more time with this dataset, where do you think you would spend more time?
If I were given more time, I would perhaps try some more different model algorithms and see how each model performs. I would also change the parameters around to see how it affects the fit of the model and learn more about hyperparameters. I would also change epoch vaule and increase number of trials value to get a better kaggle score.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default|default|default|1.80276|
|add_features|default|default|default|0.70335|
|hpo|GBM:'num_boost_round': 100,'num_leaves'(lower=26, upper=66, default=36)|NN_TORCH (num_epochs': 10), activation('relu', 'softrelu', 'tanh'), dropout:(0.0, 0.5, default=0.1)|search_strategy: 'auto', num_trials: 2, scheduler: local|0.49091|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
TODO: Add your explana
