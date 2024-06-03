<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Recommender System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 800px;
            margin: auto;
            padding: 20px;
            background: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1, h2, h3 {
            color: #333;
        }
        pre {
            background: #f4f4f4;
            padding: 10px;
            border: 1px solid #ddd;
            overflow-x: auto;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Music Recommender System</h1>

        <h2>Overview</h2>
        <p>This project is a music recommender system that suggests songs based on similarity measures. The system uses a precomputed similarity matrix to find songs that are similar to a given track. The dataset includes information about users, artists, tracks, and playlists.</p>

        <h2>Features</h2>
        <ul>
            <li>Recommends songs based on a given track.</li>
            <li>Uses a precomputed similarity matrix for fast recommendations.</li>
            <li>Handles missing values in the dataset.</li>
        </ul>

        <h2>Setup</h2>
        <p>To set up the recommender system on your local machine, follow these steps:</p>
        <ol>
            <li>
                Clone the repository:
                <pre><code>git clone https://github.com/nikithamarythomas/musicrec.git
cd musicrec</code></pre>
            </li>
            <li>
                Install the required libraries:
                <pre><code>pip install -r requirements.txt</code></pre>
            </li>
            <li>
                Download the precomputed similarity matrix and data files:
                <ul>
                    <li><code>similarity.pkl</code>: The similarity matrix.</li>
                    <li><code>df.pkl</code>: The dataset with user, artist, track, and playlist information.</li>
                </ul>
                <p>Due to GitHub's file size limits, these files are not fully visible on the GitHub repository. You can download the complete files by cloning the repository and accessing them locally.</p>
            </li>
            <li>
                Load the data files in your script:
                <pre><code>import pickle

with open('similarity.pkl', 'rb') as file:
    similarity = pickle.load(file)

with open('df.pkl', 'rb') as file:
    df = pickle.load(file)</code></pre>
            </li>
        </ol>

        <h2>Usage</h2>
        <p>Here is an example of how to use the recommender system:</p>
        <pre><code>import pickle

# Load the similarity matrix and data frame
with open('similarity.pkl', 'rb') as file:
    similarity = pickle.load(file)

with open('df.pkl', 'rb') as file:
    df = pickle.load(file)</code></pre>
    </div>
</body>
</html>
