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

In the next video of the first homework of the course, the reader of this repository could see a simple simulation using (inverse cinematics).



https://github.com/mobile-robotics-unal/kobuki-first-steps/assets/161974694/e7decc99-74c2-463f-a6b3-094dbec19438

For this simulation the team use MATLAB with CoppeliaSIM (Vrep), the MATLAB code is:

```matlab
%% Simulación robot con ruedas - Fundamentos de Robótica móvil
% Universidad Nacional de Colombia - Sede Bogotá (2024-1S)
% Equipo 1: Kobuki
% Daniel Esteban Molano Garzón
% Camilo Esteban Zambrano Pereira
% Cristhian Sandoval
% Juan Sebastián Dueñas

%% Programa para el caso 1

%Programa para verificar el uso de handles y desde MATLAB leer variables en Coppelia Sim.
%Establecer la conexión
vrep=remApi('remoteApi'); % usar el archivo prototipo (remoteApiProto.m)
vrep.simxFinish(-1); % si se requiere, cerrar todas las conexiones abiertas.
% asigna el handle de identificación de cliente clientID
clientID=vrep.simxStart('127.0.0.1',19999,true,true,5000,5);
if (clientID>-1)
    disp('Conexión exitosa')
end
%Algoritmo
% Consulta el handle del objeto Caja1 en la escena Esc01 y lo asigna al handle caja_m.
[returnCode,kobuki_m]=vrep.simxGetObjectHandle(clientID,'kobuki',vrep.simx_opmode_blocking);

% Ruedas
[returnCode,wR]=vrep.simxGetObjectHandle(clientID,'jointR',vrep.simx_opmode_blocking);
[returnCode,wL]=vrep.simxGetObjectHandle(clientID,'jointL',vrep.simx_opmode_blocking);

r= 0.0684/2;                        %Radio de las ruedas motrices [m]
l= 0.1025;                          %Distancia del centroide del robot a la rueda [m]
vel_ang = 10;                       %Velocidad angular de la rueda 1  [rad/s]
vel_lin = vel_ang*r;                %Velocidad lineal del robot[m/s]
x = 4;                              %Distancia a recorrer [m]
d_duration = x/vel_lin;             %Duración del recorrido [s]

% Calculo de la velocidad angular de las ruedas a partir del jacobiano del
% sistema y la velocidad angular objetivo
vel_rotation = [1/r l/r;1/r -l/r]*[0; pi/2];

disp("d_duration: "+ d_duration)

vrep.simxGetPingTime(wR)
vrep.simxGetPingTime(wL)
% Se establece la posición y orientación inicial del robot
Pos_ini=[2,2,0.0445];
Or_ini=[0,0,pi/2];
[returnCode]= vrep.simxSetObjectPosition(clientID, kobuki_m,-1,Pos_ini,vrep.simx_opmode_blocking);
[returnCode]=vrep.simxSetObjectOrientation(clientID,kobuki_m,-1,Or_ini,vrep.simx_opmode_blocking);
% Bucle para definir el movimiento del robot
for c = 1:4
    vrep.simxSetJointTargetVelocity(clientID, wL, vel_ang, vrep.simx_opmode_oneshot);
    vrep.simxSetJointTargetVelocity(clientID, wR, vel_ang, vrep.simx_opmode_oneshot);
    pause(d_duration);
    vrep.simxSetJointTargetVelocity(clientID, wL, 0, vrep.simx_opmode_oneshot);
    vrep.simxSetJointTargetVelocity(clientID, wR, 0, vrep.simx_opmode_oneshot);
    pause(1)
    vrep.simxSetJointTargetVelocity(clientID, wL, vel_rotation(1), vrep.simx_opmode_oneshot);
    vrep.simxSetJointTargetVelocity(clientID, wR, vel_rotation(2), vrep.simx_opmode_oneshot);
    pause(1)
    vrep.simxSetJointTargetVelocity(clientID, wL, 0, vrep.simx_opmode_oneshot);
    vrep.simxSetJointTargetVelocity(clientID, wR, 0, vrep.simx_opmode_oneshot);
    pause(1)
end
vrep.simxSetJointTargetVelocity(clientID, wR, 0, vrep.simx_opmode_oneshot)
vrep.simxSetJointTargetVelocity(clientID, wL, 0, vrep.simx_opmode_oneshot)

[returnCode,P]=vrep.simxGetObjectPosition(clientID,kobuki_m,-1,vrep.simx_opmode_blocking);

disp('Programa terminado')
vrep.delete(); % llama el destructor!
```

## References 
1.  [coppeli bubbleRob Tutorial](https://manual.coppeliarobotics.com/en/bubbleRobTutorial.htm)

