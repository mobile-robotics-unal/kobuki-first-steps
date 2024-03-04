# Identifing the sensors on the platform

<!--

Práctica de identificación y uso de los sensores integrados en los robots, explicando cómo interactúan
con el entorno.

-->

## Sensors

The Kobuki robot is equiped with the following sensors:
* Motor overload detection
* Bumpers
* Odometry
* Gyro
* Bumpers
* Cliff sensor
* Wheel drop sensor
* Docking sensor
* Batery sensor

All sensors works at 50 Hz data rate.

### Motor overload detection

The Kuboki's motor overload detection is designed to disable motor power when it detects excessive current. If the current exceeds a treshold arround 3A the Kobuki's control systems turn off the motors.

#### Causes
The motor overload detection is relevant specially when:
* Obstacules: The robot find an obstacule where it get trapped or it requires an excessive effort.
* Heavy load: When the load that the robot is carrying is too heavy that exceds the recommended wight. (5 kg in hard floor or 4 kg in carpet).
* Cleaning and Maintenance: Dust, dirt or debris can stuck the wheels causing an overload.

## Bumpers
The bumpers on the Kobuki are designed as contact sensors to detect physical collisions with objects in the robot's environment. When a collision occurs, the bumper sensors register the impact and provide crucial feedback to the robot's control system, enabling it to react appropriately to avoid potential damage or navigate around obstacles.

## Odometry
Odometry refers to the method used by the Kobuki to estimate its position and orientation based on the rotation of its wheels. By tracking the revolutions of its wheels using wheel encoders, the Kobuki can calculate its displacement relative to a starting position, allowing for precise navigation and mapping.
Can be used for localization, mapping or motion control.

## Gyro
The gyro sensor on the Kobuki measures the rate of rotation or angular velocity around its axes. This information is crucial for stabilizing the robot's orientation, compensating for external disturbances, and maintaining accurate control during motion.
Is used for stabilization, motion control and navigation


## Cliff Sensor
Cliff sensors on the Kobuki are designed to detect changes in surface elevation, such as cliffs, stairs, or ledges, to prevent the robot from falling or getting stuck in hazardous terrain. This sensor play a critical role in preventing the Kobuki from falling off edges or cliffs. By detecting abrupt changes in surface elevation, the sensors provide early warning of potential hazards, allowing the robot to adjust its trajectory or halt its motion to avoid dangerous drops.

## Wheel Drop Sensor
Wheel drop sensors on the Kobuki are designed to detect instances where one or more wheels lose contact with the ground, indicating potential issues such as wheel slippage, detachment, or obstruction.

## Docking sensor
The docking sensor on the Kobuki is a specialized sensor system designed to facilitate the precise alignment and docking of the robot with charging stations or docking stations. It enables the Kobuki to autonomously navigate to designated docking locations, ensuring seamless recharging or docking operations without human intervention.

## References
1. [Kobuki Docs](https://iclebo-kobuki.readthedocs.io/en/latest/index.html). Consulted: 03/03/2024
2. [ROS Kobuki documentation](https://wiki.ros.org/kobuki). Consulted: 03/03/2024