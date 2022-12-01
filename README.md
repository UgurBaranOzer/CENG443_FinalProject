# CENG443 - Final Project
###   Subject: Parallelization of Sobel Edge Detect Filter in CUDA
### Student & ID: Uğur Baran Özer - 250201034

------------

##### Algorithm Definition

[![sobel_filter](https://raw.githubusercontent.com/pascal-canuel/SobelFilter-Cuda/master/showcase/field.PNG "sobel_filter")](https://raw.githubusercontent.com/pascal-canuel/SobelFilter-Cuda/master/showcase/field.PNG "sobel_filter")
Figure shows Sobel Filter applied on left and original image right
------------


Sobel Filter in image processing is an algorithm to identify sharp changes in intensity which means edges. This discrete differentiation operator convolves the input image in the horizontal and vertical axes with a 3x3 kernel to approximate the gradient of the image intensity function. Steps of the algorithm seen as:

1.  Convert RGB image to grayscale
2.  Convolve the grayscale image with horizontal gradient
3.  Convolve the grayscale image with vertical gradient
4. Combine vertical and horizontal gradient 

##### Project Idea


In this algorithm steps(2-3) convolution calculation made by CPU and in image with high resolution these calculations can take majority of the time. A parallel CUDA impelementation can be made for these steps. Images width is equal to total blocks in CUDA grid and images height is equal to number of threads per block. With this implementation every calculation of a pixel in image made by one thread.
