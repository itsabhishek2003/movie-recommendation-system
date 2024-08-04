### GitHub README for Movie Recommender System

# Movie Recommender System

This project is a movie recommender system built using the TMDB 6000 dataset from Kaggle. The system recommends movies based on user input, leveraging text preprocessing techniques and a cosine similarity algorithm to find and suggest similar movies. The project is divided into two main components: the backend for data processing and machine learning, and the frontend for user interaction using Streamlit.

## Project Structure

- `movie_recommender_system.ipynb`: Jupyter Notebook for data preprocessing, feature extraction, and model building.
- `app.py`: Streamlit application for the frontend, providing an interactive user interface for movie recommendations.

## Data Preprocessing and Feature Extraction

### Loading and Cleaning the Dataset
The TMDB 6000 dataset from Kaggle is loaded and cleaned to remove any inconsistencies and missing values. The dataset contains information about movies, including their titles, genres, and descriptions.

### Combining Features
To create a comprehensive 'tags' column for each movie, relevant features such as genres, keywords, cast, and crew are combined into a single string. This helps in capturing the essential aspects of each movie for better similarity measurement.

### Text Preprocessing
Basic text preprocessing techniques are applied to the text data. This includes:
- Tokenization: Splitting text into individual words or tokens.
- Lemmatization: Reducing words to their base or root form.
- Removal of stop words: Eliminating common words that do not contribute to the meaning, such as 'and', 'the', etc.

### Bag of Words Vectorization
The Bag of Words (BoW) approach is used to convert the textual data into numerical vectors. The CountVectorizer from scikit-learn is employed, which counts the frequency of words in each document. This method helps in understanding the importance of words in the dataset. The vectorized data is then used to calculate the similarity between movies.

## Building the Recommender System

### Cosine Similarity
Cosine similarity is computed between the vectors to measure the similarity between movies. The similarity score helps in identifying movies that are closely related to the input movie.

### Recommendation Function
A recommendation function is created to suggest movies based on the similarity scores. This function takes a movie title as input and returns a list of recommended movies along with their posters.

### Exporting Data
The processed data and similarity matrix are exported using the `pickle` module. These files (`movies_dict.pkl` and `similarity.pkl`) are used in the Streamlit frontend to provide real-time recommendations.

## Streamlit Frontend

### User Interface
The Streamlit application (`app.py`) provides an interactive user interface where users can select a movie from a dropdown list and get recommendations for similar movies.

### Fetching Movie Posters
The TMDB API is used to fetch and display movie posters for the recommended movies. This enhances the user experience by providing a visual representation of the recommendations.

### Recommendation Display
Upon selecting a movie and clicking the "Show Recommendation" button, the application displays the recommended movie names and their posters in a visually appealing layout.

## How to Run

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd movie-recommender-system
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the Streamlit application:
   ```bash
   streamlit run app.py
   ```

## Conclusion

This movie recommender system leverages text preprocessing techniques and cosine similarity to provide accurate movie recommendations based on user input. The combination of a robust backend and an interactive frontend makes this project a comprehensive solution for movie recommendations.

Feel free to explore the code and provide feedback or suggestions for improvement!

---
