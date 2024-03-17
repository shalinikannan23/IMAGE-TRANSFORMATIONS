# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1: 
Import numpy module as np and pandas as pd.
### Step 2: 
Assign the values to variables in the program.
### Step 3: 
Get the values from the user appropriately.
### Step 4: 
Continue the program by implementing the codes of required topics.
### Step 5: 
Thus the program is executed in google colab.

## Program:

#### Developed By : SHALINI K
#### Register Number : 212222240095

### Installing OpenCV , importing necessary libraries and displaying images  

```py
# Install OpenCV library
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images 
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

```

#### (i) Image Translation
```py
# Load an image from URL or file path
image_url = '1.jpg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```

#### (ii) Image Scaling
```py

# Load an image from URL or file path
image_url = '2.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis


# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original Image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```




#### (iii) Image shearing
```py
# Load an image from URL or file path
image_url = '3.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)

```



#### (iv) Image Reflection

```py
# Load an image from URL or file path
image_url = '4.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

```

##### (a) → Reflecting Horizontally

```py
# Display original and reflected images

show_image(image)
print("↑ Original Image")
show_image(reflected_image_horizontal)
print("↑ Reflected Horizontally")
```

##### (b) → Reflected Vertically

```py
show_image(image)
print("↑ Original Image")
show_image(reflected_image_vertical)
print("↑ Reflected Vertically")

```

##### (c) → Reflecting Horizontally & Vertically
```py

show_image(image)
print("↑ Original Image")
show_image(reflected_image_both)
print("↑ Reflected Both")

```

### (v) Image Rotation

```py
# Load an image from URL or file path
image_url = '5.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)

```



### (vi) Image Cropping

```py
# Load an image from URL or file path
image_url = '6.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)

```


## Output:

### (i) Image Translation

<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/29c1dde6-653d-46a0-b427-a2eb49039165">

<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/7c3ed51e-a382-482c-9f6b-f4c0ae5e6240">




### (ii) Image Scaling
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/30e55c7b-3f2a-49d1-b59c-8182b7a6eda1">
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/82fa986d-8131-43c2-ac88-c4a2b7aeac4c">


### (iii) Image shearing

<img height=15% width=48% src="!https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/05ba513b-7c51-4ba4-a54e-c8c4ffaaab9b">
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/112f8ce9-b3af-45e8-b060-46ee3493fc51">


### (iv) Image Reflection

#### Reflecting Horizontally

<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/6d477f87-b263-446a-8ea9-3db3f724edea">
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/009c6f79-a460-43fc-8096-fdadebb5412b">


#### Reflecting Vertically
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/4c9fc26b-af4a-40ff-9fe7-93d705350566">
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/fd3dafaa-0dcb-45de-9d63-06a4587b38d4">


#### Reflecting Horizontally & Vertically
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/be580f93-d376-4ac3-b105-cceb12f1b99f">

<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/8e42be40-4a88-4471-8fc8-898c6e6ae1f2">


### (v) Image Rotation
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/d2a9e0be-042b-49f6-a138-f501ed6d7728">


### (vi) Image Cropping
<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/e0cadb83-1b19-454f-8cec-ea531edec65a">

<img height=15% width=48% src="https://github.com/shalinikannan23/IMAGE-TRANSFORMATIONS/assets/118656529/1d1320f8-282c-4975-9623-95278c1b696f">


## Result: 

### Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
