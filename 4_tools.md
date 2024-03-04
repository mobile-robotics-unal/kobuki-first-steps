# Tools, Programming languages, libraries and APIs

<!--
APIs y lenguajes de programación: Identificar las APIs o librerías disponibles para programar los
robots. Enumerar los lenguajes de programación compatibles con los robots.
-->

Kobuki has a serial communication protocol to command the behavior of the robot. This allows the usage of any programming language that suports a serial interface as viable path to control the robot. However in practice a C++ library has been already implemented and works as the primary base for interacting with the robot with out the need to meddle with the protocol itself. Chapter 3 of the kobuki documention goes into detail on how to start working with the library and then Chapter 4 dives deeper on creating your applications [1](#references).


ROS packages have been build over this C++ library in order to integration into the ROS ecosystem. These where build for the ROS verisons: _groovy_, _hydro_, _indigo_ and _kinetic_; altough a work around is known to make it work in _noetic_.
These packages are composed by the following [4](#references):

- kobuki_bumper2pc 
- kobuki_capabilities 
- kobuki_controller_tutorial 
- kobuki_description 
- kobuki_keyop 
- kobuki_node 
- kobuki_random_walker 
- kobuki_rapps 
- kobuki_safety_controller 
- kobuki_testsuite


Despite a [repo](#references) showing support for the platform in ROS2, it is not active and lacking documentation so the it not well supported for the latest distros. 



## References
1. [kobuki Documentation](https://kobuki.readthedocs.io/_/downloads/en/stable/pdf/)
2. [kobuki C library repo](https://github.com/kobuki-base/kobuki_core)
3. [kobuki ROS wrapper repo](https://github.com/yujinrobot/kobuki)
4. [kobuki ROS documentation](https://wiki.ros.org/kobuki)
5. [kobuki ROS2 repo](https://github.com/kobuki-base/kobuki_ros?tab=readme-ov-file)
