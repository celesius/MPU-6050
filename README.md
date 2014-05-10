MPU-6050
========

Basic MPU-6050 Arduino sketch of sensor function

Demonstrate  MPU-6050 basic functionality including initialization, accelerometer and gyro calibration, sleep mode functionality as well as parameterizing the register addresses. Added display functions to allow display to on-breadboard monitor. 
No DMP use. We just want to get out the accelerations, temperature, and gyro readings.
 
Runs on 3.3V 8 MHz Pro Mini and Teensy 3.1.

Added quaternion filter based on Madgwick's open-source sensor fusion algorithms. The MPU-6050 lacks a magnetic vector for absolute orientation estimation as is possible with the MPU-9150 or LSM9SD0, This algorithm allows estimation of quaternions and relative orientation, allowing output of Yaw, Pitch, and Roll which is subject to Yaw drift due to gyro bias drift. Despite the inclusion of a gyro bias drift correction component to the sensor fusion algorithm, Yaw drift is about  half a degree per minute orless, which is not too bad. In principle, Yaw should not be possible to estimate with only a single absolute reference (gravity down), yet this algorithm does a good job of estimating relative Yaw with good stability over short time scales.
