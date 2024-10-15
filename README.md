
# Penguins Clustering Analysis

This project performs clustering analysis on a dataset of penguin measurements using K-Means clustering and Principal Component Analysis (PCA). The goal is to explore the penguin dataset, preprocess the data, and visualize the clusters formed based on the measurements.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Data Overview](#data-overview)
- [Data Preprocessing](#data-preprocessing)
- [Principal Component Analysis](#principal-component-analysis)
- [K-Means Clustering](#k-means-clustering)
- [Visualization](#visualization)
- [Contributing](#contributing)
- [License](#license)

## Installation

To run this project, you will need to have Python installed along with the following packages:

- `pandas`
- `matplotlib`
- `scikit-learn`

You can install the required packages using pip:

```bash
pip install pandas matplotlib scikit-learn
```

## Usage

1. **Download the Dataset**: Place the `penguins.csv` dataset in a folder named `data`.
2. **Run the Script**: Execute the script in a Python environment.

```bash
python penguins_clustering.py
```

## Data Overview

The dataset used for this analysis is the **penguins dataset** which contains measurements of various penguin species. The key columns include:
- `culmen_length_mm`: Length of the penguin's bill
- `culmen_depth_mm`: Depth of the penguin's bill
- `flipper_length_mm`: Length of the penguin's flipper
- `body_mass_g`: Mass of the penguin

## Data Preprocessing

The following preprocessing steps are applied to the dataset:

1. **Loading the Data**: The dataset is loaded into a pandas DataFrame.
2. **Handling Missing Values**: Rows with missing values are dropped.
3. **Outlier Removal**: Outliers are removed based on the `flipper_length_mm` measurement.
4. **Creating Dummy Variables**: Categorical variables are one-hot encoded.
5. **Standard Scaling**: The features are standardized using `StandardScaler`.

## Principal Component Analysis

Principal Component Analysis (PCA) is performed to reduce the dimensionality of the dataset while retaining most of the variance. The following steps are involved:

1. **Fitting PCA**: PCA is fitted to the preprocessed data.
2. **Determining the Number of Components**: The number of principal components is selected based on the explained variance ratio.

## K-Means Clustering

The K-Means algorithm is applied to the PCA-transformed data to cluster the penguins into groups. The following steps are taken:

1. **Inertia Calculation**: The inertia (within-cluster sum of squares) is calculated for a range of cluster numbers to determine the optimal number of clusters using the Elbow Method.
2. **Clustering**: K-Means clustering is performed with a predefined number of clusters.

## Visualization

The results of the clustering are visualized using a scatter plot of the first two principal components, with points colored by their cluster label. The Elbow Method chart can also be plotted to visualize the inertia values for different cluster counts.

```python
plt.plot(range(1, 30), inertia, marker='o')
plt.xlabel('Number of clusters')
plt.ylabel('Inertia')
plt.title('Elbow Method')
plt.show()
```

## Contributing

Contributions to improve this project are welcome! Please feel free to submit a pull request or open an issue.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
