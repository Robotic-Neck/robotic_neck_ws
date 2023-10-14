# robotic_neck_ws
This is the ROS2  workspace for de robotic neck capstone project

TODO: add image

## Description
This repository is to organize the different ROS2 package and PlatformIO repositories necessaries to develop the robotic neck software. Any package has a description of the dependencies that you would need to work with it, make sure to check it after installing the workspace.

## Dependencies
* Operating system: [Ubuntu 22.04](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)
* Framework: [ROS2 Humble (desktop)](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)
* [launch_utils](https://github.com/MonkyDCristian/launch_utils) 

### Hardware
* Modern multi-core CPU
* At lest 4 Gb of RAM

## Install and Compile
Before install, make sure to source ROS2.

```
git clone https://github.com/Robotic-Neck/robotic_neck_ws.git
cd robotic_neck_ws/
git submodule update --init --recursive
```

If you dont have the [launch_utils](https://github.com/MonkyDCristian/launch_utils) dependencie, you can install it by:
```
cd robotic_neck_ws/src/
git clone https://github.com/MonkyDCristian/launch_utils.git
cd robotic_neck_ws/
colcon build --packages-select launch_utils
```

Now you can source your ws and buil it by
```
echo "source <path_to>/robotic_neck_ws/install/setup.bash" >> ~/.bashrc
source ~/.bashrc
colcon build
```

## Install ROS packages dependencies with rosdep

Install, init and update rosdep, in case you haven't
```
sudo apt-get install python3-rosdep
sudo rosdep init
rosdep update
```

Install dependencies  
```
cd robotic_neck_ws/
rosdep install -i --from-path src --rosdistro humble -y
```

## Demo 
```
ros2 launch caleuche_viz wam_v.launch.py
```

## Robotic Neck sub-modules

* [robotic_neck_driver](https://github.com/Robotic-Neck/robotic_neck_driver): ROS2 package to bringup the comunication between the platform and the computer`s user. it also contain a node to apply teleoperation by a PS4 controller.
* [robotic_neck_viz](https://github.com/Robotic-Neck/robotic_neck_viz): ROS2 package to visualize the robot kinematics with RVIZ for simulation or digital twin uses.
* [robotic_neck_control](https://github.com/Robotic-Neck/robotic_neck_control): ROS2 package to apply PID position control over the linear actuators for pitch and roll manipulation.
* [robotic_neck_micro_ros](https://github.com/Robotic-Neck/robotic_neck_micro_ros): PlatformIO repository to develop the microcontroller software with the Micro-ROS framework. 
  
## Documentation
TODO

## Guides
TODO
* [Documentation template]()
* [Add dependencies with rosdep]()

## Authors
* Cristian Nova (cristian.nova@uc.cl)
* Name 2 (TODO)
* Name 3 (TODO)
* Name 4 (TODO)
