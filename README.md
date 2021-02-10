# Forca: ROS1 packages
This repo has code and config files related to the ROS1 parts of the forca project.


Note: at the moment ROS2 foxy is not supported on the xavier, so you will have to compile it from source.
Also note the [special build instructions](https://github.com/ros2/ros1_bridge/blob/master/README.md) for the ROS bridge.

## How to run the calibration

1) Start the camera trigger with:

```
roslaunch forca_ros1 set_camera_frequency.launch
```
Then set fps with;
```
roscd forca_ros1/src
./set_frame_rate.bash 5
```

2) Start the ROS2 camera drivers in the forca (ROS2) workspace
```
ros2 launch forca cameras.launch.py
```
3) Start the ROS1/ROS2 bridge
```
uros2
ros2 run ros1_bridge dynamic_bridge
```

4) Start the calibration:
```
roslaunch forca_ros1 calibration.launch
```
