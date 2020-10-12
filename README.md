# Moving Object Detection
<br>

Moving object detection is a technique used in computer vision and image processing. Multiple consecutive frames from a video are compared by various methods to determine if any moving object is detected. Moving objects detection has a wide range of applications like video surveillance, activity recognition, road condition monitoring, airport safety, monitoring of protection along marine border, etc. By acting segmentation among moving objects and stationary area or region, the moving objects motion could be tracked and thus could be analyzed later. To achieve this, consider a video is a structure built upon single frames, moving object detection is to find the foreground moving target(s), either in each video frame or only when the moving target show the first appearance in the video.


## Steps Involved
- Extract Background in Video Input

    -  Capturing the Video in 'cap' and extract 30 random frames and store the selected frames in an array
    -  Calculating median and average frames, for better outlier removal
 <br>
 
- Processing a Frame
    -  Studying a single frame separately (first frame)
    -  Converting the Median and sample image to grayscale
  <br>
  
- Background Removal : Performing Absolute Difference between gray_frame_sample and gray_frame_median to get the moving objects only, with the background removed
 <br>
 
- Blurring : Performing Gaussian Blur for noise reduction and to simplify edge detection
 <br>
 
- Binarizing the image - Thresholding : Performing Threshold and OTSU Threshold to bring the moving objects out clearly
 <br>
 
- Countour and Boundary Boxes

    -  Creating contours on the thresholded frame. Contours are curves joining continuous points in an image with same color intensity. We shall use cv2.RETR_EXTERNAL to fing the extreme outer contours and cv2.CHAIN_APPROX_SIMPLE to remove the redundant points.
    -  Creating Bounding Boxes (rectangular) for identified contours and display them on frame_sample
 <br>
 
- Compiling frames together for processing video

    -  Declaring output video to be created
    -  Creating cap and getting total frame count
    -  Running a Loop to go through all frames and process the Video

## Demonstration

![](Media/Detect.gif)
