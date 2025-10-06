## 🧮 IMAGE ARITHMETIC AND THRESHOLDING

### 🎨 IMAGE ARITHMETIC

Now, what do you mean by **image arithmetic**?
Well, just like how we add, subtract, multiply, or divide numbers — we can also do the same with **images**!

Since an image is basically a **matrix of pixel values**, performing operations on them changes how the image looks.

Imagine you’ve got two images like two transparent sheets — when you **add** them, both mix; when you **subtract**, the differences appear; and when you **multiply or divide**, brightness and contrast change.

---

### 🧩 Basic Operations

Let’s take two images of the **same size** for this (you can resize them using `cv2.resize()` if needed).

```python
import cv2
import numpy as np

img1 = cv2.imread('image1.jpg')
img2 = cv2.imread('image2.jpg')

# Resize to match dimensions
img1 = cv2.resize(img1, (500, 500))
img2 = cv2.resize(img2, (500, 500))
```

#### 1️⃣ ADDITION

```python
added = cv2.add(img1, img2)
cv2.imshow("Added Image", added)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

🧠 **What happens?**

* Each pixel’s values from both images are added.
* If it exceeds 255, OpenCV caps it at 255 (the max brightness).
* This brightens and merges both images.

---

#### 2️⃣ SUBTRACTION

```python
subtracted = cv2.subtract(img1, img2)
cv2.imshow("Subtracted Image", subtracted)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

🧠 **What happens?**

* Subtracts pixel values of `img2` from `img1`.
* Useful when you want to find **differences** — like detecting movement between frames.

---

#### 3️⃣ BLENDING

```python
blended = cv2.addWeighted(img1, 0.7, img2, 0.3, 0)
cv2.imshow("Blended Image", blended)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

🧠 **What happens?**

* You’re mixing two images by weights (70% of one + 30% of another).
* This is used for **fade effects**, **watermarks**, or **transition visuals**.

---

### ✂️ THRESHOLDING

Now, thresholding is where things start to look “computer vision-y” 🤖

Thresholding is used to **binarize** an image — meaning convert it into just **black and white**, based on intensity.

Think of it like this:

> “If a pixel’s intensity is above a certain value, make it white; else, make it black.”

---

### ⚙️ Basic Threshold

```python
import cv2

img = cv2.imread('image.jpg', 0)   # grayscale

_, thresh = cv2.threshold(img, 120, 255, cv2.THRESH_BINARY)

cv2.imshow("Original", img)
cv2.imshow("Thresholded", thresh)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

🧠 **Explanation:**

* `120` → threshold value
* `255` → max value (white)
* Anything **above 120** becomes **white**, else **black**

---

### 🧩 Types of Thresholding

| Method                  | Description                                 |
| ----------------------- | ------------------------------------------- |
| `cv2.THRESH_BINARY`     | Pixels > threshold → white; else → black    |
| `cv2.THRESH_BINARY_INV` | Inverse of above                            |
| `cv2.THRESH_TRUNC`      | Pixels > threshold → set to threshold value |
| `cv2.THRESH_TOZERO`     | Pixels > threshold → keep as is; else 0     |
| `cv2.THRESH_TOZERO_INV` | Inverse of above                            |

Example:

```python
_, binary = cv2.threshold(img, 120, 255, cv2.THRESH_BINARY)
_, binary_inv = cv2.threshold(img, 120, 255, cv2.THRESH_BINARY_INV)
_, trunc = cv2.threshold(img, 120, 255, cv2.THRESH_TRUNC)
_, tozero = cv2.threshold(img, 120, 255, cv2.THRESH_TOZERO)
_, tozero_inv = cv2.threshold(img, 120, 255, cv2.THRESH_TOZERO_INV)

cv2.imshow("BINARY", binary)
cv2.imshow("BINARY_INV", binary_inv)
cv2.imshow("TRUNC", trunc)
cv2.imshow("TOZERO", tozero)
cv2.imshow("TOZERO_INV", tozero_inv)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

### 🧠 ADVANCED: Adaptive Thresholding

Sometimes the **lighting** in an image is uneven, and one global threshold doesn’t work well.
Adaptive thresholding fixes this by calculating thresholds for small regions.

```python
adaptive = cv2.adaptiveThreshold(img, 255,
                                 cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                 cv2.THRESH_BINARY,
                                 11, 2)

cv2.imshow("Adaptive Threshold", adaptive)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

🧩 **Use case:** Document scanning, license plate detection, text extraction.

---

### 💡 MINI PROJECT: Combine Arithmetic + Threshold

> 📸 “Make an image blending + threshold tool”

**Idea:**
Create a program that takes two images, blends them using trackbars (slider), and lets the user apply a threshold on the blended output.

You’ll learn:

* Trackbars (`cv2.createTrackbar`)
* Image blending
* Threshold tuning interactively

---

