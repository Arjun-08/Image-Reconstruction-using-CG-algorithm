# Image Reconstruction Using Conjugate Gradient Algorithm

This repository contains the implementation of a Conjugate Gradient (CG) algorithm to solve an image reconstruction problem as part of **Assignment II** for the course **E1 251: Linear and Nonlinear Optimization**.

## Problem Description

The goal is to reconstruct a 2D image (X) of size n x n from pixel values (m_i) sampled at random locations (r_i). The reconstruction problem is framed as the minimization of the function:

![image](https://github.com/user-attachments/assets/49bde183-d7bd-42b6-a068-775473b35326)


where:
- S_r_i is the operator that selects pixels at location r_i.
- λ is the regularization parameter.
- D_xx, D_yy, D_xy are second derivatives of Y in x, y, and both dimensions, respectively.
- ||...||^2 represents the sum of squared elements.

The mask M (binary matrix) identifies sampled pixel locations, and G (grayscale image) stores the sampled pixel values. The relationship between M, G, and X is defined as:

M ⊙ X = G,

where ⊙ represents element-wise multiplication.

The gradient of f(Y) is given as:

Gradient f(Y) = QY - G,

where Q is a linear operator determined by M and λ.

## Results and Observations

### Question 1
A Conjugate Gradient (CG) algorithm was implemented to minimize the reconstruction function and compute the missing pixel values. The algorithm iteratively updates the estimate until the gradient condition is satisfied:

||∇f(Y)|| / ||G|| < ε,

where ε is the tolerance parameter.

- **Visualization**: Original, sampled, and reconstructed images were displayed to demonstrate successful reconstruction.
- ![image](https://github.com/user-attachments/assets/9fe7a7e0-5f4f-4fc5-93c2-ab596f48e68e)
- ![image](https://github.com/user-attachments/assets/fd709576-3d4e-4dff-ae60-a9598739618f)



### Question 2
The effect of the tolerance (ε) on reconstruction quality was analyzed. Multiple ε values were tested, and the error between the original and reconstructed image was calculated as:

Reconstruction Error = ||X - X̂||^2,

where X is the original image and X̂ is the reconstructed image.

- **Graphs**: Plots showed the relationship between ε and reconstruction error.
- **Comparison**: Original, sampled, and reconstructed images for each ε value were displayed.
- **Optimal ε**: The best ε minimized the reconstruction error.
- ![image](https://github.com/user-attachments/assets/a7fdc428-4cce-4383-b8b0-63a9736b20ab)
- ![image](https://github.com/user-attachments/assets/0b6d3db5-95e2-4b3a-a97d-6008d9bcd4ab)
- ![image](https://github.com/user-attachments/assets/c188fa62-c9da-4105-84bb-c7656682a481)


### Question 3
The effect of the regularization parameter (λ) on reconstruction accuracy was evaluated. Various λ values were tested to determine their influence on reconstruction error:

Reconstruction Error = ||X - X̂||^2.

- **Graphs**: Reconstruction errors were plotted for different λ values.
- **Result**: The best λ was identified as the one that minimized reconstruction error.
- ![image](https://github.com/user-attachments/assets/d24a4bb8-72c3-43ff-b374-1130200d0f59)
- ![image](https://github.com/user-attachments/assets/220a2278-9f05-427c-ba76-773cb738eba9)
- ![image](https://github.com/user-attachments/assets/f0b6da2a-551a-42e7-97c2-00022a10469d)
- ![image](https://github.com/user-attachments/assets/d5786762-50d9-4a8f-92ec-6d9bc4f3a4ef)
- ![image](https://github.com/user-attachments/assets/790b300a-0034-4ca8-bbeb-96ee95269094)


### Question 4
Reconstruction was repeated for five different grayscale images, and the optimal λ was determined for each case.

- **Visualization**: Original, sampled, and reconstructed images for each test case were displayed side-by-side.
- ![image](https://github.com/user-attachments/assets/c3ebaa77-740a-49ce-bc3a-151141987ee6)

- **Optimal λ**: The best λ for each image was reported, highlighting its significance in improving reconstruction quality.
![image](https://github.com/user-attachments/assets/e4fecc50-9662-48ee-84cd-56b46d6a95c5)


## Dependencies

- Python 3.x
- NumPy
- Matplotlib
- Jupyter Notebook/Lab

## Contact
If you have any questions or suggestions, please feel free to reach out to me at nvarjunmani07@gmail.com.


