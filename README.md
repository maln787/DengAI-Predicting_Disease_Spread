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

#### i) Understanding the data

To understand the data and the features than can be most useful, I first read few papers and articles. This helped me understand the problem in more depth and what can help me in building the model.

#### ii) Cleaning the data / Engineering the features

I first looked at the null values and found that there were very few null values in the dataset. Since the data is continuos, also the data points are of weather and vegetation index, it is highly unlikely that the vegetation changes drastically next week or if summers are going are the temperature is almost going to be same the next week. Therefore, I imputed the null values with forward fill method which fills the current null value with previous value.

After I filled the null values I checked the features and their correlation with each other. I first created average of reanalysis and ndvi (vegetation index) as the features associated with these are highly correlated with each other. Then I dropped the columns used to create these two new features.

Then, I looked again at the correlation of the features remaining and dropped the features having high multicollinearity, as this is not going to add much information in the modeling and even make model more complex.

#### iii) 

Initially I had a training labels dataset and in that we seperated the dataframe by two regions 


(Provide more detailed overview of the project.  Talk a bit about your data sources and what questions and hypothesis you are exploring. What specific data analysis/visualization and modelling work are you using to solve the problem? What blockers and challenges are you facing?  Feel free to number or bullet point things here)

### Needs of this project

An understanding of the relationship between climate and dengue dynamics can improve research initiatives and resource allocation to help fight life-threatening pandemics.

## Contact
[(Back to table of contents)](#table-of-contents)

* Feel free to contact me with any questions or if you want to understand any concepts. (www.nikunjmalpani.com)
