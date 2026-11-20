# EX.7 - HOUGH TRANSFORM
# Aim
To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

# Learning Objective
Understand each stage of image processing
Learn how to build a complete computer vision pipeline
Practice writing code in guided sections

# Instructions
Fill ONLY in # Your Code Here sections
Do NOT change existing code
Run step-by-step
Verify outputs

# Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

# Developed By
# Name: Harini V K
# Register No: 212225220036

# Program
```
import cv2
import numpy as np
import matplotlib.pyplot as 
 Step 2: Load the image using imread() from cv2 module
image = cv2.imread('Harini.new.jpeg')  # Replace 'image.jpg' with your image path
step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"

# Step 6: Draw the detected lines on the original image

for line in lines:
    x1, y1, x2, y2 = line  # Unpacking coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

# Output

<img width="662" height="457" alt="image" src="https://github.com/user-attachments/assets/c8ffdfb0-3568-4dd6-9ce3-b303b58e4764" />

<img width="650" height="462" alt="image" src="https://github.com/user-attachments/assets/d4f9dc1b-49d9-4902-83c9-fee27e558084" />

<img width="645" height="460" alt="image" src="https://github.com/user-attachments/assets/df529007-53f3-4cdc-b98a-a2ee1406d1f0" />

<img width="653" height="453" alt="image" src="https://github.com/user-attachments/assets/32be9ecf-b3bb-4cc1-9adc-8b54af1ca959" />

# Result
Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.




