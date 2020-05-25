# Capstone Project

## Perfume Ratings

*Worked by Kalina Zeligowska Serej*

***

The aim of this project was to create a statisctical model making predictions on perfumes ratings.

I used the data from fragrantica.com - a popular internet portal for fragrances' lovers. Exploring users preferences and interests alowed me to get a deep understanding of the perfumes rating system.

Utilising this kind of prediction, can help to create better communication between manufactures, sellers and customers, especially those who are present on the online market.

***

If you are interested in this project and would like to discuss its details, please contact me directly at:
* <p><a href="mailto:kalina.zeligowska@gmail.com">kalina.zeligowska@gmail.com</a></p>

*** 

## Table of Contents

1. <a href="https://github.com/kalina-kalina/perfumes_ratings#1-file-descriptions" target="_blank">File descriptions</a>

2. <a href="https://github.com/kalina-kalina/perfumes_ratings#2-technologies-used" target="_blank">Technologies Used</a>

3. <a href="https://github.com/kalina-kalina/perfumes_ratings#3-executive-summary" target="_blank">Execiutive Summary</a>

4. <a href="https://github.com/kalina-kalina/perfumes_ratings#4-more-information" target="_blank">More Informations</a>

* <a href="https://github.com/kalina-kalina/perfumes_ratings#how-does-the-rating-system-work" target="_blank">How does the Rating System work</a>

* <a href="https://github.com/kalina-kalina/perfumes_ratings#most-important-steps-in-cleaning-preparing-and-engineering-notebook" target="_blank">Most important steps from Cleaning, preparing and engineering</a>

* <a href="https://github.com/kalina-kalina/perfumes_ratings#most-important-steps-in-data-splitting-and-modelling-notebook" target="_blank">Most important steps from Modelling</a>

5. <a href="https://github.com/kalina-kalina/perfumes_ratings#5-possible-improvements-and-future-work" target="_blank">Possible improvements and future work</a>

***

### 1. File descriptions

* <a href="01 - Cleaning, preparing and engineering.ipynb" target="_blank">01 - Cleaning, preparing and engineering.ipynb</a>: notebook with data exploration, data cleaning and data preprocessing
* <a href="02 - Data Splitting and Modelling.ipynb" target="_blank">02 - Modelling.ipynb</a>: notebook with data modelling
* Checklist.md: checklist of work on the project
* <a href="README.md" target="_blank">README.md</a>: readme file
* <a href="perfume.csv" target="_blank">perfume.csv</a>: dataset from kaagle.com
* <a href="presentation-pdf.pdf" target="_blank">presentation-pdf.pdf</a>: short presentation (non-technical)
* <a href="ready.csv" target="_blank">ready.csv</a>: cleand and ready for modelling dataset
* start.ipynb: copy of code, will be removed after finishing work

***

### 2. Technologies Used

* Python
* Pandas
* Seaborn
* Matplotlib
* Numpy
* Scikit-learn

***

### 3. Executive Summary


The dataset which I worked on includes information scraped off fragrantica.com.

Fragrantica.com is a portal for perfume lovers. Is consists of three main segments - a catalogue of perfumes, an independent magazine on this subject and a community - users who comment, discuss and assess perfumes.

I took the dataset from <a href="https://www.kaggle.com/sagikeren88/fragrances-and-perfumes" target="_blank">kaggle.com</a> as a ready-to-use csv file.

My code is split into separated notebooks to keep is as clear and readable as possible.

The steps of my project are the following:

1. Cleaning, preparing and engineering: <a href="01 - Cleaning, preparing and engineering.ipynb" target="_blank">notebook</a>

The biggest issues:
* correctly understanding the data and the way it was collected
* unifying all variables
* deciding which variables are valuable
* creating new, valuable features

2. Data Splitting and Modelling: <a href="02 - Data Splitting and Modelling.ipynb" target="_blank">notebook</a>

