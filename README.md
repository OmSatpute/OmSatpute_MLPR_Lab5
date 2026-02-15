# MLPR_Lab5: Distance-Based Face Clustering and Classification

## Aim

The primary objective of this project is to implement a distance-based machine learning pipeline to detect faces in an image, extract meaningful features, and group them using clustering techniques. Additionally, the project demonstrates how to classify a new "template" image based on its proximity to established clusters in a feature space.

## Methodology

The workflow follows a standard computer vision and machine learning pipeline:

* **Image Pre-processing:** * Loading the faculty image and converting it to grayscale.
* Converting the image to the **HSV (Hue, Saturation, Value)** color space to isolate color information from brightness.


* **Face Detection:** * Utilizing the **Haar-Cascade classifier** (`haarcascade_frontalface_default.xml`) to detect faces within the image.
* **Feature Extraction:** * Calculating the **Mean Hue** and **Mean Saturation** for each detected face to create a 2D feature vector.
* **Clustering:** * Applying the **K-Means algorithm** () to group faces based on their color profiles.
* **Classification:** * Extracting features from a template image (e.g., Dr. Shashi Tharoor).
* Using the trained K-Means model to predict its cluster based on the **Euclidean distance** to the nearest centroid.



## Key Findings

<img width="1601" height="1079" alt="output1" src="https://github.com/user-attachments/assets/b9afa994-d817-4c4b-b315-f4f7deb5483e" />


<img width="1005" height="547" alt="output2" src="https://github.com/user-attachments/assets/dd0fb3df-29c1-4022-bc36-bf108c8af61b" />


<img width="1005" height="547" alt="output3" src="https://github.com/user-attachments/assets/42b441b1-a004-445e-8630-a648e18d891a" />


<img width="499" height="536" alt="output4" src="https://github.com/user-attachments/assets/ed993684-d961-4685-875a-8c30ec0550ce" />


<img width="1005" height="547" alt="output5" src="https://github.com/user-attachments/assets/df5615a7-81a6-462d-a805-bbc71d838ac0" />


<img width="1005" height="547" alt="output6" src="https://github.com/user-attachments/assets/34fe5b7d-1142-49d8-9fe9-8c926328f83a" />


### 1. Feature Space Representation

By utilizing Hue and Saturation, we successfully mapped high-dimensional image data into a simple 2D space. This visualization allowed us to see distinct groupings that standard RGB values might have obscured due to lighting variations.


### 2. K-Means Clustering Results

The algorithm effectively partitioned the faces into two clusters. The centroids represented the mathematical "average" face profile for each group.

* **Cluster 0 (Green):** Represented faces within a specific hue range.
* **Cluster 1 (Blue):** Represented faces with a different saturation profile.

### 3. Template Classification

The template image of Dr. Shashi Tharoor was successfully mapped into the feature space. By calculating the distance to the centroids, the model assigned it to the most similar cluster. This demonstrates the efficiency of Distance-based Classification for real-world applications.

## Conclusions

* **HSV over RGB:** The HSV color space is significantly more effective for color-based clustering as it is more robust to changes in lighting.
* **Distance Metrics:** Euclidean distance served as a reliable metric for determining similarity in a low-dimensional feature space.
* **The Power of K:** The choice of  is critical. while  was sufficient for this lab, a higher  could lead to **overfitting** by being too sensitive to minor feature variations.
