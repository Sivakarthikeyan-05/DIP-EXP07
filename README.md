# EXP-7 RECORD — HOUGH TRANSFORM

**Register No:** 212225220098
**Name:** Sivakarthikeyan V

---

## Aim

To implement the Hough Transform using OpenCV for detecting and highlighting straight lines in an image.

---

## Learning Objective

* Understand the stages of image processing.
* Learn image loading and grayscale conversion.
* Understand Canny edge detection.
* Learn the working of Probabilistic Hough Line Transform.
* Detect and highlight straight lines using OpenCV.

---

## Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (`cv2`)
* NumPy
* Matplotlib

---

## Algorithm & Implementation

### Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2: Load the Image

```python
# Load the image using imread() from cv2 module
image = cv2.imread('Photo.jpg')
```

### Step 3: Convert the Image to Grayscale

```python
# Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

### Step 4: Display Input and Grayscale Images

```python
# Input image
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

# Grayscale image
plt.subplot(1, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

plt.show()
```

### Step 5: Edge Detection Using Canny Operator

```python
# Detect edges using Canny operator
edges = cv2.Canny(gray_image, 50, 150)

plt.figure(figsize=(10, 5))
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()
```

### Step 6: Hough Line Transform

```python
# Detect line coordinates using HoughLinesP()
lines = cv2.HoughLinesP(
    edges,
    1,
    np.pi / 180,
    100,
    minLineLength=50,
    maxLineGap=10
)
```

### Step 7: Draw Detected Lines

```python
# Draw detected lines on the original image
for line in lines:
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.figure(figsize=(10, 6))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Detected Lines")
plt.axis("off")
plt.show()
```

---

## Complete Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('Photo.jpg')

# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)

# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

# Step 5: Using HoughLinesP(), detect line coordinates
# Parameters: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(
    edges,
    1,
    np.pi / 180,
    100,
    minLineLength=50,
    maxLineGap=10
)

# Step 6: Draw the detected lines on the original image
for line in lines:
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.figure(figsize=(10, 6))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Detected Lines")
plt.axis("off")
plt.show()

# Display the result of Hough Transform
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```

---

## Expected Output

The program produces the following results:

1. Original input image
2. Grayscale image
3. Canny edge detected image
4. Hough Transform detected lines
5. Final image with detected lines highlighted in green

---

## Output

### 1. Input Image

> Add your input image here.

<img width="270" height="368" alt="image" src="https://github.com/user-attachments/assets/a8abbd0f-e1f5-4329-9904-9892169edd44" />



### 2. Grayscale Image

> Add your grayscale output here.

<img width="270" height="370" alt="image" src="https://github.com/user-attachments/assets/c84b0b2c-e666-4445-a6e9-ed89b0972107" />



### 3. Canny Edge Detector

> Add your Canny edge detection output here.

<img width="285" height="382" alt="image" src="https://github.com/user-attachments/assets/14209eb7-e940-4e7a-85fc-b07cafb3b509" />



### 4. Detected Lines

> Add your final Hough Transform output here.

<img width="279" height="379" alt="image" src="https://github.com/user-attachments/assets/0ada8273-9212-436c-aa88-a1e69ca9e944" />



---

## Result

Thus, the Hough Transform algorithm was successfully implemented using OpenCV. The system detects straight lines from the image using Canny edge detection and `HoughLinesP()` and highlights the detected lines on the original image.

---

## Developed By

**Name:** Sivakarthikeyan V
**Register No:** 212225220098
