How to Train your Raspberry Pi for Facial Recognition
Prepare: Raspberry Pi 3 or 4
         Power supply/microSD/Keyboard/Mouse/Monitor/HDMI Cable (for your Raspberry Pi)
         Webcam or picam
Set up camera:
   
    sudo raspi-config

    interface option -> legacy camera -> yes -> ok -> finish
 
    sudo reboot now
    
    sudo su
    
    sudo nano /boot/congig.txt

in line Automatically load overlays for detected cameras, mark # for camera_auto_detetec=1, writte start_x=1 in below line

scroll in end of page, change gpu_mem=128 to gpu_mem=256 

Ctrl o -> ok Ctrl x
     
     reboot

if you use webcam, run:
     
     sudo apt install fswebcam

if you use picam, run: 
 
     pip install picamera[array] 
     
    
Part 1: Install Dependencies for Raspberry Pi Facial Recognition

#1: To expand the swapfile, we will start by opening dphys-swapfile for editing:
 
    sudo nano /etc/dphys-swapfile

Once the file is open, comment out the line "CONF_SWAPSIZE=100" and add "CONF_SWAPSIZE=2048".

Press Ctrl-X, Y and then Enter to save your changes to dphys-swapfile.

    sudo systemctl restart dphys-swapfile

Install opencv(Readme_Install_opencv.txt)

#2. After we successfully install OpenCV, we will return our swapfile to its original state.

    sudo nano /etc/dphys-swapfile

Once the file is open, uncomment "CONF_SWAPSIZE=100" and delete or comment out "CONF_SWAPSIZE=2048"

Press Ctrl-X, Y and then Enter to save your changes to dsudo phys-swapfile.

    sudo systemctl restart dphys-swapfile

#3. Install face_recognition

    pip install face-recognition

#4. Install imutils

    pip install imutils
 
    pip3 install imutils

Part 2: Train the Model for Raspberry Pi Facial Recognition

#1.Open Terminal, we need to download source code 

    https://github.com/PearMiddleHieu/Face_detection.git

#2. From your Raspberry Pi Desktop Open your File Manager by clicking the folder icon
Right-Click within the dataset folder and select New Folder and set your name
    
otherway: in terminal command: cd /home/pi/facial.recognition/datashet 
                                   mkdir "name-file"

#3. Take picture
From facial_recognition folder 
   open "headshots.py" in thorny if you use webcam
 
   open "headshots_picam.py" in thorny if you use picam

in line 3 change name = "name-file" you have make in step 2
    
Run python code and when your camera start you need Press the spacebar to take photos of youself.

These photos will be used to train our model. Press Esc or End thorny when you have finished.

Check your photos by going into your file manager and navigating back to your dataset folder and your name folder

#4. training

In terminal

    cd facial_recognition

Run the command to train the model

    python train_model.py

If you get an error message saying imutils or face-recognition modules are missing, reinstall them using pip2 instead of pip

#5. let’s test the model we just trained

Run in command
    
    python face_rec.py

In a few seconds, your webcam view should open up

Congratulations! you have trained your Raspberry Pi to recognize your face

Press ‘q’ to stop the program