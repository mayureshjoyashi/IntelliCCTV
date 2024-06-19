# IntelliCCTV

The goal is to have your Pi up and ready for development. It is okay to have any version of Raspbian OS on your Pi but make sure the version of OpenCV is 4.1 or greater. You can either follow the above tutorial to compile your OpenCV which will take hours but is more reliable for heavy projects or just install it directly from pip using the following commands.

$ pip install opencv-contrib-python==4.1.0.25

If you are installing OpenCV with pip for the first time, you have to install the other dependencies as well. Use the below commands for that.

$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev

$ sudo apt-get install libxvidcore-dev libx264-dev

$sudo apt-get install libatlas-base-dev gfortran

$ sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103

$ sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5

def create_camera (channel):
rtsp = "rtsp://" + rtsp_username + ":" + rtsp_password + "@" + rtsp_IP + ":554/Streaming/channels/" + channel + "02" #change the IP to suit yours
cap = cv2.VideoCapture(rtsp, cv2.CAP_FFMPEG)
cap.set(3, cam_width) # ID number for width is 3
cap.set(4, cam_height) # ID number for height is 480
cap.set(10, 100) # ID number for brightness is 10
return cap 

The create_camera function initializes a connection to an RTSP camera stream using OpenCV. It constructs the RTSP URL from given credentials and channel information, then opens the stream with cv2.VideoCapture using the FFMPEG backend. The function sets the camera's width, height, and brightness, returning the configured video capture object.

def read_camera ():
success, current_screen = cam1.read()
Main_screen [ , , :3] = current_screen
success, current_screen = cam2.read()
Main_screen[cam_height 2, , :3] = current_screen
success, current_screen = cam3.read()
Main_screen[, cam_width2, :3] = current_screen
success, current_screen = cam4.read()
Main_screen[cam_height2, cam_width 2, :3] = current_screen
return (Main_screen)


The read_camera function captures frames from four different cameras (cam1, cam2, cam3, cam4) and arranges them into a single Main_screen matrix. Each camera's frame is read and placed in a specific quadrant of Main_screen, creating a composite image of all four camera feeds. The function then returns the combined Main_screen.
