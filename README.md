# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
<br>
Translate the image using a function warpPerpective()

### Step3:
<br>
Scale the image by multiplying the rows and columns with a float value.

### Step4:
<br>
Shear the image in both the rows and columns.

### Step5:
<br>
Find the reflection of the image.

### Step 6:
<br>
Rotate the image using angle function.

## Program:

## Developed By: JANANI S
## Register Number: 212223230086

```python

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image
image = cv2.imread('hib.jpg')  # Load the image from file

# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off')

i)Image Translation

tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')

ii) Image Scaling

fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')

iii)Image shearing

shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')

iv)Image Reflection

reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')

v)Image Rotation

(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')

vi)Image Cropping

x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')

```
## Output:

<img width="754" height="606" alt="image" src="https://github.com/user-attachments/assets/dbffc278-50c6-4fd8-9a5a-096890b5046b" />

### i)Image Translation
<br>
<br>
<img width="703" height="551" alt="image" src="https://github.com/user-attachments/assets/8bec4dd9-58cd-4aa5-ad87-c5847c6b3d21" />

<br>
<br>

### ii) Image Scaling
<br>
<br>
<img width="695" height="280" alt="image" src="https://github.com/user-attachments/assets/61d3c90c-24c7-42d7-8c31-3bb98478857a" />

<br>
<br>


### iii)Image shearing
<br>
<br>
<img width="704" height="550" alt="image" src="https://github.com/user-attachments/assets/df03bde2-3e52-4be8-9d48-3128bb07f21d" />

<br>
<br>


### iv)Image Reflection
<br>
<br>
<img width="681" height="544" alt="image" src="https://github.com/user-attachments/assets/9bc01bc7-b4d6-4b48-8d9c-db08343476b3" />

<br>
<br>



### v)Image Rotation
<br>
<br>
<img width="686" height="549" alt="image" src="https://github.com/user-attachments/assets/5170e11c-5549-4540-ae0f-39324eec23ab" />

<br>
<br>



### vi)Image Cropping
<br>
<br>
<img width="678" height="440" alt="image" src="https://github.com/user-attachments/assets/b12c0ca0-f3ec-4d0e-808e-97ee983036df" />

<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
