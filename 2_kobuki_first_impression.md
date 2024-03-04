# Kobuki First impression

<!--
TODO:
Presentación de los Robots: Descripción detallada de los robots Kuboki incluyendo sus carac-
terísticas físicas y capacidades
-->

## What is Kobuki?

Kobuki is a mobile robot platform developed by Yujin Robot, a South Korean company, designed for research, education, and development purposes.

The Kobuki platform consists of a wheeled base equipped with sensors and motors for autonomous navigation. It is commonly utilized in academic and industrial environments for tasks such as mapping, surveillance, and human-robot interaction.

## Physical features

The Kobuki has a circular shape with a radius of 354mm and a height of 89mm up to the top of the robot. Additionally, it can be fitted with a structure to hold equipment and peripherals, increasing the height of the robot up to 420mm.

<p align="center">
<img align="center" height="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/53503084/4cdffa0b-a1c2-4d47-b0cb-efb0394f6c9a">  
<img align="center" height="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/53503084/cf94b7a4-8848-419b-bf00-1b34cb73e350">  
</p>
[!NOTE]  
Taken from [Turtlebot](https://clearpathrobotics.com/turtlebot-2-open-source-robot/)


The Kobuki features a differential drive system with two main drive wheels and two passive wheels (one at the front and one at the back). The drive wheels are higher than the passive wheels, resulting in the robot typically balancing on three wheels. The two main wheels have a radius of 35mm and a width of 21mm.


<p align="center">
<img align="center" height="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/4e8fb1ca-c8e1-4fcf-bc12-22c30b3ee0d3">  
<img align="center" height="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/36fc64d3-e5af-419d-bfd5-8f964fa02e62">  
</p>
[!NOTE]  
Taken from [Kobuki Anatomy](https://iclebo-kobuki.readthedocs.io/en/latest/anatomy.html)

The Kobuki robot is equipped with bumpers and cliff sensors, essential safety features that prevent collisions with obstacles or falls from edges. Three bumpers detect contact with objects, while cliff sensors detect proximity to edges or drop-offs, positioned at the right, center, and left sides of the robot.




## Electrical features

### Frontal panel

The Kobuki's frontal panel is equiped with several connections and I/O functions:

* 19V/2A Molex output for laptop power supply.
* 12V/5A Molex output for arm power supply.
* 12V/1.5A Molex output for Kinect power supply.
* 5V/1A Molex output for gemneral purposes.
* Status LED:
    - Green: Battery at high voltage level.
    - Orange: Battery at low voltage level.
    - Green blinking: Battery charging.
* Two programmable LEDs.
* USB for data transmition.
* B0/1/2 programmable buttons.
* RS232 Serial port:
    - RX/TX serial data connection at 3.3V.
    - 4 x Digital inputs.
    - 4 x Digital outputs.
    - 4 x Analog inputs.
* Power adapter of 19V@3.16A


<p align="center">
<img align="center" height="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/53503084/4cf87f55-b01d-41fd-b5db-f70c7bbd7b4c">  
</p>
[!NOTE]
Taken from [Kobuki Anatomy](https://iclebo-kobuki.readthedocs.io/en/latest/anatomy.html)

## Functional features

* Maximum translational velocity: 70 cm/s
* Maximum rotational velocity: 180 deg/s
* Payload: 5kg 
* Cliff: will not drive off a cliff with a depth greater than 5cm
* Threshold Climbing: climbs thresholds of 12 mm or lower
* Rug Climbing: climbs rugs of 12 mm or lower
* Expected Operating Time: 3/7 hours 
* Expected Charging Time: 1.5/2.6 hours 
* Docking: within a 2mx5m area in front of the docking station


## References:

1. [Kobuki Docs](https://iclebo-kobuki.readthedocs.io/en/latest/index.html). Consulted: 03/03/2024
