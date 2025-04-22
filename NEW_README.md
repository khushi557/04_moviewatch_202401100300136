Overview
This project performs clustering of users based on their movie watching patterns, which are derived from the following features:

Time of Watching: Extracts time-related features from movie watch timestamps.

Genre Preference: Identifies the distribution of genres each user prefers.

Rating Behavior: Analyzes users' rating tendencies, such as average rating and variability.

The final goal is to group users into clusters of similar patterns, which can be useful for:

Improving recommendation systems.

Personalizing user experiences.

Understanding audience behavior for marketing.

Features
Clustering based on time of watching (hour of day, day of week).

Genre preference calculated from movie categories watched.

Rating behavior analysis, including average rating and rating variability.

Data normalization and standardization to ensure clustering is based on comparable features.

Visualizations of clustered data to interpret patterns.

Setup
Prerequisites
Python 3.x

Libraries:

pandas

numpy

sklearn

matplotlib

seaborn

You can install the required libraries using the following:

bash
Copy
Edit
pip install pandas numpy scikit-learn matplotlib seaborn
Data
Ensure you have a CSV file containing user movie watch data with the following columns:

UserID: Unique identifier for each user.

Timestamp: The time when the user watched the movie.

Genre: The genre(s) of the movie(s).

Rating: The rating the user gave the movie (e.g., on a scale from 1 to 10).

Example format:

csv
Copy
Edit
UserID,Timestamp,Genre,Rating
1,2025-04-01 15:30:00,Action,8
1,2025-04-02 20:45:00,Comedy,7
2,2025-04-01 22:00:00,Drama,6
...
Running the Project
Clone or download this repository.

Place your movie data CSV file in the project directory.

Run the clustering.py script to perform clustering.

bash
Copy
Edit
python clustering.py
This will:

Load the data.

Extract features such as time of watching, genre preferences, and rating behavior.

Normalize and cluster the data.

Visualize the clusters.

Data Description
The dataset should contain the following columns:

UserID: The unique identifier for each user.

Timestamp: The timestamp indicating when a movie was watched.

Genre: A string representing the genre(s) of the movie (e.g., "Action", "Comedy").

Rating: The rating provided by the user for that movie.

Example Data

UserID	Timestamp	Genre	Rating
1	2025-04-01 15:30:00	Action	8
1	2025-04-02 20:45:00	Comedy	7
2	2025-04-01 22:00:00	Drama	6
2	2025-04-02 18:30:00	Action, Comedy	9
Implementation
The implementation follows these steps:

Data Preprocessing:

Extract features such as hour, day_of_week from the Timestamp.

Compute the average and variability of ratings for each user.

Calculate the genre preference based on the genres of the movies watched.

Data Normalization:

Normalize the features to make them comparable (using standard scaling or Min-Max scaling).

Clustering:

Apply clustering algorithms (e.g., K-Means, DBSCAN, etc.) to group similar users based on their patterns.

Evaluation:

Evaluate the clustering using metrics like Silhouette Score, Davies-Bouldin Index, and cluster interpretation.

Visualization:

Visualize the clusters using scatter plots and other charts to interpret the results.

Clustering Methods
The following clustering methods were explored:

K-Means:

Used to partition users into a specified number of clusters.

The optimal number of clusters (K) is chosen using the Elbow Method.

DBSCAN (Density-Based Spatial Clustering of Applications with Noise):

Used for clustering users with varying densities and irregular shapes.

Hierarchical Clustering:

Used to create a dendrogram representing nested clusters.

Gaussian Mixture Model (GMM):

A probabilistic model that clusters based on a mixture of Gaussian distributions.

Visualization
To visualize the clustering results, you can generate scatter plots and 2D/3D plots using the matplotlib and seaborn libraries. The features can be reduced to 2D/3D using Principal Component Analysis (PCA) or t-SNE.

Example Visualization Code:
python
Copy
Edit
import seaborn as sns
import matplotlib.pyplot as plt

sns.scatterplot(x=user_data['hour'], y=user_data['average_rating'], hue=user_data['Cluster'], palette='viridis')
plt.title('User Clusters based on Time of Watching and Rating Behavior')
plt.show()
Evaluation
Evaluate the quality of the clusters using metrics such as:

Silhouette Score: Measures how similar each point is to its own cluster compared to other clusters.

Davies-Bouldin Index: Measures the similarity between clusters. Lower values indicate better separation.

Cluster Interpretation: Analyze the characteristics of each cluster (e.g., peak watching times, preferred genres, average ratings).

License
This project is licensed under the MIT License - see the LICENSE file for details.

This README provides a comprehensive guide to set up, run, and evaluate the clustering model based on movie watch patterns. Let me know if you need further adjustments or additions!




![Screenshot 2025-04-22 113041](https://github.com/user-attachments/assets/195c7632-e24a-45c8-9cf8-a284e1db88d0)
