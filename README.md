# 📸 Panorama Image Stitching with SIFT and RANSAC

## 💡 Overview
This computer vision project implements a robust pipeline for **Image Stitching**, transforming two overlapping images into a single, seamless panoramic view. The core challenge is addressed by using **Scale-Invariant Feature Transform (SIFT)** for feature detection and **RANSAC** for accurate image alignment, resulting in a robust system capable of handling minor image distortions and noise.

* **Skills:** SIFT, Feature Detection & Matching, Homography Estimation, RANSAC, Image Warping, Seamless Blending, OpenCV.

## 🔑 Key Methodology & Process
The panoramic image was created through a robust five-step process, designed to ensure both the accuracy of the alignment and the quality of the final composition:

1.  **Feature Extraction (SIFT):** **SIFT** was used to detect distinctive key points and descriptors that are invariant to scale changes and rotations, making the feature matching highly reliable.
2.  **Robust Matching (Lowe's Ratio Test):** Features were matched using a **Brute-Force Matcher**. The matches were then rigorously filtered using **Lowe's Ratio Test** (a threshold on the distance ratio between the best and second-best match) to retain only high-confidence correspondences.
3.  **Image Alignment (RANSAC):** The **Homography matrix ($H$)**—the geometric transformation required for alignment—was calculated using **RANSAC**. This iterative algorithm robustly rejects remaining outliers, ensuring the final transformation is precise, even in the presence of noise.
4.  **Warping & Composition:** The calculated Homography was applied to warp one image onto a large canvas, which was then composed with the second image.
5.  **Seamless Blending:** **Feather blending** (or similar linear blending) was applied in the overlap region to create a smooth, invisible transition between the two source images, resulting in a single, seamless output.

---

## 🖼️ Expected Result
*Showcase the final panorama image here. If the notebook won't render, upload the image separately and embed it.*

**Final Output:** A single, wide panoramic image with smooth transitions and accurate alignment, created from two source images.

## 💻 Files & Technologies

**Main File:** [`Image_Stitcher.ipynb`](./Image_Stitcher.ipynb) - *Please convert your HTML file back to this .ipynb format.*

**Dependencies:**
* Python
* OpenCV (cv2)
* NumPy
* Matplotlib

## 🚀 How to Run

```bash
# Clone the repository
git clone [https://github.com/YourUsername/Your-Portfolio-Repo.git](https://github.com/YourUsername/Your-Portfolio-Repo.git)
cd Panorama-Image-Stitching-SIFT

# Install required Python dependencies
pip install opencv-python numpy matplotlib jupyter

# Launch the notebook
jupyter notebook Image_Stitcher.ipynb
