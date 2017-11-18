# IP Camera Ros Node


This is a ros node to publish the stream data from IP camera, you should configure your computer first for the cameras.



#### IP Camera Configuration
The IP camera router was configured as `192.168.3.100`, so do not configure your computer address as the address above.
  - Plug the internet cable into your computer
  - set up your computer IPv4 address as manual and set them to `192.168.3.[2-254]`
  - set up your mask as `255.255.255.0`
  - set up your gateway as `192.168.3.1`
  - ##### unplug your wire and replug it again
Now you are supposed to reconnect to the `LAN` and you are able to connect the camera at:
`http://192.168.3.100/mjpg/video.mjpg?camera=4`
here the `camera=4` is the camera connect to the axis box. Don't miss that.

### Run the script to test your connection
```sh
$ cd /to/directory/you/download/this/repository
$ python ./test_video_resource.py http://192.168.3.100/mjpg/video.mjpg?camera=4
```
The window will now pop up and show the stream directly

## Getting started with the provided code 

- Obtain and compile the assignment code and add it to your ROS environment: 
  - git clone `https://github.com/rancheng/IP_Camera_Stream_ROS.git`
  - cd IPCamera 
  - catkin_make (if problems, try again with -j1 flag)
  - echo source $(pwd)/devel/setup.bash >> ~/.bashrc 
  - source ~/.bashrc  ( must also be run in any previously opened terminals... or just close and re-open them )
- Launch the stream:
  - roslaunch video_stream_opencv ip_camera.launch
- In a new terminal window, start an image viewer:
  - rqt_image_view
  - In the top drop-down menu select "/ipcamera/result_image" to see your method's comparison to ground truth

