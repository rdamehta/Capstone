# Chest X-ray Classifier using Convolutional Neural Networks

<br>
<br>
<p align="center">
  <img src="https://github.com/rdamehta/Capstone/blob/master/readmeX.PNG" 
       width="200" height="250">
  <img src="https://github.com/rdamehta/Capstone/blob/master/readmeCHECK.PNG" 
       width="210" height="250">
</p>
<br>

<a id = 'over'></a>

## Table of Contents
- [Introduction](https://github.com/rdamehta/capstone#introduction)

- [Prerequisites](https://github.com/rdamehta/capstone#prerequisites)

- [Model Topology](https://github.com/rdamehta/capstone#model-topology)

- [Model Comparison and Results](https://github.com/rdamehta/capstone#model-comparison-and-results)

- [Final Thoughts and Future Considerations](https://github.com/rdamehta/capstone#final-thoughts-and-future-consideration)

### Introduction
Chest x-rays are one of the most ubiquitous medical imaging procedures and can reveal essential clinical information about a patient for physicians and medical proffesionals. The goal of this project was to build a model that could predict whether or not disease was present in an frontal Chest Xray using various convolutional neural networks 
#### Data
The ChestXnet Dataset was released in Fall of 2017 and gave the public access to over 100, 000 Chest Xrays image. The full dataset is available on [kaggle](https://www.kaggle.com/nih-chest-xrays/data), and the sample dataset of as well as a sample set of over 5000 Xrays is available [here](https://www.kaggle.com/nih-chest-xrays/sample/data).

There is also a csv available with each row corresponding to each image and each column either patient or image data corresponding to each image. The [csv](https://www.kaggle.com/nih-chest-xrays/data/downloads/Data_Entry_2017.csv/3) is also available on kaggle. 
### Prerequisite
- `pip install tensorflow`
- `pip install keras`
- `pip install sklearn` 
- `pip install pillow`
- `pip install opencv`
- `pip install numpy`
- `pip install pandas`

### Model Topology

**Topology of a simple CNN**
<p align="center">
  <img src="https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/Typical_cnn.png" 
       width="650" height="200">
  In this project the Simple CNN topology consisted of: 
  
    Conv2d 
    Pooling
    Conv2d
    Pooling
    Conv2d
    Flatten to Dense
    Dropout
    Dense(outputs)
  
  **MobileNet Topology**: mobilenets were designed to be used on android and ios platforms.
  <img src="https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/mobilenet.png"
       width="650" height="200">
  <img src="https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/mobile_net_table.png" width="400" height="400">
The full MobileNets network has 30 layers.

  **InceptionV3 architecture** 
  
  <img src = "https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/inceptionv3.png"
       width="650" height="200">
      
    
</p>



### Model Comparison and Results
### Final Thoughts and Future Consideration

## Current Progress:
Framing the problem as one that is solvable with binary classification. Currently the model classifies Anterior-Posterior and Posterior-Anterior Chest X-rays as 'No Findings' or Abnormal with Findings. 

Currently testing on CNN architecture consisting of 3 convolutional Layers, Dense layer, dropout layer, Dense layer. A very simple topology that my laptop with 16gb and a nvidea 940mx can handle. 

Grayscaling, resizing, and normalizing images to 128 x 128 and 256 x 256 using openCV and comparing with 256x256x3 channel images. This was done to fit everything in RAM.

Convolutional Neural Network Topologies compared:
- Simple Naive Model as described above
- MobileNet as Baselayer
- InceptionV3 as Base Layer

3 Different images inputs vs 3 different topologies.

As of now InceptionV3 does the best job at predicting abnormal xrays with an AUC ROC of .62. Transfer significantly improved the predictive abilites over a simple CNN topology.

## Future Considerations:
- Try other CNN topologies published in Literature
- Latest research is showing very deep CNNs perform very well at image recognition and object detection. Dense121 is an very deep CNN
- Try to detect individual pathologies aka mutlticlass multioutput task

