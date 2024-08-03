# MyInternshipProjects2
# Movie Recommendation System 
This project presents a movie recommendation system using both collaborative filtering and vector search techniques to recommend movies to users. The core dataset consists of 11,506 American movies released between 1970 and 2023, with ratings from 11,675 users. This framework offers personalized recommendations while addressing the cold-start problem through vector search.

screenshot

# Data:
Source:

Movie titles, cast & crew, and year: Self-collected from Wikipedia https://en.wikipedia.org/wiki/Lists_of_American_films.
Movie IDs, genres, and ratings: Collected using The Movie Database API and cleaned (details in 01_Data_Acquisition_and_Cleaning.ipynb).
Datasets:

Movies: /data/movies.csv
Ratings: /data/ratings_cleaned.csv
Preprocessing: Analysis of missing values and outlier handling can be found in 01_Data_Acquisition_and_Cleaning.ipynb.

Exploratory Data Analysis Analyzing the data revealed a highly sparse utility matrix, where a significant portion of users haven't rated many movies. This sparsity can pose challenges for traditional collaborative filtering techniques, as they rely on sufficient user-movie interactions for accurate recommendations.

# Database

Chroma DB, an open-source vector database specifically designed for storing and retrieving vector embeddings.
Implementation:

To integrate vector search into my recommendation system, I followed these steps:
Movie and User Embeddings:
I used the Sentence Transformer model all-MiniLM-L6-v2 to generate vector embeddings for movie features. These embeddings capture the semantic meaning of each entity and allow for similarity comparisons.
You can find the details of this process in notebook 03_Content_Embedding-Cold_Start.ipynb.
Chroma DB Integration:
I stored the generated movie and user embeddings in Chroma DB. This enables efficient retrieval of similar movies based on a user's profile or a target movie (when dealing with cold-start scenarios).
Impact:

By utilizing vector search, I was able to:
Recommend relevant movies to users who haven't rated many movies yet (cold-start problem).
Improve the overall recommendation by considering not only user-movie interactions but also the content similarity between movies.
Mitigate posterior collapse in recommender systems by efficiently retrieving similar items or users based on their embeddings or representations.

# Flask App

Download this repository: Clone or download this repository to your local machine.

Create new environment: Set up a new Python environment using virtualenv or conda to manage dependencies.

Install requirements: Navigate to the root directory of the downloaded repository and install the required packages by running:

pip install -r requirements.txt
Run the Flask app:

Navigate to the root directory.
Run the following command to start the Flask app:
python -m flask --app movies run
This command will launch the Flask app, and you can access it in your web browser at the specified address.

Dataset: You can download it from data folder.

# Thank You
