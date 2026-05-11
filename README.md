# Geometric Transformations Using OpenCV

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

### Developed By: Shadhanashree S V

### Register No: 212223230202

```python
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

### Image Translation

<img width="515" height="381" alt="image" src="https://github.com/user-attachments/assets/86e5a1f2-6597-4e21-ad35-be55c3939382" />


### Image Scaling
 
<img width="515" height="176" alt="image" src="https://github.com/user-attachments/assets/06d22df5-99d8-49cf-bce8-279c88a96da1" />


### Image Shearing

<img width="515" height="381" alt="image" src="https://github.com/user-attachments/assets/54c86c9e-eec5-47a1-9415-4df2fefe45d1" />


### Image Reflection
  
<img width="515" height="381" alt="image" src="https://github.com/user-attachments/assets/2780f744-4e06-42c8-bf04-41788e8a60bc" />


### Image Rotation

<img width="515" height="381" alt="image" src="https://github.com/user-attachments/assets/6a5bfb65-bc61-45b0-8586-279b0602c893" />


### Image Cropping

 <img width="512" height="409" alt="image" src="https://github.com/user-attachments/assets/925e928c-339e-4580-b3a8-dbb0b060c3c5" />


---

## Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, rotation, and cropping are successfully performed using OpenCV.
