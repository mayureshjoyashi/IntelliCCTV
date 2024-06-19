# IntelliCCTV

The goal is to have your Pi up and ready for development. It is okay to have any version of Raspbian OS on your Pi but make sure the version of OpenCV is 4.1 or greater. You can either follow the above tutorial to compile your OpenCV which will take hours but is more reliable for heavy projects or just install it directly from pip using the following commands.

$ pip install opencv-contrib-python==4.1.0.25
If you are installing OpenCV with pip for the first time, you have to install the other dependencies as well. Use the below commands for that.

$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
$ sudo apt-get install libxvidcore-dev libx264-dev
$sudo apt-get install libatlas-base-dev gfortran
$ sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103
$ sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
