# Unsupervised Learning: PCA and ICA

## Project Overview

This project explores unsupervised learning techniques with a focus on **Principal Component Analysis (PCA)** and **Independent Component Analysis (ICA)** for dimensionality reduction. The notebook includes toy examples to illustrate these techniques and applies them to a real-world dataset of facial images. It highlights the power of unsupervised methods in discovering structure and reducing dimensionality without labeled data.

The project is implemented entirely in a Jupyter Notebook (`.ipynb` file), making it easy to follow and execute.

## Theoretical Background

To provide further clarity and insight into the mathematical steps presented, let's expand on the importance and implications of these transformations, particularly in the context of Principal Component Analysis (PCA).

### Geometric Interpretation

The transformation $Y = XU$ represents the projection of the original data matrix $X$ into a new coordinate system where the axes are defined by the principal components (the eigenvectors of $C$). These principal components are orthogonal directions that capture the maximum variance in the data. By projecting $X$ onto this new basis defined by the matrix $U$, we align the data along uncorrelated axes.

The result is that the covariance matrix of the transformed data $Y$, which is given by $C_Y = D$, is diagonal. This indicates that the new features (the principal components) are uncorrelated with each other, and the diagonal elements of $D$ correspond to the variances along each principal component. This diagonalization is a hallmark of PCA, as it simplifies the structure of the data, making it easier to interpret and analyze.

### Eigenvalue Decomposition and Dimensionality Reduction

The decomposition $C = UDU^T$ reveals that the covariance matrix $C$ can be factored into its eigenvectors $U$ and eigenvalues $D$. The eigenvalues in $D$ represent the amount of variance captured by each principal component, and they are arranged in decreasing order. This structure allows for dimensionality reduction: by selecting only the first few principal components (corresponding to the largest eigenvalues), we can capture most of the variance in the data with fewer dimensions, reducing the complexity of the dataset without losing much information.

### Orthogonal Transformations and Preservation of Inner Products

The orthogonal property of $U$, where $U^T U = I$, plays a crucial role in preserving certain geometric properties of the data. Specifically, this orthogonal transformation preserves inner products, distances, and angles between vectors. As shown in the proof, the inner product between any two transformed vectors $y_p$ and $y_q$ is the same as the inner product between the original vectors $x_p$ and $x_q$:

$$ y_p y_q^T = x_p x_q^T $$

This property ensures that the transformation by $ U $ does not distort the relationships between data points. In other words, the relative positions of the data points in the new coordinate system reflect their original relationships, making PCA a powerful tool for dimensionality reduction while preserving the structure of the data.


### Principal Component Analysis (PCA)

PCA is a statistical technique used to reduce the dimensionality of data while retaining most of the variance. It identifies new axes (principal components) that maximize the variance in the data, and projects the data onto these axes. The result is a compressed version of the dataset that preserves essential patterns.

Mathematically, PCA seeks to solve:

$$ \text{Maximize: Var}(y) = Var(W^T X) $$

Where:
- $X$ is the input data,
- $W$ are the weights representing the principal components,
- $y$ is the transformed data along the principal components.

### Independent Component Analysis (ICA)

ICA goes beyond PCA by not only reducing dimensionality but also identifying statistically independent components within the data. This technique is particularly useful in applications like source separation (e.g., separating mixed audio signals).

ICA assumes that the observed data is a linear mixture of independent sources, and it attempts to recover these sources by maximizing statistical independence.

## Key Skills Demonstrated

- **Dimensionality Reduction**: Application of PCA and ICA to reduce the number of features while retaining critical information in both toy examples and real-world datasets.
- **Face Dataset Analysis**: Applied PCA and ICA to a dataset of facial images, showcasing the ability of unsupervised learning to extract meaningful features (e.g., eigenfaces for PCA).
- **Data Visualization**: Visualized the transformation of the data in reduced dimensions, demonstrating the effectiveness of these techniques in simplifying complex datasets.

## Project Structure

- **PCA Implementation**: Applied PCA on toy datasets to illustrate the algorithm’s ability to reduce dimensionality and retain maximum variance. Extended this to a facial image dataset, demonstrating how PCA can capture dominant patterns in faces (e.g., eigenfaces).
- **ICA Implementation**: Applied ICA to the same datasets, showcasing how it can uncover independent components, which are often more interpretable in real-world applications.
- **Data Visualization**: Plotted the principal and independent components to visualize the transformations. This includes a comparison of how PCA and ICA treat the data differently.
- **Face Dataset Results**: Visualized the compressed representations of facial images using PCA and ICA, comparing the reconstructions and extracting insights from the components identified.

## Notable Results

- **PCA on Face Dataset**: Extracted dominant eigenfaces that effectively represent various features of human faces.
- **ICA on Face Dataset**: Identified statistically independent components, providing a different interpretation of the data, especially useful for feature extraction.
- **Toy Examples**: Illustrated the mechanics of both algorithms on simple datasets, giving an intuitive understanding of how dimensionality reduction works.

## Lessons Learned

- **Dimensionality Reduction**: Understood the trade-offs between PCA and ICA, particularly in how they handle variance and independence.
- **Feature Extraction**: Learned how unsupervised methods can extract meaningful features without any labeled data, which is especially useful in fields like computer vision and signal processing.
