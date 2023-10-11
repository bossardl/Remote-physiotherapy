Welcome to our AR-Physiotherapy project! This repository hosts a generative model tailored for in-home upper limb rehabilitation.
# Project overview 

Our project is dedicated to advancing the field of in-home physiotherapy by leveraging the power of Artificial Reality (AR).\
We've developed a system that utilizes human body pose tracking to provide an immersive experience for patients from their couch. 🚀📱

# AR-physiotherapy in SP - code.py

Generative model for rehabilitation of upper limbs at home.\
Human body pose tracking for the development of Artificial Reality (AR) in-home physiotherapy.\

**Color code:**
- :green_heart: Expected position for the exercise
- :heart: Need to move in the direction of the ➡️ to get to the right position


<div align="center">
  <img src="https://github.com/bossardl/Remote-physiotherapy/assets/90336628/a2842582-3669-4ab9-840a-92dc9c16e1ca.gif" alt="Upper limb rehabilitation at home" />
</div>

# HOW IT WORKS

In this setup, the patient's environment includes a visual representation of the ideal exercise position, which is displayed in the background. As the patient engages in their rehabilitation exercises, a color-coded system offers real-time feedback. This feedback is designed to assist the patient in adjusting their limb positions to meet the prescribed guidelines effectively.

Our goal is to make at-home physiotherapy more engaging, interactive, and ultimately more beneficial for patients. We invite you to explore the code and resources in this repository to learn more about our innovative AR-Physiotherapy project.

**Disclaimer:**

I own the code and the video. This is a research project conducted under the supervision of Pr. Cedric Pradalier at Georgia Tech Europe.

# PART 1  

Run real-time detection OpenPose on gpu (too slow on cpu) and run the code to validate the position in parallel.
To use real time detection directly with the camera, from my understanding, download OpenPose from Source.
Link to medium where the installation is detailled:
https://medium.com/pixel-wise/real-time-pose-estimation-in-webcam-using-openpose-python-2-3-opencv-91af0372c31c

# PART 2 
Run OpenPose on several sequence of image to directly run OpenPose and get an output .json (2D only working with my code).

# Getting started with OpenPose
1)HOW TO RUN OpenPose on Windows 	(detailed here: https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/installation/0_index.md)

2)DOWNLOAD OpenPose 
- <ins>for Windows:</ins>
unzip body_motion
code for gpu is in folder openpose-1.7.0-binaries-win64-gpu-python3.7-flir-3d_recommended in the zip file
- <ins>for Ubuntu:</ins>
git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose
cd openpose/
git submodule update --init --recursive --remote


3)CHECK Dataset_gpu

Train file exemple: '..\Dataset_gpu\Perso\Calibration\Train':
The same pose is registered for different persons.

Test file example: '..\Dataset_gpu\Perso\Calibration\Test':
 The same pose is registered for different persons with their eye closed 
In  '..\Dataset_gpu\Perso\Calibration\Test\Ludo', I perform whole other positions

Reference dataset '..\Dataset_gpu\Perso\Calibration\Train\Ludo'
Test dataset '..\Dataset_gpu\Perso\Calibration\Test\Ludo' 


4)RUN OpenPose

1. First change root directory
  - cd '..\openpose-1.7.0-binaries-win64-cpu-python3.7-flir-3d' 

2. Then run openpose in the directory above
  - bin\OpenPoseDemo.exe --image_dir '..\Dataset_gpu\Perso\Calibration\Train'  --write_json '..\openpose\output_json_folder\Train_Ludo'   
(You may need to create the repository  Train_Ludo if the algorithm doesn't create it itself)

