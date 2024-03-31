#1 update
sudo apt-get update
sudo apt-get upgrade
sudo rpi-update

#2 Install the required developer tools and packages:

sudo apt-get install build-essential cmake pkg-config

#3 Install image I/O packages.
sudo apt-get install libjpeg8-dev libtiff4-dev libjasper-dev libpng12-dev

#4 Install the GTK development library. This library is used to build Graphical User Interfaces (GUIs) and is required for the highgui  library of OpenCV which allows you to view images on your screen:
sudo apt-get install libgtk2.0-dev
#5 Install the necessary video I/O packages.These packages are used to load video files using OpenCV:
Install OpenCV and Python your Raspberry Pi 2 and B+Shell

sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev

#6 Install libraries that are used to optimize various operations within OpenCV:

sudo apt-get install libatlas-base-dev gfortran

#7 Install the Python 2.7 development tools:

sudo apt-get install python2.7-dev

#8 Download opencv
sudo apt-get install build-essential git cmake pkg-config
sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt-get install libavcode-dev libavformat-dev libswscale-dev libv41-dev
sudo apt-get install libgtk2.0-dev
sudo apt-get install libatals-base-dev gfortran
cd
git clone https://github.com/Itseez/opencv.git
cd opencv
checkout 3.0.0
sudo apt-get update
sudo apt-get upgrade
sudo rpi-update
sudo apt install python3-opencv

#10 Install pi camera
pip install "picamera[array]"
#11 Install fswebcam
sudo apt install fswebcam

