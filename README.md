# Movie-Recommendation-Model
This repository contains a Jupyter Notebook that builds a user-based collaborative filtering recommendation system. The project uses the classic MovieLens 100k dataset to recommend movies to users based on the ratings of similar users.

## 📋 Table of Contents

- Project Overview

- Dataset

- Methodology

- Performance Evaluation

- How to Run

- Requirements

## 🚀 Project Overview <a name="project-overview"></a>

The goal of this project is to create a recommendation engine that suggests movies to a user based on their similarity to other users. This is a fundamental concept in building personalized experiences.

The notebook demonstrates a complete data science workflow:

1- Data Loading and Exploration: Understanding the structure and characteristics of the user, movie, and ratings data.

2- Exploratory Data Analysis (EDA): Visualizing key aspects of the dataset, such as rating distributions, movie popularity, user demographics, and genre popularity.

3- Model Building: Implementing a user-based collaborative filtering algorithm from scratch using Pandas and Scikit-Learn.

4- Recommendation Generation: Creating a function to generate a ranked list of movie recommendations for a specific user.

5- Evaluation: Measuring the model's performance using the Precision@K metric on a predefined test set.

## 💾 Dataset <a name="dataset"></a>

This project uses the MovieLens 100k Dataset, a widely-used benchmark dataset in the recommender systems community. It was collected by the GroupLens Research Project at the University of Minnesota.

The dataset consists of:

- 100,000 ratings from 943 users on 1682 movies.

- Each user has rated at least 20 movies.

- Demographic info for the users (age, gender, occupation).

- Movie information including title, release date, and genres.

You can find the dataset on [kaggle](https://www.kaggle.com/datasets/prajitdatta/movielens-100k-dataset)

## 🛠️ Methodology <a name="methodology"></a>

The core of this project is the implementation of user-based collaborative filtering. The logic is as follows:

1- Create a User-Item Matrix: A matrix is constructed with users as rows, movies as columns, and the ratings as the values. This matrix is sparse, as not every user has rated every movie.

2- Calculate User Similarity: The similarity between users is computed using the cosine similarity metric. This measures the cosine of the angle between two user-rating vectors, providing a score of how similar their tastes are.

3- Generate Recommendations:

 - For a target user, we identify other users who are most similar.

 - We then look at the movies that these similar users have rated highly (e.g., 4 or 5 stars).

 - Movies that the target user has not yet seen are collected and ranked based on a weighted score (similarity score * rating).

The top N movies are returned as the final recommendations.

## 📊 Performance Evaluation <a name="performance-evaluation"></a>

To assess the quality of the recommendations, the model was evaluated using Precision at K (Precision@K). This metric measures the proportion of recommended items in the top-K set that are actually relevant.

- Relevant Item: A movie is considered relevant if the user rated it 4 or 5 stars in the test set.

- K: The number of recommendations to consider (set to 10 for this project).

The model achieved an Average Precision@K of 0.2971. This means that, on average, nearly 3 out of the 10 movies recommended to a user were relevant and liked by them.

## 💻 How to Run <a name="how-to-run"></a>

1- Clone the repository:

<div class="command-block">
<pre>git clone https://github.com/your-username/movie-recommendation-system.git</pre>
</div>
<div class="command-block">
<pre>cd movie-recommendation-system</pre>
</div>

2- Create a virtual environment (recommended):

<div class="command-block">
<pre>python -m venv venv</pre>
</div>
<div class="command-block">
<pre>source venv/bin/activate  # On Windows, use venv\Scripts\activate</pre>
</div>

3- Install the required packages:

<div class="command-block">
<pre>pip install -r requirements.txt</pre>
</div>

4- Launch Jupyter Notebook:

<div class="command-block">
<pre>jupyter notebook</pre>
</div>

5- Open the movie-recommendation-system.ipynb notebook and run the cells.

## 📦 Requirements <a name="requirements"></a>

The project requires the following Python libraries. You can install them using the requirements.txt file.

<div class="command-block">
<pre>pandas
numpy
matplotlib
seaborn
scikit-learn</pre>
</div>
