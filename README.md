# Netflix Challenge
Side project where I try to build a recommender engine. Data is from the Netflix Prize and can be downloaded from Kaggle (see `data` folder for more information). 

# Goal
The main goal is creating an algorithm to **predict user ratings** for different movies. 

# Methods
Data was manipulated using Python (Pandas, NumPy) in Jupyter Notebook. Because of the massive size of this dataset, only about half the data was used to build the recommender. 

Once data was processed, the Surprise package was used to predict the ratings given by different users. 

# Data Exploration and Processing
Even years after the original Netflix Prize, this dataset can still be considered really large and there are issues associated with handling this amount of data - processes take longer to run, and the computer may not have enough memory to handle all the data. For those reasons, only the `combined_data_1.txt` and `combined_data_2.txt` files were parsed. 

The figure below gives an idea of the size of the dataset. Using the two data files mentioned previously, there are 9,210 movies, 478,018 unique customers, and 51,031,355 ratings. From this figure, we can also notice that the rating distribution is not normal. A possible explanation for this is that people are not interested in watching a movie with bad reviews/ratings, so consequently fewer low ratings are given. 

![Rating distribution across whole dataset](saves/images/rating_distrib.png)

Another aspect we can consider is how many ratings a given movie has received. This is shown in the image below. For readability, 

!![Rating count per movie](saves/images/rating_permovie_distrib.png)

To try and make the dataset more manageable, we follow two different approaches:
* Filter out movies that have been reviewed very few times
* Filter out users that have given very few ratings 