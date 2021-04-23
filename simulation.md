# Simulation

paper, tips, notes.

## PMSF

https://www.asam.net/members/detail/pmsf/

## Carla

https://carla.org/

* Carla is combine with CarSim (more at: https://carla.org/2020/12/22/release-0.9.11/)
* Abour CarSim: https://www.carsim.com/products/carsim/index.php
* Carla with RoS: ROS Bridge-CARLA experience (more at: https://carla.org/2020/12/22/release-0.9.11/)
* https://www.youtube.com/watch?v=AaJekfFR1KQ : Good tutorial showing CARLA toplevel: Unreal engine and a python client to get sensor data.

#### Tips

Low quality mode
```shell
./CarlaUE4.sh -quality-level=Low
```
Abbrevation
1. HUD: Head Up Display

## Autoware

https://www.autoware.ai/

https://github.com/Autoware-AI/autoware.ai

Autoware is the world's first "all-in-one" open-source software for self-driving vehicles. The capabilities of Autoware are primarily well-suited for urban cities, but highways, freeways, mesomountaineous regions, and geofenced areas can be also covered. The code base of Autoware is protected by the Apache 2 License. Please use it at your own discretion. For safe use, we provide a ROSBAG-based simulation environment for those who do not own real autonomous vehicles. If you plan to use Autoware with real autonomous vehicles, please formulate safety measures and assessment of risk before field testing.

You may refer to Autoware Wiki for Users Guide and Developers Guide.

![Autoware blocks](https://raw.githubusercontent.com/Autoware-AI/autoware.ai/master/docs/images/autoware_overview.png)

## LGSVL Simulator

https://www.lgsvlsimulator.com/

LGSVL Simulator: Simulation software to accelerate safe autonomous vehicle development


## CarMaker

## Video_Injection_Methods
https://ipg-automotive.com/fileadmin/user_upload/content/Download/PDF/Articles/1607-08_ATZworldwide_IPG_Automotive_Video_Injection_Methods_EN.pdf

## Formula Student: Simulink® and CarMaker
https://www.youtube.com/watch?v=M2x86MSZyXI

## CarMaker and ROS

### pycarmaker

https://github.com/gmnvh/pycarmaker

Python class to control, write and read information from CarMaker (https://ipg-automotive.com/).

If you are writing your application in C, use the APO library. Here is an example: https://github.com/gmnvh/pycarmaker/tree/master/examples/C
