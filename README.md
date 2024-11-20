# Image Reconstruction Using Conjugate Gradient Algorithm

This repository contains the implementation of a Conjugate Gradient (CG) algorithm to solve an image reconstruction problem as part of **Assignment II** for the course **E1 251: Linear and Nonlinear Optimization**.

## Problem Description

The objective is to reconstruct a 2D image \( X \) of size \( n \times n \) from pixel values \( \{m_i\} \) sampled at random locations \( \{r_i\} \). The reconstruction is achieved by solving the following minimization problem:

\[
f(Y) = \sum_{i=1}^{L}(S_{r_i}Y - m_i)^2 + \lambda \left( \|D_{xx}Y\|_2^2 + \|D_{yy}Y\|_2^2 + 2\|D_{xy}Y\|_2^2 \right),
\]

where:
- \( S_{r_i} \) selects pixels at location \( r_i \),
- \( D_{xx}, D_{yy}, D_{xy} \) denote second-order derivatives in \( x \), \( y \), and cross terms,
- \( \lambda \) is the regularization parameter,
- \( M \) is a binary mask representing pixel locations \( \{r_i\} \),
- \( G \) contains the pixel values \( \{m_i\} \),
- The reconstructed image \( \hat{X} \) minimizes \( f(Y) \).

## Results and Observations

### Question 1
A Conjugate Gradient (CG) algorithm was implemented to minimize \( f(Y) \) and reconstruct the image from incomplete data. The algorithm iteratively updates \( Y \) using the residual error until convergence. The reconstruction objective function is defined, and the results demonstrated successful reconstruction from randomly sampled pixel values.

- **Visualization**: Original, sampled, and reconstructed images were displayed side-by-side.
- 

### Question 2
The impact of the tolerance parameter \( \epsilon \) on the reconstruction error \( \|X - \hat{X}\|_2 \) was analyzed. The algorithm tested various \( \epsilon \) values and found the optimal value based on the minimum reconstruction error.

- **Graphs**: Plots showed the relationship between \( \epsilon \) and reconstruction error.
- **Comparison**: Original, sampled, and reconstructed images for each \( \epsilon \) were displayed.

### Question 3
The effect of regularization parameter \( \lambda \) on reconstruction accuracy was analyzed. Various \( \lambda \) values were tested to evaluate their influence on reconstruction error \( \|X - \hat{X}\|_2 \).

- **Graphs**: Reconstruction errors were plotted against \( \lambda \) values.
- **Result**: The optimal \( \lambda \) was identified to minimize reconstruction error.

### Question 4
The reconstruction process was repeated for five grayscale images, optimizing \( \lambda \) for each image. The results demonstrated the impact of \( \lambda \) on reconstruction quality.

- **Visualization**: Original, sampled, and reconstructed images were displayed for each test case.
- **Best \( \lambda \)**: The optimal \( \lambda \) for each image was reported.

## Implementation Details

The implementation is provided in a Jupyter Notebook (`LNO2.ipynb`) and includes:
- CG Algorithm
- Simulation of random pixel sampling
- Analysis of \( \epsilon \) and \( \lambda \)
- Reconstruction and visualization


## Dependencies

- Python 3.x
- NumPy
- Matplotlib
- Jupyter Notebook/Lab
