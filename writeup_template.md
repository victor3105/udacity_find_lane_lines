# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 8 steps. First, I converted the images to grayscale, then I used Gaussian blur to smooth the images. After that I found edges using Canny detector. The next step was to find lines in the images using Hough transform. Then I had to find the average for each obtained line and extrapolate those averaged lines. The final step was to draw extrapolated lines over the original images.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by finding lines with close slope and averaging them (functions calc_slope() and average_lines() are used). Then I extrapolated the averaged lines (function extrapolate_lines()). In order to extrapolate lines, I calculated x-values at the top and the bottom of ROI.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be that the approach is not universal and is sensitive to the light conditions changes.

Another shortcoming is that sometimes glare on the windshield is recognized as lane lines.

The accuracy of the lane lines recognition sometimes is insufficient.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to find a way to average lines more effectively.

Another potential improvement could be to decrease light conditions sensitivity using image enhancing techniques.
