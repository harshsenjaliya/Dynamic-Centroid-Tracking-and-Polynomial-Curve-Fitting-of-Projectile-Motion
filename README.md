# Object Tracking and Centroid Detection 
This project focuses on extracting frames from a video, processing each frame to detect the centroid of a specified object, and visualizing the trajectory of the centroid over time using polynomial curve fitting. 
## Table of Contents 
- [Overview](#overview)
- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage) 
- [How It Works](#how-it-works)
- [Output Visualization](#output-visualization)

## Overview
The script uses OpenCV to read video files and extract individual frames. Each frame is processed to identify the centroid of an object based on pixel intensity values. 
The trajectory of the centroid is then fitted using a polynomial curve for visualization.

## Dependencies This project requires the following Python packages:
- `opencv-python`
- `numpy`
- `matplotlib`
- `google.colab` (for Google Colab users) To install these packages, you can use pip:
``` pip install opencv-python numpy matplotlib ```

## Installation 

1. Clone the repository:

 -``` git clone https://github.com/harshsenjaliya/object_tracking.git cd object_tracking ```

2. Install the required dependencies (if not using Google Colab).

 ## Usage
1. Mount your Google Drive to access the video file:
 
 -```python from google.colab import drive drive.mount('/content/drive', force_remount=True) ```
3. Specify the path to the video file and the output directory for frames:
 
 -```python video_path = '/content/drive/MyDrive/ENPM673/object_tracking.mp4' output_path = '/content/drive/MyDrive/ENPM673/frames' ```
5. Run the script. It will extract frames, process them to detect the centroid of the object, and visualize the results.

## How It Works 
1. **Frame Extraction:** The video is read frame by frame, and each frame is saved as an image in the specified output directory.
2. **Centroid Detection:** For each frame, the image is converted to grayscale, and pixel values below a certain threshold are identified to locate the object. The centroid is calculated based on the coordinates of the detected pixels.
3. **Polynomial Curve Fitting:** The detected centroid coordinates are fitted with a polynomial curve to analyze the trajectory over time. ## Output Visualization After running the script, a plot is generated displaying the detected centroid points and the fitted polynomial curve. The x-axis represents the horizontal pixel coordinates, while the y-axis represents the vertical pixel coordinates of the centroid.

-```python plt.scatter(val_dark[:, 0], val_dark[:, 1], c='g', marker='o') plt.plot(data_x, fitted_y) plt.xlabel('X') plt.ylabel('Y') plt.title('Centroid of the object') plt.gca().invert_yaxis() plt.show() ```

## Output Results
Below are the output results visualizing the centroid detection and the trajectory fitting:
![Description of Image 1](path/to/Centroid_pf_Obj...png)
![Description of Image 2](path/to/Curve_Traj._Plot.png)
