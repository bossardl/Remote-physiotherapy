# AR-physiotherapy
Human body pose tracking for the development of Artificial Reality (AR) in-home physiotherapy

# ################     PART 1    #####################

Run real-time detection OpenPose on gpu (too slow on cpu) and run the code to validate the position in parallel.
To use real time detection directly with the camera, from my understanding, download OpenPose from Source.
Link to medium where the installation is detailled:
https://medium.com/pixel-wise/real-time-pose-estimation-in-webcam-using-openpose-python-2-3-opencv-91af0372c31c

# #################     PART 2     #####################
Run OpenPose on several sequence of image to directly run OpenPose and get an output .json (2D only for now workin with my code).

# #################     Getting started    #####################
1)HOW TO RUN OpenPose on Windows 	(detailed here: https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/installation/0_index.md)

2)DOWNLOAD OpenPose 
<ins>for Windows:</ins>
unzip body_motion
code for gpu is in folder openpose-1.7.0-binaries-win64-gpu-python3.7-flir-3d_recommended in the zip file<
<ins>for Ubuntu:</ins>
git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose
cd openpose/
git submodule update --init --recursive --remote


3)CHECK Dataset_gpu

Train file exemple: '..\Dataset_gpu\Perso\Calibration\Train':
The same pose is registered for different persons.

Test file example: '..\Dataset_gpu\Perso\Calibration\Test':
 The same pose is registered for different persons with their eye closed (Can we see a difference?)
+ in  '..\Dataset_gpu\Perso\Calibration\Test\Ludo'  I perform whole other positions

Reference dataset '..\Dataset_gpu\Perso\Calibration\Train\Ludo'
Test dataset '..\Dataset_gpu\Perso\Calibration\Test\Ludo' 


4)RUN OpenPose

1. First change root directory
  - cd '..\openpose-1.7.0-binaries-win64-cpu-python3.7-flir-3d' 

2. Then run openpose in the directory above
  - bin\OpenPoseDemo.exe --image_dir '..\Dataset_gpu\Perso\Calibration\Train'  --write_json '..\openpose\output_json_folder\Train_Ludo'   
(You may need t ocreate the repository  Train_Ludo if the algorithm doesn't create it itself)

