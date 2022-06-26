
## Solar Radiation Prediction using Random Forest and Randomized SearchCV

Solar Energy is the future, considering the fact that it is an inexhaustible energy source and requires low installation cost.

PV panels often cannot provide stable electrical power output due to variations in weather conditions, the power grid stability is reduced significantly while integrating the PV power to the power grid.As a stable power grid is a necessity, a precise forecasting technique is required for the stable and safe integration of the PV power to the power grid.

We can predict the power output for a particular array of solar power generators, knowing some environmental conditions. Generation of energy by a solar panel or cell depends upon the doping level and design of solar PV array but the main factors are the amount of solar radiation falling on the panel, environmental factors like atmospheric temperature and humidity and pressure and wind speed present on the panels . These factors are naturally variable and hence the output of solar cell directly depend on it.


About Data

These datasets are meteorological data from the HI-SEAS weather station from four months (September through December 2016) between Mission IV and Mission V.

For each dataset, the fields are:

* A row number (1-n) useful in sorting this export's results
* The UNIX time_t date (seconds since Jan 1, 1970). Useful in sorting this export's results with other export's results
* The date in yyyy-mm-dd format
* The local time of day in hh:mm:ss 24-hour format
* The numeric data, if any (may be an empty string)
* The text data, if any (may be an empty string)

The units of each dataset are:

* Solar radiation: watts per meter^2

* Temperature: degrees Fahrenheit

* Humidity: percent

* Barometric pressure: Hg

* Wind direction: degrees

* Wind speed: miles per hour

* Sunrise/sunset: Hawaii time

## Dependencies
* Python 3.6

* Pandas

* scikit-learn

* Matplotlib

* Seaborn

* Numpy

## Model
Random forest is a supervised learning algorithm. The “forest” it builds is an ensemble of decision trees, usually trained with the “bagging” method. The general idea of the bagging method is that a combination of learning models increases the overall result.

Put simply: random forest builds multiple decision trees and merges them together to get a more accurate and stable prediction.

One big advantage of random forest is that it can be used for both classification and regression problems, which form the majority of current machine learning systems.




![random-forest-algorithm](https://user-images.githubusercontent.com/105455186/175829431-f6209be6-4c50-4147-9be2-91500abc0c90.png)



## Refrences

 - [Random Forest](https://builtin.com/data-science/random-forest-algorithm)

 - [Hyperparameter Tuning](https://www.jeremyjordan.me/hyperparameter-tuning/)

 - [Randomized SearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html)



## Results

The model was evaluated using : 
r2_score : 0.8094939996265258
RMSE : 108.55174675101202

The performance of the model : 
![Performance of the model in prediction of Radiation for corresponding UNIXTime](https://user-images.githubusercontent.com/105455186/175832445-3663f7f6-d00b-4cb2-93dc-f41839875cd9.png)


Another great quality of the random forest algorithm is that it is very easy to measure the relative importance of each feature on the prediction. Sklearn provides a great tool for this that measures a feature’s importance by looking at how much the tree nodes that use that feature reduce impurity across all trees in the forest. It computes this score automatically for each feature after training and scales the results so the sum of all importance is equal to one.

![Importance of different parameters](https://user-images.githubusercontent.com/105455186/175832357-26865e85-ab2e-4397-b0dd-4943bba311fb.png)
