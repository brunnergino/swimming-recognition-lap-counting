# Swimming Style Recognition and Lane Counting Using a Smartwatch

Code and data for our ISWC 2019 paper "Swimming Style Recognition and Lane Counting Using a Smartwatch"

## Paper

https://dl.acm.org/citation.cfm?id=3347719

## Code and Data

Our code and data can currently be found here: http://bit.ly/2VGEeWN 

We will update this repository with the code, a how-to and complete data description soon. 


### Data

Currently only the data as it is used to train our neural network is available. This data is pre-processed and labeled as described in the paper, and re-sampled at 30Hz. Each file consists of a header denoting the column names, and then one row for each timestamp. 

The header is is as follows:

timestamp,ACC_0,ACC_1,ACC_2,GYRO_0,GYRO_1,GYRO_2,MAG_0,MAG_1,MAG_2,PRESS,LIGHT,label,ACC_012,ACC_01,ACC_02,ACC_12,GYRO_012,GYRO_01,GYRO_02,GYRO_12,MAG_012,MAG_01,MAG_02,MAG_12

- timestamp is given in nanoseconds of uptime, i.e, how many nanoseconds have passed since the watch was booted up.
- ACC, GYRO, MAG, PRESS, LIGHT, stand for the accelerometer, gyroscope, magnetometer, pressure and light sensors readings respectively.
- The digits (0,1,2) behind ACC, GYRO and MAG stand for the (x,y,z) axes of these three sensors. 
- The columns with more than one digit (e.g., ACC_012) denote the L2-norm of the (x,y,z) accelerometer vector. These features were added during the earlier stages of the work, and are not used for training the neural networks. 
- The label denotes the ground truth annotation and takes a value in (0 1 2 3 4 5) which corresponds to the classes ('null', 'freestyle', 'breaststroke', 'backstroke', 'butterfly', 'turn')
- The label 0 (null) denotes any activity that is not swimming, such as resting between laps. For the paper we merged the 'null' and 'turn' classes into the 'transition' class

