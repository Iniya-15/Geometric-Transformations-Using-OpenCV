# Geometric-Transformations-Using-OpenCV

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling  
- Image Shearing  
- Image Reflection  
- Image Rotation  
- Image Cropping  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 100 pixels to the right and 50 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image using scaling factors:
  - 5.0× in x direction  
  - 2.0× in y direction  
- Use `cv2.resize()`  
- Display original and scaled images  

### Step 5: Image Shearing
- Create shearing matrix  
- Apply shearing transformation using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform image reflection using `cv2.flip()`  
- Display reflected image  

### Step 7: Image Rotation
- Create rotation matrix for 45° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display rotated image  

### Step 8: Image Cropping
- Define crop coordinates and dimensions  
- Extract selected image portion using array slicing  
- Display cropped image  

---

## Program

### Developed By: Iniya E

### Register No: 212224230096

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image
image = cv2.imread('Qn4.jpg')

# Display original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')

# Step 2: Image Translation
tx, ty = 100, 50
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')

# Step 3: Image Scaling
fx, fy = 5.0, 2.0
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')

# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')

# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')

# Step 6: Image Rotation
(height, width) = image.shape[:2]
angle = 45
center = (width // 2, height // 2)
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')

# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
```

---

## Output

### Original Image

<img width="334" height="510" alt="image" src="https://github.com/user-attachments/assets/b923b4fb-e6f1-40d5-ae46-84c0819bb313" />



### Translated Image
 
<img width="363" height="519" alt="image" src="https://github.com/user-attachments/assets/a8b0a6c4-fce7-4e97-8991-b28e1f4dc149" />



### Sclaed Image

<img width="665" height="429" alt="image" src="https://github.com/user-attachments/assets/61f1309d-b499-4961-b1c5-d58da5d68a5e" />



### Sheared Image
  
<img width="356" height="510" alt="image" src="https://github.com/user-attachments/assets/6f4cabbf-0c91-4fcd-8ccb-ccb242d08d08" />

## Reflected Image 

<img width="336" height="516" alt="image" src="https://github.com/user-attachments/assets/5c20247f-2d00-4ca7-b23c-b7358b97ae89" />


### Image Rotation

<img width="364" height="508" alt="image" src="https://github.com/user-attachments/assets/05f660bb-9634-45b9-900a-830646d206a2" />


### Image Cropping

<img width="658" height="507" alt="image" src="https://github.com/user-attachments/assets/b521f277-97c0-44e8-8669-b14e248690f3" />



---

## Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, rotation, and cropping are successfully performed using OpenCV.
