##Some object detection model from OpenCV

ref : https://www.pyimagesearch.com/2018/07/30/opencv-object-tracking/

BOOSTING Tracker: Based on the same algorithm used to power the machine learning behind Haar cascades (AdaBoost), 
but like Haar cascades, is over a decade old. This tracker is slow and doesn’t work very well. 
Interesting only for legacy reasons and comparing other algorithms. (minimum OpenCV 3.0.0)

MIL Tracker: Better accuracy than BOOSTING tracker but does a poor job of reporting failure. (minimum OpenCV 3.0.0)

KCF Tracker: Kernelized Correlation Filters. Faster than BOOSTING and MIL. Similar to MIL and KCF, does not handle full occlusion well. (minimum OpenCV 3.1.0)

CSRT Tracker: Discriminative Correlation Filter (with Channel and Spatial Reliability). Tends to be more accurate than KCF but slightly slower. (minimum OpenCV 3.4.2)
MedianFlow Tracker: Does a nice job reporting failures; however, if there is too large of a jump in motion, such as fast moving objects, or objects that change quickly in their appearance, the model will fail. (minimum OpenCV 3.0.0)

TLD Tracker: I’m not sure if there is a problem with the OpenCV implementation of the TLD tracker or the actual algorithm itself, but the TLD tracker was incredibly prone to false-positives. I do not recommend using this OpenCV object tracker. (minimum OpenCV 3.0.0)

MOSSE Tracker: Very, very fast. Not as accurate as CSRT or KCF but a good choice if you need pure speed. (minimum OpenCV 3.4.1)

GOTURN Tracker: The only deep learning-based object detector included in OpenCV. It requires additional model files to run (will not be covered in this post). My initial experiments showed it was a bit of a pain to use even though it reportedly handles viewing changes well (my initial experiments didn’t confirm this though). I’ll try to cover it in a future post, but in the meantime, take a look at Satya’s writeup. (minimum OpenCV 3.2.0)

Writer's suggestion = 	Use CSRT when you need higher object tracking accuracy and can tolerate slower FPS throughput
			Use KCF when you need faster FPS throughput but can handle slightly lower object tracking accuracy
			Use MOSSE when you need pure speed
			
## By the look of it, original opencv models seem useless. Need to compare with YOLO

<img src ="https://pyimagesearch.com/wp-content/uploads/2018/07/opencv_object_tracking_cv_versions.jpg">
#########################################################################################################################
Opencv-python 3.x and 4.x is a mess. very hard to get it working. C++ versions seems to be bit better
anyway, i got my Rasbarry Pi 3B+ working after i have done following command through SSH:

sudo apt-get update && sudo apt-get upgrade
sudo apt-get install build-essential cmake pkg-config
sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install libfontconfig1-dev libcairo2-dev
sudo apt-get install libgdk-pixbuf2.0-dev libpango1.0-dev
sudo apt-get install libgtk2.0-dev libgtk-3-dev
sudo apt-get install libatlas-base-dev gfortran
sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103
sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
sudo apt-get install python3-dev

Then create a virtual environment using python 3.7. 
After that, 
pip install opencv-contrib-python==4.1.0.25

Existing issue, when trying to run detection with YOLO, the camera starts and then whole Pi just restarts. 
tried many time, no improvement.
############################################################################################################################
For reference, Tiny-YOLO achieves only 23.7% mAP on the COCO dataset while the larger YOLO models achieve 51-57% mAP, 
well over double the accuracy of Tiny-YOLO.
