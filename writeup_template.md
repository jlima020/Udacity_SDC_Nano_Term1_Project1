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



[image1]: /test_images/lanes.png "New frame"
[image2]: /test_images/gray.png "Grayscale"
[image3]: /test_images/blur.png "Grayscale blur"
[image4]: /test_images/canny.png "Canny edges"
[image5]: /test_images/cannyWmask.png "Canny edges with mask"
[image6]: /test_images/hough.png "Hough with extrapolation"
[image7]: /test_images/houghNoExtrapolatiom.png "Hough with no extrapolation"
[image8]: /test_images/Full_line_extrapolation.png "Final result with extrapolation"
[image9]: /test_images/Full_line_noextrapolation.png "Final result without extrapolation"
## Reflection

### 1. Building the pipeline
---

The pipeline consists of following a series of 6 steps.

First, get a new frame and convert it to grayscale using the helper function *_grayscale(img)_*. 
The resulting output is shown below side by side.

![alt-text][image1] ![alt-text][image2]


Second, get the grayscale frame and apply Gaussian blur using the helper *_function gaussian_blur(img, kernel_size)_*. A kernel of size 5 was chosen to remove image noise using blur.


Third, the grayscale image with blur is passed to the canny edge detection function *_canny(img, low_threshold, high_threshold)_*.
By trial en error, the low and high threshold values we selected as 50 and 150 respectively, following the 1:3 ratio rule. Output result is shown below side by side.

![alt-text][image3] ![alt-text][image4]


Fourth, the image is masked to show only the area of interest, the road, using the *_region_of_interest(img, vertices)_* function.


Fifth, the masked image is passed to the *_hough_lines(img, rho, theta, threshold, min_line_len, max_line_gap)_* helper function
. This function returns an image with straight lines, drawn in red, that represent the position of the lane lines on the road. Various parameters have to be adjusted to try to produce an optimal result.


Lastly, the result of the hough transform is passed to the *_weighted_img(img, initial_img, α=0.8, β=1., λ=0.)_* that produces the frame with the annotations of the detected lines. The resulting output is shown below.

![alt-text][image7] ![alt-text][image9]


These results are not optimal. The goal was to draw only one line for the left and one for the right lanes that run continuously. This is achieved by modifying the *_draw_lines(img, lines, color=[255, 0, 0], thickness=7)_* function by gathering all coordinates points, and using the *_polyfit_* function from *_numpy_*, to calculate the slope of the line that best fit these coordinates. Making the *_y_* values fixed makes it possible to draw lines all the way to the edge of the frame, changing only the values of x based on the slopes calculated. The result of this is show below. It can be easily seen the improvement. The images to the right are the ones plotted using extrapolation.

![alt-text][image7] ![alt-text][image6]
![alt-text][image9] ![alt-text][image8]

### 2. Identify potential shortcomings with your current pipeline
---

The solution presented here has several drawbacks.

Trying to detect curved lanes on the road produces erratic results as can be seen in the challenge video output. 
Another shortcoming is the fact that changes in the lighting conditions and the contrast of the lanes with the pavement will likely result in no lane detection at all, due to the fact that the parameters for the *_canny_* and *_hough_* functions are hardcoded on the program and optimized for the specific conditions of the particular road on the videos. Another problem in the pipeline is with the lines jumping on the video, the transition between fram is not smooth.


### 3. Suggest possible improvements to your pipeline
---

A possible improvement to the pipeline would be implementing a 3rd degree polynomial fit of the lines. With this the curve detection and plotting wold likely be taking care of in part. Another improvement wold be using probabilities instead of linear fit to detect the lanes. Using an external array or ideally a small circular Q for keepeing track of slopes of the previous 5 to 10 frames would help with the smoothing of the lines by using recent previous data to calculate an average slope.
With respect to the changing lighting conditions and contrast of the lanes and pavement, using image enhancement and manipulations techniques would be a possible improvement
