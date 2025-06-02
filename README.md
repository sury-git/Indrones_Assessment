# Indrones_Assessment
Image Processing and Computer Vision on two satellite images

This assessment has been done using python virtual environment.
* To make the virtual environment "pyhton -m venv myenv" 

All the dependencies are included in requirements.txt  
* To install dependency "pip install -r reuirements.txt"

 The objective is find changes between the two images, but following issues need to be addressed:
# "Exact" alignment of images.
 * Very first plot both the images side by side using pyplot from matplotlib. 
 * To check if both images have exact alignment
    * Very first check both image's shapes are same
    * Convert them to Grayscale
    * SHIFT is being used to detect keypoints and compute descriptors
    * Matching keypoints using FLANN 
    * Finally draw the matches (Visualize the images)
    * Homography matrix estimation (good matches) for Warp the image A and visualize the image

# Correcting for environmental factors (eg, time of day, season, haze/fog). 
 * The Contrast Limited Adaptive Histogram Equalization (CLAHE) algorithm to dehaze images and visualize the images with original images side by side to differentiate
 * Image filtering is applied which is a technique used to remove noise or enhance certain features in an image.
    * Three Filters is being used: 
        1. Gaussian Blur
        2. Median Blur
        3. Bilateral Filter
    Then again visualize the images
# (3) Finding "changes" and displaying them
## Compute absolute difference & Threshold the difference 
 * Dilate to enhance to find the contours of the changes and Draw bounding boxes on the original image
    The RED squared area is marked as absolute differences of images

# (4) Segmentation + classification of changes into classes.
 * A pre-trained model has been used for image segmentation
 * 'facebookresearch/dino:main', 'dino_vits16' above model is from torch mainly trained on satellelite images
 * This will plot (Highligted) the differences in both the images