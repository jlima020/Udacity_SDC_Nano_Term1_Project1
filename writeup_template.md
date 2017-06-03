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


[//]: # (Image References)

[image1]: ./test_images/solidWhiteRight.jpg "White lines"
[image2]: ./test_images/simple_line_noextrapolation.png "No extrapolation"
[image3]: ./test_images/Full_line_extrapolation.png "extrapolation"

---

## Reflection

### 1. Building the pipeline

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

<img src="/test_images/solidWhiteRight.jpg" width = "800" alt="White lanes" />



<img src="/test_images/simple_line_noextrapolation.png" width="800" alt="White lane no extrapolation" />



<img src="/test_images/Full_line_extrapolation.png" width="800" alt="White lanes with extrapolation" />


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
