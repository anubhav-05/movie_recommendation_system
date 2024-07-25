# Movie Recommendation System

This repository contains the code for a movie recommendation system built using Streamlit. The system allows users to select a movie from a dropdown menu and get recommendations for similar movies along with their posters.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Data Preparation](#data-preparation)
- [Streamlit App](#streamlit-app)
- [Contributing](#contributing)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/anubhav-05/movie_recommendation_system.git
   cd movie_recommendation_system

2.**Create a virtual environment:**
   ```bash
   python -m venv venv

3.**Activate the virtual environment:**

On Windows:

   venv\Scripts\activate

On macOS/Linux:

   source venv/bin/activate

4.**Install the required packages:**

   pip install -r requirements.txt


## Usage
1.**Prepare the data:**

Run the Jupyter Notebook to preprocess the data and create the necessary pickle files (movie_list.pkl and similarity.pkl).

2.**Run the Streamlit app:**

   streamlit run app.py

3.**Interact with the app:**

Select a movie from the dropdown menu.

Click on the 'Show Recommendation' button to view similar movies along with their posters.

## Data Preparation

The data preparation is done in a Jupyter Notebook. Here are the steps involved:

1.**Load the data:**

Read the movie and credits data from CSV files.

2.**Merge the datasets:**

Merge the movies and credits datasets on the 'title' column.

3.**Select relevant columns:**

Keep only the necessary columns: 'movie_id', 'title', 'overview', 'genres', 'keywords', 'cast', 'crew'.

4.**Handle missing values:**

Drop rows with missing values.

5.**Convert JSON columns:**

Convert the 'genres', 'keywords', 'cast', and 'crew' columns from JSON strings to lists.

6.**Process text columns:**

Stem the words in the 'tags' column using NLTK's PorterStemmer.

7.**Vectorize the text:**

Use CountVectorizer to convert the 'tags' column into a matrix of token counts.

8.**Compute similarity:**

Calculate the cosine similarity between the vectors.

9.**Save the processed data:**

Save the processed data and similarity matrix as pickle files.

## Streamlit App

The Streamlit app (app.py) does the following:

1.**Fetch movie posters:**

Use the TMDB API to fetch movie posters based on the movie ID.

2.**Load data:**

Load the processed data and similarity matrix from the pickle files.

3.**Recommend movies:**

Implement a recommendation function to find the top 5 similar movies.

4.**Build the Streamlit interface:**

Create a dropdown menu for movie selection.

Display the recommended movies and their posters in a horizontal layout.

## Contributing
Contributions are welcome! If you have any suggestions or improvements, feel free to create a pull request or open an issue.
