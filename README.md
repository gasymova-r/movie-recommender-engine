# movie-recommender-engine
Program outputting 10 movie recommendations based on previous preferences


### About
This project explores content-based and collaborative recommendation algorithms on the example of movie recommenders. The final result is an interactive program that allows users to get personalized recommendations using Singular Value Decomposition (SVD). The approach was chosen with cross-validation using a Python library [Surprise](https://surpriselib.com).

### How it works
The main upside of the final program is that it allows flexibility – getting recommendations not only for the users already existing in the dataset, but personalized output based on any user’s input. The program works on a sample of 1,000,000 observations from the original dataset and relies on three major functions:

1.	Function for getting a random movie from the dataset – returns a random movie title.
2.	Function for creating a new user – adds observations for a new user to the sample dataset. Takes on a new user ID as an argument (calculated as the maximum ID in the current sample plus one). The function uses a WHILE loop and calls the function #1 on this list to generate random movies and ask the new user to rate them. After a new user has rated a specific number of movies (in the sample code we used 5 ratings, but it should be higher for better accuracy), they can receive and view their new ID.
3.	Function for making recommendations – fits the SVD model to make predictions. Takes on user ID as an argument and outputs a list of 10 movies. Each movie in the list has its estimated score showing the prediction of the model regarding what score a user would give a movie in the list if they have watched it.

The program itself is an infinite WHILE loop which we break out of upon getting the recommendations. When we run the program, we will essentially see two options:
1.	If we would like to get personalized recommendations as a new user – meaning someone who is not in the original dataset – we will trigger function #2 from the list creating a new user and adding them to a sample dataset.
2.	If we would like to get recommendations for someone already present in the dataset (this includes a new user if we already went through step #1), we input the user ID and trigger the function #3 to receive recommendations.

### Example

### Set up
For the purposes of this project, we worked with the [MovieLens dataset](https://grouplens.org/datasets/movielens/), which was made specifically for testing and learning about movie recommendation algorithms. The website has multiple dataset options to choose from. The version used in this project utilizes the most extensive dataset which includes 25 million ratings of around 62,000 movies applied by 162,000 users across multiple years.

In order to test the code, you need to download the dataset and add it to the project folder.
