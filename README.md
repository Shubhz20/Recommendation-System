# Simple Movie Recommendation System

## What is this?

This is a program that suggests movies you might like based on a movie you already enjoy. It's like having a friend who knows your taste in movies and says, "If you liked _that_ one, you'll love _this_ one because they are both about space travel and have funny robots."

## How does it work? (The Simple Explanation)

This system uses **Content-Based Filtering**. Here is the step-by-step process:

1.  **Reading the Movie**: It reads the details of every movie in our list, specifically looking at:
    - **Genre** (e.g., Comedy, Action)
    - **Tags** (keywords describing the movie)
    - **Summary** (the plot)

2.  **Creating a "Fingerprint"**: It combines all these details into a single text description for each movie. Then, it turns this text into a list of numbers (a "vector") that the computer can understand. This involves counting distinct words.

3.  **Comparing Movies**: To find recommendations, it compares the "fingerprint" of the movie you chose with the "fingerprint" of every other movie in the database.

4.  **Finding Matches**: It calculates a similarity score (using math called **Cosine Similarity**) to see how close two movies are. A score of 1 means they are identical, while 0 means they are completely different.

5.  **The Result**: It sorts the movies by their similarity score and lists the top 10 movies that are most similar to your choice.

## Technical Details

- **Libraries Used**:
  - `pandas`: To handle the data table.
  - `scikit-learn`: For turning text into numbers (`CountVectorizer`) and calculating similarity (`cosine_similarity`).
  - `nltk`: For processing natural language (like removing common words).
- **Method**: Bag of Words model using `CountVectorizer`.

## How to Run It

1.  **Prerequisites**: You need Python installed along with the following libraries:
    ```bash
    pip install pandas scikit-learn nltk
    ```
2.  **Dataset**: This script attempts to load a file named `NetflixDataset.csv`. **Make sure this file is in the same folder as the notebook.**
3.  **Run the Notebook**: Open `recommendation_system.ipynb` in Jupyter Notebook or Google Colab and run all the cells.
4.  **Get Recommendations**: At the bottom of the notebook, there is an input box. Type the exact name of a movie from the dataset (e.g., "The Con-Heartist"), and it will print out the top 10 recommendations!

## Example

If you enter: **"The Con-Heartist"**  
The system might recommend:

1.  Heartbeats
2.  The Other Woman
3.  Threesome
    ...and so on.
