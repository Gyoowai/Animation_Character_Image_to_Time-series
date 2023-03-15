# Animation Character Image to Time-series
Animation character image classification is a challenging problem in the field of computer vision and multimedia analysis. The identification and classification of characters in animation require an accurate and efficient approach due to the high variability and complexity of animation character images. Converting images into time series data enables the application of traditional time series analysis techniques to image classification problems, reducing the need for large amounts of labeled data.

This project aims to explore the use of time series data for animation character image classification using OpenCV and Dynamic Time Warping (DTW) algorithm. We will investigate the use of [OpenCV](https://github.com/opencv/opencv-python), an open-source computer vision library, to convert animation character images into time series data. We will also use [DTW](https://github.com/pollen-robotics/dtw), a widely used algorithm for measuring the similarity between two time series, to compare the similarity of the time series data for character classification.

![introduction_image](https://github.com/Gyoowai/Animation_Character_Image_to_Time-series/blob/master/images/intro.png)

# Methodology
## Preprocessing: 
converting images into binary format involves assigning pixel values of the character area to one and pixel values of the background to zero. To accomplish this task, we need to do the following steps:

- Thresholding: converting an image into a binary format by selecting a threshold value and assigning all pixels with intensity values above the threshold to one (white) and those below the threshold to zero (black).

- Fill contours: filling in the interior of closed curves or shapes in an image.

- Inverted binarization: inverting a binary image to make the background of an image black (zero) and the foreground is white (one).

![preprocess_image](https://github.com/Gyoowai/Animation_Character_Image_to_Time-series/blob/master/images/preprocess.png)

## Converting into time-series
Given input of two-dimensional binary array, we explored two algorithms to convert them into time-series data including:
### 1. Finding first pixel vertically
This algorithm involves scanning each column of the input array from top to bottom until the first non-zero (or non-black) pixel is found. The position of this pixel in each column is recorded as a time-series data point.

![convert1_image](https://github.com/Gyoowai/Animation_Character_Image_to_Time-series/blob/master/images/convert1.png)

### 2. Summing the rows
This algorithm involves summing the values in each row of the input array and recording the resulting value as a time-series data point.


![convert2_image](https://github.com/Gyoowai/Animation_Character_Image_to_Time-series/blob/master/images/convert2.png)

# Results
Sample input images: 

Output:
- Converting into Time-series by finding first pixel vertically:

![convert3_image](https://github.com/Gyoowai/Animation_Character_Image_to_Time-series/blob/master/images/convert3.png)

- Converting into Time-series by summing the rows:

![convert4_image](https://github.com/Gyoowai/Animation_Character_Image_to_Time-series/blob/master/images/convert4.png)

To demonstrate that the resulting time series data are potentially useful as they can be used as representatives of the original data. The results from from KNN-classification algorithm (K=1) using Dynamic Time Warping (DTW) algorithms for distance measuring are shown below:

![knn_image](https://github.com/Gyoowai/Animation_Character_Image_to_Time-series/blob/master/images/knn.png)

---
2110430 Time Series Mining and Knowledge Discovery
