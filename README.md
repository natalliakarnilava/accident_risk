# Project description
It is necessary to create a system that could predict the risk of an accident along the chosen route for a carsharing company, where risk is the probability of an accident with any damage to the vehicle. Once a driver has booked a car, got behind the wheel, and chosen a route, the system must assess the level of risk. If the risk level is high, the driver will see a warning and route recommendations.

The major task is to understand whether it is possible to predict accidents based on the historical data of one of the regions.

The customer requires to cover following points:

1. Create an accident prediction model (target value is at_fault (the culprit) in the parties table)
  * For the model, select the type of culprit - only the car (car).
  * Select cases where the accident resulted in any damage to the vehicle, except for the type of SCRATCH (scratch).
  * For modeling, limit the data for 2012 - they are the most recent.
  * A prerequisite is to take into account the factor of the age of the car.
2. Based on the model, explore the main factors of the accident.
3. Understand whether the results of modeling and analysis of the importance of factors will help answer the questions:
  * Is it possible to create an adequate driver risk assessment system when issuing a car?
  * What other factors need to be considered?
  * Does the car need to be equipped with any sensors or a camera?

# Summary

The best model is the LGBMClassifier, which showed the value of the F1-score at the level of 0.617853 on the validation set with boosting_type='dart', learning_rate=0.01 and max_depth=8 hyperparameters, and  F1-score of 0.6011 on the test data set.

However, the model adequately predict the overall risk of an accident only under the assumption that people get into an accident only when they themselves are guilty.

It seems unrealistic to force customers to build a route on the built-in car-sharing car navigators, then make sure that they do not stray from the intended route.

Nevertheless, there is a way for model improvement. For example, to integrate customers' driving data like their driving experience, the presence of an accident in the past, the presence of fines from the traffic police, the fact of registration at a drug dispensary, etc.
