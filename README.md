# Lane-line-detection-_base
# Finding Lane Lines On The Road
The goals of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report
# Reflection
# 1.Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
My pipeline consisted of 6 steps. First I convert the input image to grayscale type. Then it is blurred using Gaussian kernel. After that, canny edge is obtained from the image. A rough area of interest is determined to denote possible edges that could make up lane lines. Finally I use hough transform to obtain the lane lines and combine the line image into the original input image to form an output.
In order to draw a single line on the left and right lanes, I modified the draw_lines() function by grouping the detected lines into two main groups according to their slope. Then I use np.polyfit function to fit two major lane lines.
# 2. Identify potential shortcomings with your current pipeline
One potential shortcoming would be what would happen when there is some noise in the canny detection process. For example, in the optional challenge part, the shadow and front window of the car in the image would produce many fake cannies which would result in the failure of line fitting. Even though I use HLS channels to filter most of the region, it usually happens that some of the fake lines would be left and influent the lane line fitting.
# 3. Suggest possible improvements to your pipeline
A possible improvement would be to set the threshold of HLS channel dynamically according to every frame of video. Like someone suggests in the forum, we can calculate the number of lines in each group( left and right ) and tighten the threshold if there are too many lines picked after the line forming process in order to guarantee a decent lane line fitting.
