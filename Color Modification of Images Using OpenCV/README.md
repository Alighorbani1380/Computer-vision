# Exercise
 Change the color of the petals of the flower in the jpg image "sunflower" and save the new image with your desired color.
 
## Color Modification of Images Using OpenCV
### Introduction
Image processing is a critical aspect of computer vision, enabling various applications from basic photo editing to more advanced techniques used in machine learning and artificial intelligence. One common task in image processing is color manipulation. This document outlines how to change specific colors in an image using the OpenCV library in Python, focusing on altering the color of yellow petals in a flower image to a shade of red.

### Prerequisites
To execute the code snippet provided below, ensure you have the following:

Python installed on your system.
The OpenCV library installed. You can install it using pip:
pip install opencv-python  
A sample image named input.jpg that includes yellow regions (like a sunflower).
## Code Explanation
The following Python code demonstrates how to read an image, create a mask for yellow colors, and change those colors to red.

import cv2  
import numpy as np  

### Step 1: Load the image  
image = cv2.imread('input.jpg')  

### Step 2: Define the lower and upper bounds for the yellow color in HSV  
lower_yellow = np.array([4, 120, 120], dtype=np.uint8)  # lower bound for yellow  
upper_yellow = np.array([30, 255, 255], dtype=np.uint8) # upper bound for yellow  

### Step 3: Create a mask that isolates the yellow areas in the image  
yellow_mask = cv2.inRange(cv2.cvtColor(image, cv2.COLOR_BGR2HSV), lower_yellow, upper_yellow)  

### Step 4: Change the color of the pixels in the image identified by the yellow mask  
image[np.where(yellow_mask != 0)] = [0, 0, 150] # Set identified yellow pixels to BGR red  

### Step 5: Display the output image in a window  
cv2.imshow('output', image)  
cv2.waitKey() # Wait for a key press  

### Step 6: Save the modified image to a new file  
cv2.imwrite('flowerred.jpg', image)  
## Detailed Breakdown
Import Libraries: The code begins by importing the necessary libraries—cv2 for image processing and numpy for numerical operations.


Load Image: It uses cv2.imread() to load the image. It is important that the image file is in the correct path.


Color Range Definition: The code defines the range of yellow in the HSV color space:

lower_yellow sets the lower bound for the yellow hue.
upper_yellow sets the upper bound.
Mask Creation: The cv2.inRange() function creates a binary mask where yellow pixels are set to 255 (white) and all other pixels to 0 (black). The color space conversion from BGR to HSV is handled to make the color detection more robust.

Color Alteration: Pixels in the original image that match the yellow mask are changed to red using BGR format.

Display and Save: The modified image is displayed in a window. After closing the window, the new image with altered colors is saved as flowerred.jpg.

![image](https://github.com/user-attachments/assets/a2269936-acee-4369-867f-fccc4e709abb)


## Conclusion
The presented code provides a simple yet powerful method to manipulate colors within an image using the OpenCV library. By adjusting the HSV ranges, users can target specific colors for modification, making it versatile for various applications like creating artistic effects, improving image aesthetics, or preparing images for further analysis. Experimentation with color ranges enables users to adapt the code for different images and desired outputs.




