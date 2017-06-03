# Finding Lane Lines on the Road

## by Jorge F Lima

---
## Problem Statement.


**Finding Lane Lines on the Road**

Given a video stream, find the lane lines of the road 
using techniques of computer vision. 
For this:
* Build a pipeline for processing the video
* Output the result to a new video with the lane lines annotated


---

[image1]: /test_images/whiteLanes.png "New frame"
[image2]: /test_images/gray.png "Grayscale"
[image3]: /test_images/blur.png "Grayscale blur"
[image4]: /test_images/canny.png "Canny edges"
[image5]: /test_images/cannyWmask.png "Canny edges with mask"
[image6]: /test_images/hough.png "Hough with extrapolation"
[image7]: /test_images/houghNoExtrapolation.png "Hough with no extrapolation"
[image8]: /test_images/Full_line_extrapolation.png "Final result with extrapolation"
[image9]: /test_images/simple_line_noextrapolation.png "final result without extrapolation"
## Reflection

### 1. Building the pipeline

The pipeline consists of following a series of 5 steps.

First, get a new frame and convert it to grayscale using the helper function grayscale(img). 
The resulting output is shown below side by side.

![alt-text][image1] ![alt-text][image2]


Second, get the grayscale frame and apply gaussian blur using the helper function gaussian_blur(img, kernel_size). A kernel of size 5 was chosen to remove image noise using blur.

![alt-text][image2] ![alt-text][image3]


Fifth, the grayscale image with blur is passed to the canny edge detection function canny(img, low_threshold, high_threshold).
By trial en error, the low and high threshold values we selected as 50 and 150 respectively, following the 1:3 ratio rule. Output result is shown below side by side.

![alt-text][image3] ![alt-text][image4]

<img src="/test_images/simple_line_noextrapolation.png" width="800" alt="White lane no extrapolation" />



<img src="/test_images/Full_line_extrapolation.png" width="800" alt="White lanes with extrapolation" />


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
