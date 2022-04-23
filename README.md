# SC1015 Data Science Project - Improving your Life Expectancy
![image](https://user-images.githubusercontent.com/95838788/164887057-3989db1c-b1cb-417e-87bf-22728bc5f502.png)

# ❓ About
This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on countries' Life Expectancies from [Kaggle's Life Expectancy Dataset](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who)

# 🔎 Problem Definition
* What should we do to effectively increase the life expectancy of Singapore's population in today's context? 
* What are some main areas of concern to prioritise and tackle in order to become the country with the highest life expectancy globally?

# 💪 Motivation 
* The rate at which Singapore's Life Expectancy is increasing in the past decade has slowed significantly. 
* [Singapore is currently the 5th ranked country globally with a life expectancy of 84.07 years](https://www.worldometers.info/demographics/life-expectancy/)
* By 2025, we hope to see Singapore as the country with the **highest life expectancy of 88 years!**

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
- Obtained a MSE Score of 6.45
</code></pre>

# 💡 Conclusion 
Out of the 3 models, Random Forest regression had the lowest MSE of 3.30.
| Model  | Minimum MSE (2 d.p) |
| ------------- | ------------- |
| SKLearn Multi-Variate Regression with Cross Validation  | 12.63 |
| Random Forest Regression with Cross Validation  | 3.30  |
| Multi-Variate Regression with TensorFlow | 6.45 |

Random Forest Regression may have been more effective due to the <b>size of the dataset</b>. For Deep Networks, <b>a large dataset</b> would be make the model <b>more accurate</b>. However, the dataset which we utilised only had 2578 rows of data and was further split into a 80-20 train-test split. Hence, Random Forest may have performed better than the Deep Learning Model due to this reason.

Furthermore, the Deep Learning Model used a <b>non-linear regression model</b>, and it performed better than the <b>linear regression model</b> from SKLearn, suggesting that the relation between predictor variables and Life Expectancy were <b>not linear</b> to begin with.

From the Random Forest Regression, we identified that Adult Mortality, Income Composition of Resources and Schooling were the most important factors.

With the 3 factors, we made comparisons with the countries with the highest life expectancies as shown below. The blue line represents Singapore's statistics of the 3 variables over the years, while the red line represents the average of each variable for these top countries. 

![Screenshot 2022-04-23 180322](https://user-images.githubusercontent.com/104251224/164889935-7f64cd8e-00f3-44b8-801f-d608872d499b.png)

From Schooling, we can see that Singapore is under average of what the top countries had.

We inputted these variables into our Random Forest model and found that just by slightly increasing schooling, income composition of resources and decreasing adult mortality, there will be improvements in life expectancy with schooling being the most significant.

![image](https://user-images.githubusercontent.com/104251224/164889979-2d861c1b-99e1-4cd6-9dc0-41321e1ecb93.png)

# 🗣️ Recommendations 
Therefore, for Singapore specifically, to improve our life expectancy, we need to prioritise as follows:

1. To increase schooling, Singapore should invest more funds and resources to subsidise citizens’ higher education to increase years of average schooling

2. To increase incomposition of resources, Singapore should strive to achieve a better utilisation of resources (e.g. manpower). This will allow for more efficient allocation of resources to healthcare.

3. To reduce adult mortality rates, Singapore should further improve healthcare services and provide incentives for individuals to lead healthier lifestyles (e.g. Cash rebates for exercising)

Of course, other variables should also be considered when taking into account the big picture, such as Alcohol Intake, GDP Per Capita of the country as well as Polio immunization coverage rates. However, in this analysis, our main purpose was to identify and extract the key points for Singapore to focus on in order to become the country with the highest life expectancy! 😀

# 📚 New Content Learnt
* Deep Learning using TensorFlow and Keras library
* Random Forest Regression
* Various ways to prevent the issue of overfitting (Cross Validation and EarlyStopping in Keras Callbacks)
* Feature Importance using Random Forest
* Git and Github Usage

# 🧑🏽‍🤝‍🧑🏽 Contributors
* [Chong Wei Kang](https://github.com/weikangg): Problem Statement, Motivation, Data Preparation
* [Joel Tan](https://github.com/pluffff): Deep Learning with TensorFlow, Conclusion
* [Sua Qi Rong](https://github.com/Soqoro): EDA, Multi-variate Linear Regression, Random Forest Regression

**However, overall, we helped each other for the whole project and our contributions were not limited to the above.**

# References
* [Kaggle's Life Expectancy Dataset](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who) <br>
* [Singapore Life Expectancy Data for our Motivation](https://tablebuilder.singstat.gov.sg/table/TS/M810501) <br>
* [Regression with TensorFlow](https://www.tensorflow.org/tutorials/keras/regression)
