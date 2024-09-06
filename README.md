<h1>Movie Recommendation System</h1>
Overview
This project implements a movie recommendation system based on the content of the movies using various attributes such as genres, keywords, cast, crew, and overview. The recommendation system uses the cosine similarity between movies to suggest similar ones.

Dependencies
Before running the code, ensure you have the following dependencies installed:

numpy
pandas
nltk
scikit-learn
You can install the required packages using pip:

bash
Copy code
pip install numpy pandas nltk scikit-learn
Data Files
The code requires two CSV files:

tmdb_5000_movies.csv - Contains movie metadata.
tmdb_5000_credits.csv - Contains movie cast and crew information.
Ensure these files are in the same directory as the script or adjust the file paths accordingly.

Code Explanation
Data Loading and Merging:

The movies and credits datasets are loaded into Pandas DataFrames.
The two DataFrames are merged on the title column.
Data Processing:

Selected columns are kept for the recommendation system: movie_id, title, overview, genres, keywords, cast, and crew.
Missing values are removed, and any duplicate entries are dropped.
genres, keywords, cast, and crew columns are transformed from JSON strings into lists of relevant names.
Text Processing:

The overview column is split into individual words.
All text fields are stripped of spaces.
A tags column is created by concatenating overview, genres, keywords, cast, and crew.
Text is converted to lowercase, and stemming is applied using PorterStemmer to reduce words to their base form.
Vectorization and Similarity Computation:

CountVectorizer is used to convert text data into numerical vectors.
Cosine similarity is calculated to find similarity between movies based on their tags.
Recommendation Function:

A recommend function is defined to return the top 5 similar movies to a given movie based on cosine similarity.
Usage
Run the Script: Ensure all dependencies are installed and data files are available. Run the script to execute the recommendation system.

Call the Recommendation Function: Use the recommend function to get movie recommendations. For example:

python
Copy code
recommend('Batman Begins')
This will print the top 5 movies similar to "Batman Begins" based on content similarity.

Example Output
plaintext
Copy code
The Dark Knight
Inception
Interstellar
Memento
The Prestige
Troubleshooting
Ensure that the CSV files are correctly formatted and located in the expected directory.
Check for missing dependencies or import errors and install them using pip.
If there are issues with the recommendation function, verify that the movie title exists in the dataset.
License
This project is licensed under the MIT License. See the LICENSE file for details.

