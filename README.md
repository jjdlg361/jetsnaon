# To implement YoloV7 on a NVIDIA Jetson Nano B01 running Ubuntu 20.04 with an Intel Realsense D435 camera  

## How to set up the NVIDIA Jetson Nano

The steps taken are taken in a specific way of my choosing, however in some instances the choice for the software used may differ. In my case I will be doing this on my personal PC running Ubuntu 22.04. 

### Steps: 

1.Wipe micro sd card of all existing data. 

2.Download and install the OS. 

3.Adapt the downloaded repositories. 

4.Start NVIDA Jetson Naon. 

#### Step 1: 

Use your OS disk manager to wipe the exiscting data and format it respectively. 

As seen below will be formatting it for use in all systems. 




#### Step 2: 

In our case we will be using Ubuntu 20.04 for Jetson Nano. 

May be accessed at: https://github.com/Discombobulated88/Xubuntu-20.04-L4T-32.3.1/releases/download/v1.0/Xubuntu-20.04-l4t-r32.3.1.tar.tbz2 

Please download and extract the image file. 

We will be using balena to flash the micro-SD with Ubuntu. Please download it at https://www.balena.io/etcher/ , select the previously extracted disk image and flash the micro-SD using the program. This will take around 20 minutes. 

#### Step 3: 

 

Please note, there are two designs of the Jetson Nano, the A02 and B01. Ours is the B01 (900-13448-0020-000) as can be seen in the image, as a result we will require further steps as opposed to the A02 that shall skip to step 4. 

 

#### Step 4: 

 

