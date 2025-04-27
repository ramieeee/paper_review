It is not all of a sudden that I was intrigued by the subject *Ultrasonic* scanning to detect objects or classify the objects. I once randomly thought about what I would choose for PhD paper if I had to go through PhD course, then ultrasound was the key idea that popped into my head. To strengthen the idea I was on the act to search the webs for papers then I found this.
My idea about *ultrasound* was this.

* has to be able to detect objects
* reads the environment and could tell it by the signal
* related to scanning the environment and able to visualize it
* low cost

Of course low cost for my personal project but it would be a different story if I were a part of the university in PhD course, which I am not, thus the cost matters.

I had a thorough review on this paper written by Turkish people, and according to this paper the authors belong to Defense Industries Research and Development Institute of Turkey, which gave me a belief that this paper would be meticulous and analytic.

# 1. Introduction
### Why Ultrasonic sensor?
* Low cost compared to LAIDAR
The most and critical reason for utilizing ultrasonic sensing is because of the cost. Compared to ultrasonic sensor, other sensors are quite heavy in terms of price, LIDAR for example is a great sensor with a stunning visualization and detecting objects around, yet is high in price and individuals have impediments to access to this.

* Useful when optical sensing is not possible
LIDAR, again, has the strength when the light can travel to objects. However, when optical sensing is disturbed by conditions such as weather or other factors, it may not be able to collect information from objects as there will be noise and the sensing tasks will not be fulfilled completely.

### Aim
The paper aims to contribute to provide with the methodologies of 1) object classification and 2) coordinate estimation with a single ultrasonic sensor, so to be utilized on robotic or human applications such as helmets scanning objects in real time

# 2. Proposed methods
### Data Collection
The authors placed the sensor on 3D printer for automated data collection. Every 2mm in X direction of the 3D printer, the data will be collected through ultrasonic sensor with 116 different scenarios.
### Dataset
3 objects with 3 classes were to be used for dataset: large object (40mm), medium object (20mm) and narrow object (10 mm)

![](objects_sensor.png)

The process of the ultrasound sensor is as below.
1. Transmitter sends the signal to objects
2. Receiver takes the signal and process the signal through amplifier
3. Digitalize the signal
4. Send digital data to USB

### Algorithm
CNN algorithm was applied to process the signal information. This was not a multi-modal model. Classic CNN model consists of 3 of 2D convolutional layers and 3 of max pooling layers, then flatten layer. Dense layer will take the vector feature and softmax will classify objects, and another dense layer will solve the linear regression for coordinates estimation.

### Preprocessing
Data was collected by placing the objects at certain position in y-axis, and random between 0 - 40 cm in x-axis and measure every 2mm with ultrasonic sensor. 5mm is too much and miss out some information.
The data then will look like a fluctuation on 2D graph where the object reflection is detected. Then envelope of the signal will be extracted from the raw data. When the two features are combined, a pillar-looking data shows on graph, seemingly very disheveled with a lot of noise.

![](wave.png)

![](envelope.png)

![](combination.png)
### Normalization
There are two normalization process.

* 0-255 to 0-1 scale
This is necessary on image preprocessing so the model will take inputs with values from 0 to 1 and will not have big values to save memory of the machine as well as to prevent from overfitting as the value could grow intimidatingly when MSE is applied for error calculation.

* Change input size and and change to grayscale
Size of the picture should be in a certain format such as 12 x 12 scale or other so the model will take the input accordingly. And also grayscale was applied to this algorithm.

# 3. Key Point
If divided into big categories, they will be as below.
* Data collection
* Data processing
* CNN to determine values

It focuses on CNN algorithm to perform multiple tasks and this differentiates the paper from other researches. Traditional CNN could perform such tasks with ultrasonic image data.

![](detection.png)

# 4. Reflection
The paper indeed is outstanding in details of how the data was prepared and the processing was done. It may be a barrier though, that if there is no knowledge about the sound waves, or graphs related to waves, and also the devices used for wave detection, this would be quite a handful paper to review. The paper introduces the modules and models of devices. Various kinds of these were new to me as I am not familiar with the sound wave or anything related to this domain.

I would need to see many studies of ultrasonic about environmental conditions like roads, metals or materials 

### Improvements
* Score
The model itself was great in detecting objects and estimating the coordinates of objects. However, multiple object detection F1-score was unexpectedly low, although the first object showed over 90%. From the second object to multiple objects, the score would significantly decrease that some would score 79% in F1-score. The score could be said the model is adequately reliable with such performance, but also the score shows that there is a handful amount of error that this may not be appropriate for adaption in industries.

* Number of Sensor
The aim of the paper is on the single-sensor algorithm. This was brilliant enough to show the possibility of object detection using only one ultrasonic sensor. However it has limitation when addressing many objects with a single sensor. As mentioned in the paper when Gaussian noise and salt-and-pepper noise were applied to the test dataset for real-world applications, the score would drop up to 70% for the third object. I strongly believe that using more sensors to this research will improve the quality of image processing and sensing data from the sensors.

* Test method
I noticed that the test was conducted by placing objects at a certain y-axis, which is not at random points. This could be the limitation of the suggested method. I would be more reliable if the test was conducted with various position for x, y axis.

# 5. Reference
[1] Karagoz A., Dindis G., _Object Recognition and Positioning with Neural Networks: Single Ultrasonic Sensor Scanning Approach_, Sensors 2025, 25(4), 1086, [https://doi.org/10.3390/s25041086](https://doi.org/10.3390/s25041086) (CC BY 4.0)