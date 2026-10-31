# Exp-4- Record-Image Transformations
# Name:DHIVYASHREE R
# Regno:212225040077

## Aim

To perform image transformations such as Translation, Scaling, Shearing, Reflection, Rotation, and Cropping using OpenCV and Python.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules.

### Step 2
Choose an image and save it as `filename.jpg` or `bird.png`.

### Step 3
Use `cv2.imread()` to read the image.

### Step 4
Use `cv2.warpPerspective(image, M, (cols, rows))` to translate the image.

### Step 5
Use `cv2.warpPerspective(image, M, (cols2, rows2))` to scale the image.

### Step 6
Apply shearing, reflection, and rotation by defining the appropriate transformation matrices.

### Step 7
Crop a specific region of the image and save the cropped image.

## Program
## i) Image Translation

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image
image = cv2.imread('me.jpeg')  # Load the image from file

# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off')

# Step 2: Image Translation
tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')
```

## ii) Image Scaling

```python
# Step 3: Image Scaling
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')
```

## iii) Image Shearing

```python
# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')
```

## iv) Image Reflection

```python
# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')
```

## v) Image Rotation

```python
# Step 6: Image Rotation
(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')
```

## vi) Image Cropping

```python
# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
```

## Output
### i) Input Iamge

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/e4ac9c6e-4e22-42b5-b935-1956bae09feb" />



### ii) Image Translation

<img width="286" height="407" alt="image" src="https://github.com/user-attachments/assets/94112df0-a89a-4c46-848b-2206536367a7" />



### iii) Image Scaling

<img width="515" height="394" alt="image" src="https://github.com/user-attachments/assets/6e0d5519-8030-4f74-9eaf-858d005f15c8" />


### iv) Image Shearing

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/0cbbfb79-41ac-417c-84e9-8adec4c8292b" />


### v) Image Reflection

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/f20e9b54-781b-4ecb-a64a-1c7ae62dc88b" />

### vi) Image Rotation

<img width="227" height="410" alt="image" src="https://github.com/user-attachments/assets/182eeeb3-b9e9-4e8c-9a27-17fa03d224cb" />



### vii) Image Cropping

<img width="512" height="410" alt="image" src="https://github.com/user-attachments/assets/29c5453a-4314-4e8d-b00c-55e507e36d5d" />



## Result

Thus, different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation, and Cropping were performed using OpenCV and Python programming.
