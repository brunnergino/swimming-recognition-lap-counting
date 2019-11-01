# Swimming Style Recognition and Lane Counting Using a Smartwatch

Code and data for our ISWC 2019 paper "Swimming Style Recognition and Lane Counting Using a Smartwatch"

## Paper

https://dl.acm.org/citation.cfm?id=3347719

## Code and Data

Our code and data can currently be found here: http://bit.ly/2VGEeWN 

We will update this repository with the code, a how-to and complete data description soon. 


### Data
In the data directory, there is a separate folder for each of the 40 swimmers. Within each swimmer's folder, there is one file per recording session, labeled with the pre-dominant style and the Epoch time stamp. 

Currently only the data as it is used to train our neural network is available. This data is pre-processed and labeled as described in the paper, and re-sampled at 30Hz. Each file consists of a header denoting the column names, followed by the data-rows. 

The header of each file contains the following column names

,timestamp,ACC_0,ACC_1,ACC_2,GYRO_0,GYRO_1,GYRO_2,MAG_0,MAG_1,MAG_2,PRESS,LIGHT,label,ACC_012,ACC_01,ACC_02,ACC_12,GYRO_012,GYRO_01,GYRO_02,GYRO_12,MAG_012,MAG_01,MAG_02,MAG_12

- First column is an ID corresponding to the row ID of the pandas dataframe from which the text file was generated
- **timestamp**: nanoseconds of uptime, i.e, how many nanoseconds have passed since the watch was booted up
- **ACC_0, ACC_1, ACC_2**: X, Y, Z axes of the accelerometer sensor (Android sensor type: "TYPE_ACCELEROMETER")
- **GYRO_0, GYRO_1, GYRO_2**: X, Y, Z axes of the gyroscope sensor (Android sensor type: "TYPE_GYROSCOPE")
- **MAG_0, MAG_1, MAG_2**: X, Y, Z axes of the magnetometer sensor (Android sensor type: "TYPE_MAGNETIC_FIELD")
- **PRESS**: Ambient pressure sensor (Android sensor type: "TYPE_PRESSURE")
- **LIGHT**: Ambient light sensor (Android sensor type: "TYPE_LIGHT")
- **label**: Ground truth annotations. Values (0,1,2,3,4,5) corresponds to the classes ('null', 'freestyle', 'breaststroke', 'backstroke', 'butterfly', 'turn'). The label 0 (null) denotes any activity that does not belong to any of the four swimming styles, such as resting between laps. For the paper we merged the 'null' and 'turn' classes into the 'transition' class.
- **ACC_012, ACC_01, etc.** : The columns with more than one digit (e.g., ACC_012) denote the L2-norm of the (x,y,z) accelerometer vector. These features were added during the earlier stages of the work, and are not used for training the neural networks. 


