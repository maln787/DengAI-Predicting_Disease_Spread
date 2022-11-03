# DengAI-Predicting_Disease_Spread
This project is a part of the takehome assessment for the role of Data Scientist at **Constellation** (https://www.helloconstellation.com/). DengAI: Predicting Disease Spread is a online challenge hosted by **DrivenData**.

### Project Status: [Active/ Continually improving]

## Table of contents
* [Project Introduction-Objective](#project-introduction-objective)
* [Methods Used](#methods-used)
* [Technologies](#technologies)
* [Project Description](#project-description)
    + [Data Sources](#data-sources)
    + [Approach](#approach)
    + [Needs of this project](#needs-of-this-project)
* [Contact](#contact)


## Project Introduction-Objective
[(Back to table of contents)](#table-of-contents)

Can you predict local epidemics of dengue fever?

Dengue fever is a mosquito-borne disease that occurs in tropical and sub-tropical parts of the world. In mild cases, symptoms are similar to the flu: fever, rash, and muscle and joint pain. In severe cases, dengue fever can cause severe bleeding, low blood pressure, and even death.

Because it is carried by mosquitoes, the transmission dynamics of dengue are related to climate variables such as temperature and precipitation. Although the relationship to climate is complex, a growing number of scientists argue that climate change is likely to produce distributional shifts that will have significant public health implications worldwide.

My task is to predict the number of dengue cases each week (in each location) based on environmental variables describing changes in temperature, precipitation, vegetation, and more.

An understanding of the relationship between climate and dengue dynamics can improve research initiatives and resource allocation to help fight life-threatening pandemics.

## Methods Used
[(Back to table of contents)](#table-of-contents)

* Data Cleaning
* Exploratory Data Analysis
* Data Visualization
* Feature Selection
* Modeling (Random Forest / XGBoost / GridSearchCV / Hyperparameter Tuning)
* Time Series Forecasting (Prophet)

## Technologies
[(Back to table of contents)](#table-of-contents)

* Python
* Pandas, jupyter

## Project Description
[(Back to table of contents)](#table-of-contents)


### Data Sources

We are using the environmental data collected by various U.S. Federal Government agencies—from the Centers for Disease Control and Prevention to the National Oceanic and Atmospheric Administration in the U.S. Department of Commerce for cities San Juan, Puerto Rico and Iquitos, Peru.

### Approach

### i) Understanding the data

To understand the data and the features than can be most useful, I first read few papers and articles. This helped me understand the problem in more depth and what can help me in building the model.

### ii) Cleaning the data / Engineering the features

I first looked at the null values and found that there were very few null values in the dataset. Since the data is continuos, also the data points are of weather and vegetation index, it is highly unlikely that the vegetation changes drastically next week or if summers are going are the temperature is almost going to be same the next week. Therefore, I imputed the null values with forward fill method which fills the current null value with previous value.

After I filled the null values I checked the features and their correlation with each other. I first created average of reanalysis and ndvi (vegetation index) as the features associated with these are highly correlated with each other. Then I dropped the columns used to create these two new features.

Then, I looked again at the correlation of the features remaining and dropped the features having high multicollinearity, as this is not going to add much information in the modeling and even make model more complex.

### iii) Modeling

#### Part a)

Initially, I had a training labels dataset and in that I seperated the dataframe by two regions San Juan and Iquitos. I did this because we can see that different regions can have certain characteristics that can influence different number of cases like weather of a place or how much vegetation is there or damp water because of it, etc.

In the first part of the modeling, I took all the remaining features and trained the model by Decision Tree Algorithm, and then Random Forest Regressor. I split the data 80:20 into train:test split and then measured the mean absolute error of the test set. One key point to note here would be to keep the random seed because if not then every time we split randomly the results are going to change.

#### Part b)

In the next part, I standardized the data and applied GridSearchCV to Random Forest as it was performing the best amongst other regressors. I also applied dimensionality reduction techniques like PCA to find the MAE with all the algorithms mentioned above. In addition to this, I checked the correlation of different features with our target variable which is total cases and also selected only important features to find the better fit of the model. GridSearchCV helped a bit but we need to improve the MAE score more.

#### Part c)

Next, I applied the time series model to forecast the total cases and use them as predictions for our test set. I used Prophet with hyperparameter tuning and taking different set of features and with different seasonal cycles to find the best fit of features and seasonal cycle. I used select k-best method with chi squared and f_regression function to find the important k features and then I used them as my regressors in the time series model. MAE score impoved by this.

Below is the table of the results that I found by different algorithms in their best settings, I have not incorporated the results with each and every setting that I tried with the models, but you can find more in the python files in this github repository.

<img width="580" alt="Screen Shot 2022-11-03 at 1 06 19 AM" src="https://user-images.githubusercontent.com/44938585/199651234-6224b064-80e6-4b0d-ba30-e8f956a1b750.png">


### Files consisting names and path


(Provide more detailed overview of the project.  Talk a bit about your data sources and what questions and hypothesis you are exploring. What specific data analysis/visualization and modelling work are you using to solve the problem? What blockers and challenges are you facing?  Feel free to number or bullet point things here)

### Needs of this project

An understanding of the relationship between climate and dengue dynamics can improve research initiatives and resource allocation to help fight life-threatening pandemics.

## Contact
[(Back to table of contents)](#table-of-contents)

* Feel free to contact me with any questions or if you want to understand any concepts. (www.nikunjmalpani.com)
