# mav_description

This package contains different UAV models to simulate with Gazebo. The models use the [rotors_gazebo_plugins](http://wiki.ros.org/rotors_gazebo_plugins) and [px4_gazebo_standalone](>https://github.com/jocacace/px4_gazebo_standalone) to set/get information from the robot


## Models
### 3DR Iris
### Hummingbird
### Tilting quad
To start the tilting quad use the following launch file:

       $ roslaunch mav_description ndt2.launch
  
  The UAV works in cross configuration and the propeller configuration is reported as follows:
		  
		  CW (3)    ------------- CCW (1)
	          CCW (2)   ------------- CW (4)
To get information from the UAV you can use the following topic:

	/ndt2/odometry, type: nav_msgs/Odometry
The pose is provided in NED frame

You can control each propeller of the UAV with a std_msgs/Float32MultiArray message on /ndt2/cmd/motor_vel topic.
Finally, you can tilt each propeller publishing a std_msgs/Float32 message on the rotor controller:

	/tilt_motor_1/command
	/tilt_motor_2/command
	/tilt_motor_3/command
	/tilt_motor_4/command
 

