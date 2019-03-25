# **Project1: Finding Lane Lines on the Road** 

## Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 8 steps. 

1) Convert input image to grayscale, which is required for the edge detection
2) Run Canny edge detector
3) Determin the region of interest as a triangle for searching only on the road
4) Use Hough transformation to convert the edges within the ROI into lines
5) Allocate each line to the left or right lane and convert the lines into several points
6) Fit a line separately through the left and right lane points
7) Generate the starting and end point of the left and right lane
8) Mark the lanes in the original image


![alt text](/test_images_output/solidWhiteRight.jpg)


### 2. Identify potential shortcomings with your current pipeline


One shortcoming of the method is the decision if a line belongs to the left or right lane. Currently, this is only based on the angle, which is not always correct. Further, the lane is only described as a line, not as a curve.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to fit a curve through the lane points. In addition, the threshold for the canny detector could be lowered to get a better detection accuracy.
