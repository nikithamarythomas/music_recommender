# Music Recommender System

## Overview

This project is a music recommender system that suggests songs based on similarity measures. The system uses a precomputed similarity matrix to find songs that are similar to a given track. The dataset includes information about users, artists, tracks, and playlists.

## Features

- Recommends songs based on a given track.
- Uses a precomputed similarity matrix for fast recommendations.
- Handles missing values in the dataset.

## Setup

To set up the recommender system on your local machine, follow these steps:

1. **Clone the repository:**

    ```sh
    git clone https://github.com/nikithamarythomas/musicrec.git
    cd musicrec
    ```

2. **Install the required libraries:**

    ```sh
    pip install -r requirements.txt
    ```

3. **Download the precomputed similarity matrix and data files:**

    - `similarity.pkl`: The similarity matrix.
    - `df.pkl`: The dataset with user, artist, track, and playlist information.

    Due to GitHub's file size limits, these files are not fully visible on the GitHub repository. You can download the complete files by cloning the repository and accessing them locally.

4. **Load the data files in your script:**

    ```python
    import pickle

    with open('similarity.pkl', 'rb') as file:
        similarity = pickle.load(file)

    with open('df.pkl', 'rb') as file:
        df = pickle.load(file)
    ```

## Usage

Here is an example of how to use the recommender system:

```python
import pickle

# Load the similarity matrix and data frame
with open('similarity.pkl', 'rb') as file:
    similarity = pickle.load(file)

with open('df.pkl', 'rb') as file:
    df = pickle.load(file)

# Function to recommend songs based on a given song
def recommendation(song_name):
    idx = df[df['song'] == song_name].index[0]
    distances = sorted(list(enumerate(similarity[idx])), reverse=True, key=lambda x: x[1])
    recommended_songs = [df.iloc[i[0]]['song'] for i in distances[1:11]]
    return recommended_songs

# Example usage
print(recommendation('Glee'))