The biggest issues:
* models understanding 
* models' measures understanding

*** 

### 4. More Information

### How does the rating system work:

Each bottle of fragrance is described by several parameters (according columns of the dataset):
* basic information: title, brand, year of market launch
* accords - main elements/ingredients of a fragrance

> Accords for perfumes are the same as ingredients for meals, colours for paintings or notes/sounds for music. 
>
> Top 15 most common accords: 
>
> woody, citrus, floral, sweet, aromatic, fresh spicy, fruity, white floral, balsamic, powdery, green, warm spicy, musky, vanilla, rose.

* rating_score - mean value of users votes
* votes - the number of votes submitted by users
* perfume's longevity: poor, weak, moderate, long or very long
* perfume's sillage: soft, moderate, heavy or enormous
* user's preferences (also split into sex and age categories): love/like/dislike, for winter, spring, summer or autumn, cold or hot day, day or night, I have/had or want it
* more details about accords
* target group: women, man or unisex 

![](figures/from_web.png)

> Images taken from [fragrantica.com](https://www.fragrantica.com/perfume/Chlo-/Love-Story-26227.htmll)

When users vote for a given perfume, it's not required to mark each aspect. Unfortunatelly, it couses an inbalance in ratings (the number of grades for each column does not have to be correlated with the general number of votes).


### Most important steps in Cleaning, preparing and engineering <a href="01 - Cleaning, preparing and engineering.ipynb" target="_blank">notebook</a>:

1. Small amount of votes

While exploring the data, it emerged that distribiuton of 'rating_score' variable is disrupted by products with a
low numer of votes. The less votes, the more likely the value of 'rating_score' is an integer number. After removing perfumes with less than 20 votes, distribiution has improved.

![](figures/distribution.png)

2. Messy 'accords' column. 

In each cell of this column there was a set of accords labels, interrupted by labels such as 'Videos' and 'Pictures' (these two labels are the result of web scrapping). I decided to split all of them into separeted columns, remove worthless labels, create new columns for each of the accords and fill them with 0 (when a perfume doesn't have this accord) and 1 (when a perfume has this accord).

3. Longevity and Sillage

Because of an imbalance in ratings, these two features were difficult to understand. I calculated weighted aritmetical mean for each of them to make them easier to compare.

4. Season

Also here, because of an imbalance in ratings, season's features were difficult to compare. I decided to present them as a ratio of the number of votes for specific season to the sum of votes for all seasons.

### Most important steps in Data Splitting and Modelling <a href="02 - Data Splitting and Modelling.ipynb" target="_blank">notebook</a>:

1. Data scaling

Not every feature from the dataset had the same range of values. I scaled three of them: 'votes', 'longevity' and 'sillage' using MinMaxScaler from Scikit-learn library. 

2. Checking multicolinearity

There was multicolinearity between season's and gender's variables. It could mean that users voting for winter, voted for autumn as well. And those voting for summer, voted for spring as well. After removing 'autumn' and 'spring', there are no issues with multicolinearity between this group of variables. I decided to leave the variables which are more obviously and therefore easier to unterstand. Now, season is split between hot(summer) and cold(winter).
I had the same issue with gender_man and gender_unisex. After removing gender_man, there is no issue with multicolinearity.

3. Models' understanding

From comparing the R-squared values of the test and train data sets it was found that Ridge regression performed best. All values are very, very low - it's not what I expected before I starting my porject.
Low measures mean that a set of independent variables, in this form, for linear regression models, in not enough to predict dependent variable. The final model explains only about 9% of training set and 8% of validation set. 

***

### 5. Possible improvements and future work

My data proved to be difficult to understand. My starting idea for building linear regression model wasn't correct.

I assume that working on feature engineering can be good step to extend the project.

My plan is combine some of features into groups to discrease number of independent variables and add some new to improve performance of the model.

Examples of new information:
* perfume's price
* common capacity
* price per 100 ml
* popularity and worldwide availability.
