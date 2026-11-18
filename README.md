# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.
```
image_path = next(iter(uploaded))

img = cv2.imread(image_path)

# Convert BGR to RGB
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img)
plt.title("Original Image")
plt.axis('off')
plt.show()
```

### Step 4:

Create a structuring element (kernel) of suitable size.
```
kernel = np.ones((5, 5), np.uint8)
```

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.
```
opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)

plt.imshow(opening)
plt.title("Opening Image")
plt.axis('off')
plt.show()
```

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.
```
closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

plt.imshow(closing)
plt.title("Closing Image")
plt.axis('off')
plt.show()
```

### Step 7:

Compare the original, opened, and closed images.
```
plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(opening)
plt.title("Opening")
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(closing)
plt.title("Closing")
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Program Developed By

**Name:** Janesha S

**Register No:** 212225240056

## Output

### Original Image

- The input image is displayed.
- The image serves as the source for morphological processing.

  <img width="515" height="352" alt="image" src="https://github.com/user-attachments/assets/7cf5347f-c79b-4522-ae97-35eb5e33ec4f" />


### Opening Operation

- Original image is displayed.
- Opened image is displayed.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.

  <img width="515" height="352" alt="image" src="https://github.com/user-attachments/assets/0d17938d-b7f9-496b-8e98-ffc8bcf4b851" />


### Closing Operation

- Original image is displayed.
- Closed image is displayed.
- Small holes and gaps inside objects are filled.
- Broken regions are connected.
- Object boundaries become more continuous.

  <img width="515" height="352" alt="image" src="https://github.com/user-attachments/assets/71658b31-9708-40d8-91ba-a28680110f7f" />

  <img width="1489" height="342" alt="image" src="https://github.com/user-attachments/assets/0fa28a90-429e-45df-99aa-079af2322533" />



## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
