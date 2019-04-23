# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

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

My pipeline consisted of 5 steps. 
- Convert the original image to grayscale
- Use Gaussian blurring to reduce image noise
- Use Canny edge detection to extract lane information
- Set a ROI to extract the lane area
- Use Hough linear detection to draw the lines

To draw a joint line on both left and right side, i created a new function draw_lines2() instead of the original one. Then i fitted the line and got its slope and intercept. According to the slope lines could be separated to left, if slope < 0; and right, if slope > 0. After that i fitted both left and right straight line with all the points on the left as well as right side, in order to obtain a left line and a right line. Afterwards I found the start point and the end point of them to draw the lanes. 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


- One of the shortcomings is that, the line recognition algorithms is not robust enough to detect the lanes at curves
- Another shortcoming would be that, several constants shall be replaced by parameters, in order to make the programme more flexible.


### 3. Suggest possible improvements to your pipeline

This pipeline works well on straight line however, is not capable to dealing with curves, so that a possible improvement will be to develop a new algorithms to solve this problem.
