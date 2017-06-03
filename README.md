#**Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

The Project
---

  This is the result of some hours of hard work, frustrations and success. Detecting lines on the road proved to be an exiting learning experience. Overcoming this challenge is defenitely a stepping stone in my carrer as a future autonomus car engineer.
  
  Part of the code has been provided by Udacity but you will find my contribution in the **_process_image_** function and in the 
 **_draw_line_** function. My python code style is not the most "_pythonic_" as I am still getting used to program in python, you can see is more "_C_" type of code but hey!, it gets the job done, I am confident that my python skills will improve ten fold in the comming month.
 
 The idea of this project is to detect the lane lines of the road using techniques of computer vision. The use of image gradients, the _canny edge detection algorith_ and the _hough transform algorithm_ are the main tools to accomplish this. These functions are part of _OpenCV_, which is also used to read and write images. The other part of the problem is to fit all these newly detected edges to a single line of the form y=mx+b, and is accomplished by collecting all the coordinates of these lines, filter them to be the left or right lane, and using _numpy_ functions, find the best fit for this points, meaning finding slope and intersect af a best fit line.

  I can only say that I learned a lot in a very short period of times. I had seen and used other transforms, like Fourier of Laplce, but never until this project I had heard of the Hough transform, and is a fundamental part of the line detection process. It is also my first time using numpy and OpenCV. I am not sure it could have been better.
  
  Feel free to read the code, use it, but follow my advice, do not copy and paste it, it will work but wont do you any good. It wont be until you scratch you head for days and read like a mad man from other peolpe's code, documentation, videos, that the beauty of solving the problem will benefit you.
