# MNIST Clustering Project

This project explores **unsupervised clustering techniques** on the popular **MNIST dataset** of handwritten digits. The goal is to group similar digits together **without using the labels**, using three different clustering algorithms implemented in **Jupyter Notebooks**.

## Algorithms Used

1. **Gaussian Mixture Models (GMM)**
   - Probabilistic model assuming data points are generated from a mixture of several Gaussian distributions.
   - Implemented with `scikit-learn`'s `GaussianMixture`.

2. **Normalized Cut (Spectral Clustering)**
   - Graph-based clustering that partitions data by minimizing the normalized cut value on a similarity graph.
   - Implemented via `scikit-learn`'s `SpectralClustering` with custom similarity matrices.

3. **Mean Shift**
   - Mode-seeking algorithm that clusters data by iteratively shifting data points towards the region of highest density.
   - Implemented with `scikit-learn`'s `MeanShift`.

---

## Files Included

- `Gaussian.ipynb`: Clustering MNIST using Gaussian Mixture Models.
- `Normalized Cut.ipynb`: Spectral clustering via Normalized Cuts.
- `Mean Shift.ipynb`: Clustering with Mean Shift algorithm.
- `total_time.ipynb`: Comparative analysis of computation time for each method.

---

## Dataset

- **MNIST dataset**:
  - 70,000 images of handwritten digits (28x28 grayscale).
  - Loaded via `sklearn.datasets.fetch_openml("mnist_784")` or pre-downloaded.
  - **Note**: Labels are only used for evaluation, not during clustering.
  - The MNIST dataset is provided by Yann LeCun and collaborators:  
    [http://yann.lecun.com/exdb/mnist/](http://yann.lecun.com/exdb/mnist/)
    
---
## Results Overview

### Clustering Performance

| Algorithm        | PCA Dim | Number of Clusters | Adjusted Rand Index (ARI) |
|------------------|---------|--------------------|----------------------------|
| Gaussian Mixture |   22    |         13         |         0.906265          |
| Normalized Cut   |   52    |         12         |         0.935512          |
| Mean Shift       |   22    |         62         |         0.905235          |

### Computational Time

| Algorithm        | Total Fit-Predict Time (s) | Mean Fit-Predict Time (s) |
|------------------|----------------------------|---------------------------|
| Gaussian Mixture |         145.21975          |         0.66008           |
| Normalized Cut   |        1253.37561          |         5.69716           |
| Mean Shift       |        1149.71211          |        11.16225           |

*(Note: Times and ARI scores may vary slightly depending on hardware and system load)*

---

## Evaluation Summary

- **Best Clustering Quality**: Normalized Cut achieved the highest Adjusted Rand Index (0.9355), indicating the most accurate clustering relative to ground truth labels.
- **Fastest Algorithm**: Gaussian Mixture was significantly faster, with a total fit-predict time of ~145 seconds, making it the most suitable for large-scale tasks.
- **Trade-off**: Mean Shift showed competitive clustering quality but had the highest per-run execution time, making it less optimal for large datasets without further optimization.

---

## Requirements

- Python 3.8+
- Jupyter Notebook
- Dependencies:
  ```bash
  pip install numpy matplotlib scikit-learn seaborn

---

## License
This project is open-source under the MIT License.
