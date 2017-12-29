# Lane-line-detection-_base
# Finding Lane Lines On The Road
The goals of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report
# Reflection
# 1.Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
My pipeline consisted of 6 steps. First I convert the input image to grayscale type. Then it is blurred using Gaussian kernel. After that, canny edge is obtained from the image. A rough area of interest is determined to denote possible edges that could make up lane lines. Finally I use hough transform to obtain the lane lines and combine the line image into the original input image to form an output.
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by grouping the
