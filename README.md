# PCA-for-Dimensionality-Reduction-and-Visualization
# Overview & Purpose
This Jupyter Notebook provides a practical demonstration of Principal Component Analysis (PCA), a widely used unsupervised linear dimensionality reduction technique. PCA transforms a high-dimensional dataset into a lower-dimensional space while preserving as much of the data's variance as possible. This is particularly useful for:
Visualization: Reducing data to 2 or 3 dimensions allows for plotting and visual inspection of clusters or patterns that are otherwise hidden in high-dimensional space.
Noise Reduction: By focusing on components with high variance, PCA can effectively reduce noise.
Feature Engineering: Creating new, uncorrelated features (principal components) that capture the most important information.
This project applies PCA to the famous MNIST handwritten digits dataset, a classic benchmark in machine learning, to illustrate:
Dimensionality Reduction: Transforming 784-dimensional image data (28x28 pixels) into a 2-dimensional or 3-dimensional representation.
Variance Explained: Understanding how much information (variance) is retained by each principal component.
Data Visualization: Plotting the transformed data to see if digits of the same class cluster together.

# Key Concepts & Functionality
The notebook covers the following aspects of PCA:
Initial Setup: Imports pandas and numpy for data manipulation, and matplotlib.pyplot for basic plotting.

Data Loading and Preparation:
Loads the train.csv file, which is assumed to be the MNIST training dataset.
Separates features (X, which are the pixel values) from the target variable (y, which are the digit labels).
Splits the data into training and testing sets using train_test_split.

PCA Implementation:
Imports PCA from sklearn.decomposition.
Initial PCA for Variance Analysis:
Initializes pca = PCA() without specifying n_components to compute all possible principal components.
Fits pca to the training data (X_train).
Plots the explained variance ratio for each component (pca.explained_variance_ratio_). This plot is crucial for deciding how many components to keep, as it shows the proportion of total variance captured by each component.
Plots the cumulative explained variance, which helps determine the number of components needed to retain a certain percentage of the total variance (e.g., 95%).

PCA for 2D Visualization:
Initializes pca = PCA(n_components=2) to reduce the data to two principal components.
Applies fit_transform on the training data (X_train_trf) and transform on the test data (X_test_trf).
Visualizes the 2D transformed data: Uses plotly.express.scatter to create an interactive scatter plot of PC1 vs. PC2, colored by the digit label (y_train). This allows for visual inspection of how well different digit classes separate in the reduced 2D space.

PCA for 3D Visualization (Optional/Conceptual based on typical PCA use):
(The provided snippet only shows 2D visualization, but typically PCA notebooks extend to 3D for more complex data.) If n_components=3 were used, a 3D scatter plot would be generated.

Eigenvectors (Principal Components):
Prints pca.components_, which are the principal components themselves (the eigenvectors of the covariance matrix). Each row represents a principal component, and its values indicate the contribution of each original feature to that component.
Prints the shape of pca.components_.

# Technologies Used
Python
Pandas (for data loading and manipulation)
NumPy (for numerical operations)
Matplotlib (for basic plotting, especially variance plots)
Plotly Express (for interactive scatter plots)
Scikit-learn (train_test_split, PCA)
Jupyter Notebook
