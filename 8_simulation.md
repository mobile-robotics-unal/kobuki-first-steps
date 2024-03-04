# Simulation

<!--
Modelado del robot real: Realizar el modelado del robot Kuboki y EV3, en coopeliasim.
-->

For the simulation of the kobuki in CoppeliaSim the team try using the reference drawings provided in the documentation but found them insuficient. Luckly the manufacturer provided acces to kobuki´s CAD models from which some measurement were taken in order to model the robot in coppelia.

![kobuki meassurements](https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/25491198/8a47bd42-9b4b-4d08-9e3d-8c261ee5776e)

A cylinder of 350 mm diameter and 75 mm height was used a the starting point for the base of the model. For the active wheels cylinders of 68.4 mm diameter and 20.6 mm height were used. these wheels were located 208 mm apart from each other and position in order to get a 12 mm clearence from the floor as specified in the documentation [](#references).  Under the dynamic properties they were configured as in copelia documentation in order to avoid the interference between the link members of the same object [1](#references). The acitve wheel were attach to the body through rotational joints. A pair of force sensors were used as stand in for the non-active wheels to generate the point of contact requiered for the stability of the platform as sugested in the documentation.

Finally for the visual appearance of the robot  2 mesh objects were imported one for the base of the platform and one for the top half. The dynamic properties of this objects were deactivated to not downgrade the performance of the simulation. The breakdown of the model in copeliasim can be seen the following image.


![Coppelia breakdown model](https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/25491198/3118438e-acb6-49a6-856d-af3a52655cc1)

After completing the model it was exported using the _saved as model_ option that Coppelia provides and was saved in the local library for easy access for future projects. This file is alos provide here [kobuki_simulation.zip](https://github.com/mobile-robotics-unal/kobuki-first-steps/files/14470914/kobuki_simulation.zip) for anyone to use. Mass properties were not configured yet to match the dynamic characteristics of the kobuki.


![image](https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/25491198/64a30bd9-8be5-4f0a-ae8d-bb1611534809)


## References 
1.  [coppeli bubbleRob Tutorial](https://manual.coppeliarobotics.com/en/bubbleRobTutorial.htm)

