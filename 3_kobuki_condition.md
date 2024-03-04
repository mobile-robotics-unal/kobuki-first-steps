# Status and overall condition of the plaform

<!--
TODO:
estado actual del robot y sistema de control.
-->
One of the most important aspects before working with a robot such as this, is to identify the current state of the equipment. For this special case, the following was checked:

* Robot chassis.
* Motors.
* Suspension mechanisms.
* Control system.
* Sensors (firstly physical conditions).

The team did a general check up of the ***Kobuki bot - Luna***, the porpouse of the general check up was identify each section of the robot. In the next image, the reader of this repositorie could apreciate the general condition of ***Kobuki bot - Luna***.

<p align="center">
  <img align="center" height="400" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/23eb0305-3fc8-49d4-a029-ee74bd10790b">
<p/>
  
In the inspection, the Kobuki was classified as a ***mobile robot with differential drive wheels with two free wheels***. This differential traction means that the control system allows the independent movement of each of the wheels, thus guaranteeing the description of different trajectories on the plane. Also this robot or robotic base has a structurally coupled base on which different elements such as auxiliary sensors and laptops can be supported.
The next step in the review was to verify the physical state of each part of the robot and also if the ***Kobuki bot- Luna*** could move with its default program, for this it was necessary to run a default walking mode built into the Kobuki firmware _(R. Ramirez, P. Cárdenas, 2024)_.

## Chassis condition.

The base of the kobuki appears to be in good condition, with no significant dents or scratches. The external support structure coupled to the robotic base does not present corrosion or deviations on the structural bars, nor are fastening elements missing. Likewise, the elements such as traction wheels, free wheels and the three identified bumpers are assembled according to what is indicated in the robot manual without alterations to it.

* Isometric top and bottom view _(D. Stonier, 2020)_.

<p align="center">
<img align="center" height="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/4e8fb1ca-c8e1-4fcf-bc12-22c30b3ee0d3">  
<img align="center" height="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/36fc64d3-e5af-419d-bfd5-8f964fa02e62">  
<p/>

## Wheels and suspension mechanism condition.

Both differential drive wheels are in optimal conditions; through visual inspection, no deviations or wear are observed. However, considerable surface wear occurs on the two removable freewheels.

<p align="center">
<img align="center" width="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/ed08be8c-1248-41aa-9dd8-2677f5d6fa8c"> 
  <img align="center" width="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/0c5e3042-bf97-4050-bac7-c6232042a127"> 
<p/>


The suspension system did not present any anomalies. For this, a simple test was carried out. Each wheel was pressed radially so that it reached its minimum height and returned without problems to its original position. The results were satisfactory, no oscillating behaviors were observed but rather damped ones, which allows the system to have minimal disturbances during the path taken by the robot.

<p align="center">
<img align="center" width="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/a5401bc9-a39d-4c14-8760-ebd8b9deb941"> 
<img align="center" width="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/e3912ccf-45ff-4c00-95eb-96f07f72908c"> 
<p/>

## Control system, power supply and move.
The system control panel and battery are physically in good condition. However, as previously stated, a predetermined test was performed. In this test the robot only walked in a straight line until one of the bumper sensors detected a hit. The LEDs turned on as expected, following the robotic base manual.

<p align="center">
<img align="center" width="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/14eab4b5-036b-4acb-acfa-00ee7a322c9e"> 
<img align="center" width="250" src="https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/2c4ea4f5-2a3f-40a1-b95c-3acc6da04164"> 
<p/>

To test the default program, the following steps were performed:
1. The robot was placed on the ground, ensuring that there were areas of fall or unevenness.
2. The power button was pressed.
3. Approximately 3 seconds later, button B0 is held down for 2 seconds. After 2 seconds the robotic base will execute the default program.


## References
1. Ramírez, Ricardo and Cárdenas, Pedro. _Guía 2a Introducción al framework ROS_. Fundamentos de robótica móvil. Departamento de Ingeniería Mecánica y Mecatrónica. Universidad Nacional de Colombia. Bogotá, Colombia, 2024.
2. Ramírez, Ricardo and Cárdenas, Pedro. _Guía 2b Introducción al robot Kobuki_. Fundamentos de robótica móvil. Departamento de Ingeniería Mecánica y Mecatrónica. Universidad Nacional de Colombia. Bogotá, Colombia, 2024.
3. Daniel Stonier. _Kobuki Documentation (Release 1.0.0)_. 2020.
