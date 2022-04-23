# SC1015 Data Science Project - Improving your Life Expectancy
![image](https://user-images.githubusercontent.com/95838788/164887057-3989db1c-b1cb-417e-87bf-22728bc5f502.png)

# ❓ About
This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on countries' Life Expectancies from [Kaggle's Life Expectancy Dataset](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who)

# 🧑🏽‍🤝‍🧑🏽 Contributors
* [Chong Wei Kang](https://github.com/weikangg): Problem Statement, Motivation, Data Preparation
* [Joel Tan](https://github.com/pluffff): Deep Learning with TensorFlow, Conclusion
* [Sua Qi Rong](https://github.com/Soqoro): EDA, Multi-variate Linear Regression, Random Forest Regression

**However, overall, we helped each other for the whole project and our contributions were not limited to the above.**

# 🔎 Problem Definition
* What should we do to effectively increase the life expectancy of Singapore's population in today's context? 
* What are some main areas of concern to prioritise and tackle in order to become the country with the highest life expectancy globally?

# 💪 Motivation 
Our team's main objective was to figure out the main factors that Singapore should zoom in and focus on in order to increase Life Expectancy by a larger rate again.
This is because the rate at which Singapore's Life Expectancy is increasing in the past decade has slowed significantly. To do this, we will make use of a few Machine Learning models first, and identify which Model is the best at predicting Life Expectancy. From there, we will 

# 🚀 Models used
1. Multi-variate Linear Regression (SKLearn)
2. Random Forest Regression (SKLearn)
3. Deep Learning Neural Network (Tensorflow)

# 🚶 Steps we took
**1. Data Preparation** <br>
<pre><code>- Dropping Data: Dropped "Year" and "Country"
- Correcting Variable names: Some were wrongly written and had weird spaces
- Addressing NA Values: Filling NA values with the median of the original data
- Removing outliers: Data points which are +- 1.5 IQR from Q1 and Q3 were considered to be outliers
- Encoding of Category Variables: Label Encoder to encode "Status" into 0 and 1. 0 represents Developed Countries while 1 <br>represents Developing Countries</code></pre>

**2. Data Visualisation & Exploratory Data Analysis** <br>
<pre><code>- Plotted the distribution of all variables using a boxplot, histogram and violinplot for all 20 variables
- Scatterplot of all predictor variables against Life Expectancy
- Ended off by plotting a Heatmap to show the correlation of all variables
</code></pre>

**3. SKLearn Multi-Variate Linear Regression** <br>
<pre><code>- Ran a train-test split of 80-20
- Fitted the model and plotted a scatter plot of Life Expectancy against the predictors
- Obtained an initial MSE score of 13.49
- To deal with issues such as overfitting and selection bias, we made use of 10-Fold Cross Validaton and obtained a final MSE score of 12.63.
</code></pre>

**4. SKLearn Random Forest Regression** <br>
<pre><code>- Again, we ran a train-test split of 80-20
- Made use of GridSearch to determine the best number of estimators from 1 to 101. 
- Obtained best number of estimators as 101.
- Obtained an initial MSE score of 2.85 which seemed too low and suggested the presence of overfitting.
- Thus, we again made use of 10-Fold Cross Validaton and obtained a final MSE score of 3.30.
</code></pre>

**5. Deep Learning Regression using TensorFlow** <br>
<pre><code>- To prepare the data, we had to remove all spaces and replace them with dashes.
- Ran a train-test-split of 80 to 20 and built the model by stacking layers using rectified linear unit as the activation.
- Used Adam’s stochastic gradient descent as the optimizer, and MSE for our loss function.
- Implemented an early stopping function to ensure that our model do not overfit with a patience of 2. 
- Used 512 epochs for our model so that runtime will not be too long.
</code></pre>

# 💡 Conclusion & Recommendations


# 📚 New Content Learnt
* Deep Learning using TensorFlow and Keras library
* Random Forest Regression
* Various ways to prevent the issue of overfitting (Cross Validation and EarlyStopping in Keras Callbacks)
* Feature Importance using Random Forest
* Git and Github Usage

# References
* [Kaggle's Life Expectancy Dataset](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who) <br>
* [Singapore Life Expectancy Data for our Motivation](https://tablebuilder.singstat.gov.sg/table/TS/M810501) <br>
* [Regression with TensorFlow](https://www.tensorflow.org/tutorials/keras/regression)
