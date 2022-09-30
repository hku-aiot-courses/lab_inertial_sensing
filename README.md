# IMU experiment
In the following experiment, you will get to know about inertial measurement unit (IMU), which is very common in our daily life. One vivid example is our smartphone. By containing an IMU, a smartphone can thus count your foot steps when you are walking or running. You can read more about IMU in [this article](https://en.wikipedia.org/wiki/Inertial_measurement_unit), or the given supplementary material.

## Experiment Conponents
### A. Raw data from IMU (10 points)
In this experiment, you will learn how to collect the raw data from IMU to do some analysis. The data is stored in a text file, where each line contains the following information:
```three-axis acceleration (m/s^2), three-axis angular velocity (rad/s), three-axis magnetic field```
By reading the supplementary material, you are able to understand the meaning of each data. You need to visualize that data and do a simple analysis.

##### 1. Read the data from your phone (2 points)
You need to collect the data from your phone. You can use HyperIMU, if you use an Android phone, or you can use app to collect the data and export it, if you use iPhone. The data should contains the following information:
```three-axis acceleration (m/s^2), three-axis angular velocity (rad/s), three-axis magnetic field```

##### 2. Initialize and analyze the data (3 points)
To obtain the initial state of the IMU, you have to put your phone on a flat surface and keep it still for a while. You need to calculate the mean value of the acceleration from three-axis, and further calculate the standard gavity at your place. Also, the varriance of acceleration, angular velocity and magnetic field should be calculated.
##### 3. Visualize the data (5 points)

### B. Step counting (30 points)
As mentioned above, the IMU can be used to count the foot steps. In this part, you will use the raw data to count the foot steps. You can just count the peak points or the cross-zero points from the absolute value of acceleration. The comparison of the prediction results and the ground truth is required. The unprecise results are to be expected, as the IMU has certain bias.
You are acquired to print the raw data, and the filtered data (you can use a low-pass filter to filter the data) in a platform.

##### 1. Calculate the absolute value of three-axis acceleration (10 points)
It is easy to calculate the absolute value of three-axis acceleration. A low-pass filter is required, as the walking cycle is about 300ms to 500ms.
##### 2. Count the foot steps (20 points)
You can just count the peak points or the cross-zero points from the absolute value of accelerations. It should be noticed that the part of data that starts and ends should not be considered.

### C. Moving trajectory (40 points)
In this part, you will use the raw data to calculate the moving trajectory of the IMU. By converting the IMU's own coordinate system to the ground coordinate system, the trajectory of a moving IMU can be cumulated with integral operation. You need to understand the concept of coordinate transformation and the concept of integral operation. You can refer to the supplementary material for more information. (It is common that the prediction results are quite different from what it should be like.)
##### 1. Coordinate transformation (10 points)
You need to understand the basic principle of **Quaternions**, which is a very important concept in coordinate transformation. By filling the code in the given template, you can get the transformation matrix from IMU's coordinate system to the ground coordinate system. You are able to obtain the acceleration and orientation of IMU from global coordinate. If you are unable to finish the code, you can use the processed data to do the following analysis, but you will get less points.
##### 2. Acceleration correction (10 points)
You need to eliminate the bias or drift from the obtaind acceleration, and then print the corrected acceleration, along with the original acceleration.
##### 3. Velocity update (10 points)
By integrating the corrected acceleration, you can get the velocity of the IMU. You are also acquired to print the velocity.
##### 4. Position update (10 points)
By integrating the velocity, and double integrating the acceleration, you can get the position of the IMU. You are also acquired to print the position.

**The above three experiments are fundamental and must be done by all of you. If you are not able to handle the extend experiment, which is the fourth part, it's OK to just finish three on them. And you will get almost 80 points if you do a good job.**

### D. Extend experiment (bonus)
If we do not conduct additional processing on IMU data, the step counting prediction we make will be quite different from the ground truth. In the fourth part of the project, you may try some mature methods to improve the calculation of step count or moving trajectory. For example, machine learning, or some filter algorithms (Kalman filter, butterworth filter), if you're familiar with signal processing. It should be noticed that this part will be graded in terms of experimental completness and accuracy, as well as the cross-sectional comparison with other groups.

***Let's start our trip with IMU***

### File Declaration

IMU release.pdf: an example of jupyter notebook output results

IMU tutorial.pdf: a brief introduction of IMU, including the coordinate tranformation and the integrated positions

IMU release.ipynb: the given code and the experiment requirement

step_counting data.zip: step counting datasets, mainly use the acce.txt and step.txt

Data collection.docx: tutorial of how to collect IMU data from your phone

### P.S.

Due to the limitation of time, the materials and documents of the experiment may be insufficient, your comments are welcome.