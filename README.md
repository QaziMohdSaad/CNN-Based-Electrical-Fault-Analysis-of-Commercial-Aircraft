# CNN-Based-Electrical-Fault-Analysis-of-Commercial-Aircraft
In this reprository I am going to show my M.Tech Dissertation work whose title was " Artificial Inteeligence Based electrial Fault Analysis of Commercial Aircrfat which was done on MATLAB
# Problem Formulation:
Ensuring safe and efficient flights is dependent upon the reliable operation of electrical systems in commercial aircraft, as aviation safety is of utmost importance. Within this framework, Artificial Intelligence (AI) applications offer a potential fruitful path toward improving the electrical fault diagnostic procedure in commercial aircraft.
# Objectives:
•	Based on information gathered from onboard sensors, the Convolution Neural Network (CNN) model is used in commercial aircraft for electrical defect diagnostic.
•	Create, train and assess the suggested AI-based fault analysis system using the MATLAB.
# proposed work flow approach:
 1) ADAPT Simulink Model:
 2) Numeric Data:
 3) Modified Spectrogram Images:
 4) Traning of deep nerual model:
 5) Testing of deep nerual model:

## 1) ADAPT Simulink Model:
Advanced Diagnostics and Prognostics Testbed (ADAPT) is NASA Ames Research Centre. It is a open source model which means anyone can use it. Simulink Model of Virtual ADAPT mirrors the real-world hardware subsystems, including power generation, storage, and distribution, as described in the ADAPT testbed. This model serves as a crucial tool for analyzing the system's behavior under various operational scenarios and for testing the performance of different configurations of the electrical architecture

## 2) Numeric Data:
Numeric Data is generated from ADAPT Simulink Model with the help of GUI of Virtual ADAPT. Fault of sensors can be chosen and injected from the list of faults available in the “Component” menu. From the Virtual ADAPT GUI, fault injection time can be controlled. Modes of faults such as Gain, Nominal, Inception, Bias, and Stuck Condition can be chosen from the “Fault” menu. The amplitude of a fault can be adjusted from the “Magnitude” option. 

In this proposed work, 10 faults have been considered, and have been injected. The sensors sensing these faults are E235 (DC Voltage Sensor), EY160, EY175 (Relay Position Sensor), IT140, IT281 (DC Current Sensor), LT500 (Light Sensor), ST515, ST516 (Position Sensor), and TE128, TE501 (Temperature Sensor). The first simulation is run without any fault, then fault is introduced in the above ten mentioned sensors. 
![image](https://github.com/user-attachments/assets/1123ac70-ecb9-41b3-aba0-e9225f973feb)

## 3) Modified Spectrogram Images:
After generating numeric data from the simulation, the next step is to generate images from that data. In the presented work, modified spectrogram images are generated from the data. Spectrogram image are generated for each second of data i.e., 20 samples of 73 variables are taken to generate 1 spectrogram image, as there are 20 samples in 1 second. So there are a total of 600 images for each run of the simulation model. 
## Modified Spectrogram images of fault free is shown below:
![image](https://github.com/user-attachments/assets/94f5cfe2-665f-4910-9be2-de77c0cf8e1e)

## Modified Spectrogram images of EY160 fault is shown below:
![image](https://github.com/user-attachments/assets/451b64c2-fe23-4dec-be36-527481d4eb66)

## 4) Traning of deep nerual model:
The training obtained from the work are shown below. First, the SqueezeNET model is trained with 600 images of each simulation result. There are a total of 6,600 images, which are divided into a ratio of 70:30. 70% of the total images are for training and 30% of the remaining images are for validation. There are three epochs with 115 iterations each, so there are a total of 345 iterations. Validation is done after every 20 iterations. 
Initially, the model achieved a chance-level accuracy of approximately 10%, indicating random classification. However, as the training progressed, the accuracy steadily increased, ultimately reaching 100%. This substantial improvement demonstrates the effectiveness of the SqueezeNet architecture in learning and discriminating between different fault classes in the ADAPT system. Moreover, the loss profile demonstrated a corresponding reduction in training loss throughout the training iterations. The loss metric, which quantifies the discrepancy between predicted and actual fault labels, gradually approached zero, indicating a convergence of the model's predictions with the ground truth. This reduction in loss signifies the ability of the SqueezeNet model to effectively minimize classification errors and improve the accuracy of fault identification.

![image](https://github.com/user-attachments/assets/30c9ff10-b3d4-4cb9-98c4-522c451eeede)

![image](https://github.com/user-attachments/assets/55249722-b18f-4f74-b523-377f14a97c0c)

## 5) Testing of deep nerual model:
The model was tested with a dataset comprising 220 images, with 20 images for each of the eleven classes, representing various electrical fault conditions and the normal (unfaulty) condition in aircraft systems. These test images were distinct from those used during the training and validation phases, ensuring an unbiased assessment of the model's generalization capability. During testing, the model's performance metrics, including accuracy, sensitivity, specificity, precision, and F1 Score, were evaluated to assess its ability to correctly identify and distinguish between different classes of electrical faults and normal conditions. The confusion matrix provides a detailed breakdown of the model's predictions compared to the actual labels, highlighting the number of correct and incorrect classifications across all fault classes.

![image](https://github.com/user-attachments/assets/1bf464f6-47bd-4e78-a4bd-d72168750d98)

![image](https://github.com/user-attachments/assets/875ad545-bfa0-4155-84d4-819f3136ca78)


