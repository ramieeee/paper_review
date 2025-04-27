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


### Dataset

### Algorithm

### Preprocessing


* place the object at certain position in y axis and random between 0 - 40 cm in x axis and measure every 2mm with ultrasonic sensor. 5mm is too much and miss out some information


### normalize
* 0-255 to 0-1 scale
* change input size and and change to grayscale



# 3. Key Point


# 4. Reflection
* Need to see many studies of ultrasonic about environmental conditions like roads, metals or materials
* Multiple object detection F1-score is too low. has limitation when addressing many objects for a single sensor
* y axis is not at random point. Need various position for x, y axis.

# 5. Reference
[1] 