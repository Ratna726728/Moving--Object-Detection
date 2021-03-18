Hey all! 
I wrote code to detect intruder using webcam or security cam. In this code, I have assign the modules which I am going to use that are OpenCV which is the module for
computer vision and another  module is winsound. For installing OpenCV in your system you have to run your cmd and write a instruction "pip install opencv-python" 
command and hit enter, so your package of Opencv has been download in your system. Winsound module is already downloaded in your system when you download python, so no
need to download winsound externally. So now our modules are ready to import.

After Importing modules, I have create a Cam object which stores data of captured image. So whenever, we call Cam it show us the captured image. Now, I have created a 
while loop and it will triggered when webcam is initialized. So, we have to see what webcam is showing us. For reading it we set a command called "ret, frame1=cam.read()"
and "ret, frame2=cam.read()". Here we assign two frames and this two frames are for creating difference.

Now the heart of this code will begin, from this two frames we take a absolute difference which show there is any movemnt or not and if yes then we find intruder. So, we 
take an absolute difference of image and after taking absolute difference we convert the colored image into grey scsle image for better result and after converting into grey
scale image we apply some blur effect. Blur effect create some guassian noise in image which will be further removed using thresolding. we set a threshold value by itrating them.
Here we have some noisy part after thresholding, for removing this noisy part we dilate the image. Now, we set contours to the dilated image. setting of contour is like when 
there is a distortion in dilated image then contour will show there is a movement in the image and when contour will detect any movement then it will generate a sound using
winsound module.  So the Flow of this code is as follow.

   Frame1,2--->Absolute difference---->grey scale image---->blured image---->thresholding----->dilatiom of image---->Contour to image----->alerting using beep sound.
             
In the end when we we want to shut the code, then we just press "x" as a exit statement.
