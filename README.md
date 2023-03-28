# To implement YoloV7 on a NVIDIA Jetson Nano B01 running Ubuntu 20.04 with an Intel Realsense D435 camera  

## How to set up the NVIDIA Jetson Nano

The steps taken are taken in a specific way of my choosing, however in some instances the choice for the software used may differ. In my case I will be doing this on my personal PC running Ubuntu 22.04. 

### Steps: 

1.Wipe micro sd card of all existing data. 

2.Download and install the OS. 

3.Adapt the downloaded repositories. 

4.Start NVIDA Jetson Naon. 

5.Update and upgrade the system packages with apt-get.

6.Install PyTorch, OpenCV, and other required packages using pip.

7.Download the YOLOv7 repository by Ultralytics LLC.

8.Download the weights for YOLOv7.

9.Connect the Realsense D435 camera to the Jetson Nano via USB.

10.Run the object detection using YOLOv7 and Realsense D435 camera by executing a command in the terminal.

11.The output video stream will display the detected objects along with the corresponding bounding boxes, labels, and orientation angles.

12.Done

 <h3>Step 1:</h3> 

Use your OS disk manager to wipe the exiscting data and format it respectively. 

As seen below will be formatting it for use in all systems. 




 <h3>Step 2:</h3>

In our case we will be using Ubuntu 20.04 for Jetson Nano. 

May be accessed at: https://github.com/Qengineering/Jetson-Nano-Ubuntu-20-image 

Please download and extract the image file. 

We will be using balena to flash the micro-SD with Ubuntu. Please download it at https://www.balena.io/etcher/ , select the previously extracted disk image and flash the micro-SD using the program. This will take around 20 minutes. 

 <h3>Step 3:</h3>

 

Please note, there are two designs of the Jetson Nano, the A02 and B01. Ours is the B01 (900-13448-0020-000) as can be seen in the image, as a result we will require further steps as opposed to the A02 that shall skip to step 4. 

 


 <h3>Step 4:</h3>
<p>After completing step 2 and 3 (if applicable), insert the micro-SD card into the Jetson Nano and power it on.</p>
<h3>Step 5:</h3>
<p>Once the Jetson Nano has booted up, open the terminal and run the following commands:</p>
<pre>
sudo apt-get update
sudo apt-get upgrade
</pre>
<h3>Step 6:</h3>
<p>Next, we need to install PyTorch, OpenCV, and other required packages. Run the following commands:</p>
<pre>
wget https://nvidia.box.com/shared/static/5v5w9tc3wlq3t4w4tuc5lbma9rpa5hfj.whl -O torch-1.9.0-cp36-cp36m-linux_aarch64.whl
sudo apt-get install python3-pip libjpeg-dev libpng-dev libtiff-dev libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev libgtk-3-dev libcanberra-gtk*
pip3 install numpy torch-1.9.0-cp36-cp36m-linux_aarch64.whl
pip3 install opencv-python-headless==4.5.3.56
pip3 install pyrealsense2
</pre>
<h3>Step 7:</h3>
<p>Download the YOLOv7 repository by Ultralytics LLC. Run the following commands:</p>
<pre>
git clone https://github.com/WongKinYiu/yolov7.git
cd yolov7
</pre>
<h3>Step 8:</h3>
<p>Download the weights for YOLOv7. Run the following command:</p>
<pre>
wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt
</pre>
<h3>Step 9:</h3>
<p>Connect the Realsense D435 camera to the Jetson Nano via USB.</p>
<h3>Step 10:</h3>
<p>To run the object detection using YOLOv7 and Realsense D435 camera, execute the following command:</p>
<pre>
python3 detect.py --source 0 --weights yolov7.pt --conf-thres 0.4 --device 'cuda:0'
</pre>
<p>To stop the detection, press the q key.</p>
<h3>Step 11:</h3>
<p>The output video stream will display the detected objects along with the corresponding bounding boxes, labels, and orientation angles.</p>
<h3>Step 12:</h3>
<p>Congratulations! You have successfully set up.

