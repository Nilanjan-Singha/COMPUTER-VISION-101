# Week 1: OpenCV Basics & Introduction to Computer Vision

---

## Table of Contents
- [What is Computer Vision](#what-is-computer-vision)
- [Applications of Computer Vision](#applications-of-computer-vision)
- [Images and Videos](#images-and-videos)
- [Pixels, Intensity, and Channels](#pixels-intensity-and-channels)
- [Libraries Used](#libraries-used)
- [Loading and Displaying Images](#loading-and-displaying-images)
- [Color Spaces and Conversions](#color-spaces-and-conversions)
- [Drawing Shapes and Text](#drawing-shapes-and-text)
- [Image Arithmetic and Thresholding](#image-arithmetic-and-thresholding)
- [Image Filters](#image-filters)
- [Image Transformations](#image-transformations)
  - [Resize, Flip, Rotate](#resize-flip-rotate)
  - [Affine Transformation](#affine-transformation)
  - [Perspective Transformation](#perspective-transformation)
- [Video Operations](#video-operations)
  - [Capture from Webcam](#capture-from-webcam)
  - [Read Video Files](#read-video-files)
  - [Frame-wise Processing](#frame-wise-processing)
- [Coordinate System](#coordinate-system)
- [Saving Images and Videos](#saving-images-and-videos)


---

## PROJECTS WEEK 1 

### 1️⃣ **Color Space Explorer**

* **Goal:** Load an image or live webcam feed and allow switching between **BGR, Grayscale, HSV, LAB** interactively.
* **Skills:** Image reading, conversions, `cv2.imshow`, key press events.
* **Extra:** Display **channel splits** for each color space (like R, G, B or H, S, V).

---

### 2️⃣ **Drawing & Annotation Tool**

* **Goal:** Create a blank canvas or load an image and draw **lines, rectangles, circles, polygons, and text** using mouse events.
* **Skills:** `cv2.line`, `cv2.rectangle`, `cv2.circle`, `cv2.polylines`, `cv2.putText`, mouse callbacks.
* **Extra:** Add keyboard shortcuts to **change colors or shapes** dynamically.

---

### 3️⃣ **Live Webcam Filters**

* **Goal:** Apply real-time transformations to your webcam feed:

  * Grayscale
  * Invert colors
  * Reduce saturation
  * Simple brightness/contrast adjustment
* **Skills:** Webcam capture, color conversions, simple arithmetic operations on pixels.
* **Extra:** Add **toggle keys** to switch filters live.

---

### 4️⃣ **Face/Hand Annotation Demo**

* **Goal:** Load a face image or hand image and draw **bounding boxes** or **polygons** around detected regions manually.
* **Skills:** Coordinate system, rectangles, polygons, labeling with text.
* **Extra:** Combine with **Haar cascade** for face detection.

---

### 5️⃣ **Interactive Color Picker**

* **Goal:** Click on any pixel in an image and **display its color values** (BGR, HSV, LAB).
* **Skills:** Mouse events, `cv2.getMouseCallback`, color conversion.
* **Extra:** Draw a **color swatch** on the image showing the picked color.

---

### 6️⃣ **Polygon Drawing Tool**

* **Goal:** Click multiple points on an image to form a **polygon** and fill it.
* **Skills:** `cv2.polylines`, `cv2.fillPoly`, mouse callbacks.
* **Extra:** Allow **reset** and **save** the drawn shape.

---

### 7️⃣ **Webcam Snapshot with Overlays**

* **Goal:** Capture live webcam feed, overlay **timestamp, FPS, “REC” indicator**, and allow saving snapshots.
* **Skills:** `cv2.VideoCapture`, `cv2.putText`, `cv2.circle`, key events, saving images.
* **Extra:** Add **live shape drawing** over your feed before saving.

---

### 8️⃣ **Mini Art Generator**

* **Goal:** Combine **shapes, polygons, lines, and text** to create abstract digital art on a blank canvas or image.
* **Skills:** Drawing, colors, randomization.
* **Extra:** Save generated art automatically or create multiple frames for a GIF.

---




