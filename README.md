# Weather-Impact-on-Depart-Delay-Imbalanced-Dataset-

When I was doing my final project of the Predictive Analytics course at Washington University in St. Louis. My teammates and I decided to conduct our research regarding Weather Impact on Departure Delay at O’Hare International Airport (ORD) using Python. 

Firstly, we collected flight data and weather data from two different websites. The flight data is retrieved from the Bureau of Transportation Statistics (https://www.transtats.bts.gov). Weather data is retrieved from Iowa State University (https://mesonet.agron.iastate.edu/request/download.phtml?network=NY_ASOS).We utilized the “time” variable as a key to create one-to-one correspondence between weather (temperature/ humidity/ wind/ precipitation/ visibility/ pressure) and departure delay condition. After visualizing the distribution of departure delay, we found that we had 97% non-delay, 3% of delay (including 2% mild delay, and 1% severe delay) which aroused an imbalanced dataset problem.  

To deal with such a problem, we employed two methods: undersampling the majority class and  enriching the model structure to two layers. The undersampling the majority class approach was randomly removing some observations of the non-delay class which would efficiently increase the proportion of the delay class and decrease the proportion of non-delay class and mitigate the imbalanced dataset problem. While the two-layer modeling framework means in the first layer of the model we merely classify whether it’s a delay or non-delay, in the second layer, for those cases predicted as delay in the first layer, we further classify it as non-delay, mild delay, and severe delay. It’s easy to understand that input of the second layer would be less imbalanced, therefore, the whole model would do better work in identify non-delay cases. 

Imagine this framework is as a factory, the models employed in each layer would be various machines that enable the factory to function and produce.  We tried three combinations of models which were Logistic Regression model (only for layer 1), Random Forest model (both for layer 1 and 2), and XGBoost model (both for layer 1 and 2).

The result turned out that the XGBoost model performed better than the other two models for both layer 1 and layer 2. With the XGBoost model, Our model achieved 0.93 weighted average f1-score on the testing dataset.

In addition, according to the analysis results of Random forest and logistic regression, Air Temperature, pressure, and humidity are important predictive variables for the flight delay.
