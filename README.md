# Capstone Project

## Perfume Ratings

*Worked by Kalina Zeligowska Serej*

***

The aim of this project was to create a statisctical model making predictions on perfumes ratings.

I based on the data from fragrantica.com - a popular internet portal for fragrance's lovers. Exploring users preferences and interests alowed me to get a deep understanding of the perfumes rating system.

Utilising this kind of prediction, can help to create better communication between manufactures, sellers/dealers (?) and customers, especially those who exist on the online market. (?)

***

If you are interested with this project and would like to discuss its details, please contact me directly on the following:
* [kalina.zeligowska@gmail.com]()

*** 

### Executive Summary


The dataset, what I worked on, includes the informations scraped off of the fragrantica.com website.

Fragrantica.com is a portal for perfume lovers. Is has three main fillars - an catalogue, an independent magazine and a community - users who comment, disscuse and assess perfumes.
Each bottle of fragrance JAK JEST OCENIANA

I took the dataset from <a href="https://www.kaggle.com/sagikeren88/fragrances-and-perfumes" target="_blank">kaggle.com</a> as a ready-to-use csv file.

My code is split into separated notebooks to keep is as clear and readable as possible.

(tu są kolejne pliki i główne punkty)


1. <a href="https://github.com/kalina-kalina/perfumes_ratings/blob/master/01%20-%20Data%20cleaning%20and%20preparation.ipynb" target="_blank">Data cleaning and preparing</a>

* the biggest issue - a correct understanding the data and the way it was collected
* doprowadzić do ujednoliconego typu
* poradzenie sobie z danymi które zakłócały arkusz - mała ilość głosów
* zdecydowanie które kolumny są istotne
* zmienna accords - very messy

2. <a href="https://github.com/kalina-kalina/perfumes_ratings/blob/master/02%20-%20Modelling.ipynb" target="_blank">Modelling</a>

* ujednolicenie skal zmiennych
* checking a multicolinearity and deciding which of higly correlated variables remove
* spliting the data to prepare if for moddeling
* linear regrassion model

3. "TO BE CONTINUATED"

*** 

Third, you then write what you did on the project that is a bit more technical.
Here you might say that you took data from [here and make it a link to the original data]() and then ran `a list of models you ran here` in your analysis.
Then end with one sentence that picks what your best model was and how it performed.

Lastly, you say in one or two sentences why this matters. 
For example, now as opposed to before this data analysis, you can now predict X better than Y. 

The goal of this project was to create a `regression/classification` model that was able to predict `what you set out to do`.

> If you are able to swap out the text here with what your case example is you will demonstrate the following:
> 1. You get why what you're doing 'matters'
> 2. You are able to take ill defined problems and turn them into something a data scienst can solve
> 3. You show off your analystical and modeling chops.
> 4. You are able to communicate technical things you do.

### More Information

Each bottle of fragrance is described of several parameters (according columns of the dataset):
* basic information such as: title, brand, year of (wprowadzenia na rynek)
* accords - main elements/ingredients of a fragrance

Accords for perfumes are the same as ingredients for meals, colours for paintings or notes/sounds for music. Top 10 most common accords: 
woody, citrus, floral, sweet, aromatic, fresh spicy, fruity, white floral, balsamic, powdery, green, warm spicy, musky, vanilla, rose.

* rating_score - mean value of users votes
* votes - the number of votes submitted by users
* perfume's longevity: poor, weak, moderate, long or very long
* perfume's sillage: soft, moderate, heavy or enormous
* user's preferences (also split into sex and age categories): love/like/dislike, for winter, spring, summer or autumn, cold or hot day, day or night, have/had/want- more details about accords
* target group: women, man or unisex 

Below your Executive Summary, you can document whatever you feel would be of interest to a future employer.
Here I would especially suggest diving a bit deeper into your methodology and including images that you are proud of from the project. 
Remember, that people will probably judge your github project page within 45 seconds tops, you want it to look as clean as possible. 

Write documentation that looks like someone you would want to work with.

### Show Off Your Data Viz

![Everyone Likes a Pairplot](figures/seaborn-pairplot-3.png)

> Image taken from `seaborn` [documentation](https://seaborn.pydata.org/generated/seaborn.pairplot.html)
