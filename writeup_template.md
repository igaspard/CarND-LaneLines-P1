# **Finding Lane Lines on the Road** 

## Gaspard Shen

### Here is mine report for the Udacity Self Driving Car Nano Degree Project1.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidWhiteCurve.jpg "Example"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

First, according what I learn form the lesson, I converted the images to grayscale  Then apply the Gaussian smoothing before the Canny for better smooth edge. Third, apply the Canny Edge detection.
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by identify the value of slope positive or negative. Then decide the right and left lane lines. Then take group of left/right lines to use the cv2.fitLine to extrapolating the line from the lines by the hough transform. The result looks great. Here is the image after using the cv2.fitLine to extrapolating lines.
In the end, draw the left and right extrapolating line on the original images.

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when I run the chanllege.mp4.
I need to adjust the interest region manually according to this sence.
Need a better way to find out the interest region instead of manually adjust by hand.

Another shortcoming also find when running the chanllege.mp4.
Look like sometimes the left curve lane was not correct and not stable.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use information from past frames and have better result of the lane marking.
Calculate the interest region maybe depenping on the camera position at the car.

