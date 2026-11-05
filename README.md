# Edge-detection-using-opencv

### NAME : PRIYA B
### REG.NO : 212224230208

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

## Software Required

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## ⚙️ Algorithm

#### Step 1:
Import all the necessary modules for the program.

#### Step 2:
Load an image using cv2.imread().

#### Step 3:
Convert the image to grayscale.

#### Step 4:
Apply Sobel operator using OpenCV to detect edges.

#### Step 5:
Apply Prewitt operator using custom kernels.

#### Step 6:
Apply Roberts operator using custom kernels.

#### Step 7:
Apply Laplacian operator using OpenCV.

#### Step 8:
Apply Canny edge detector using OpenCV.

#### Step 9:
Display all edge-detected images for comparison.

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('pass.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

```
## Output

<img width="314" height="447" alt="image" src="https://github.com/user-attachments/assets/090074c1-76dd-424f-96bd-ef8bbb07cf29" />

<img width="320" height="410" alt="image" src="https://github.com/user-attachments/assets/80120220-39fb-4ebb-9397-62eb699bbb08" />

<img width="316" height="443" alt="image" src="https://github.com/user-attachments/assets/23945b49-3520-4043-b00c-9e4c7b4667d6" />

<img width="327" height="443" alt="image" src="https://github.com/user-attachments/assets/09b1678b-530e-4fa6-96f9-932b7ec4b878" />


## Result
Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
