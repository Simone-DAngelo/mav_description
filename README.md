# mav_description

This package contains different UAV models to simulate with Gazebo. The models use the [rotors_gazebo_plugins](http://wiki.ros.org/rotors_gazebo_plugins) and [px4_gazebo_standalone](>https://github.com/jocacace/px4_gazebo_standalone) to set/get information from the robot


## Models
### 3DR Iris
To start the iris quadrotor use the following launch file:

       $ roslaunch mav_description iris.launch
### Hummingbird
To start the hummingbird drone use the following launch file:

       $ roslaunch mav_description hummingbird.launch
### tilting Firefly
To start the tilting firefly drone use the following launch file:

       $ roslaunch mav_description firefly_tilt.launch
### Tilting coaxial octarotor
To start the NDT tilting drone use the following launch file:

       $ roslaunch mav_description ndt2.launch
To start the NDT tilting drone equipped with the 6 DoF manipulator use the following launch file:

       $ roslaunch mav_description ndt2_with_arm.launch

NB: don't forget to clone the manipulator model too: [arm_description]([http://wiki.ros.org/rotors_gazebo_plugins](https://github.com/Simone-DAngelo/arm_description.git ))      

NB: remember to add the apriltag textures to gazebo: https://github.com/koide3/gazebo_apriltag.git
I have modified the first one to be 10cmx10cm. Please find the modified models here: https://github.com/Simone-DAngelo/model_editor_models.git

The NDT drone propeller configuration is reported as follows:
		  
	UP	  CW (2)   ------------- CCW (1)
	         CCW (3)   ------------- CW (4)
	DOWN	 CCW (5)   ------------- CW (6)
	          CW (8)   ------------- CCW (7)	
	   
To get information from the UAV you can use the following topic:

	/ndt2/odometry, type: nav_msgs/Odometry
 
The pose is provided in NED frame

You can control each propeller of the UAV with a std_msgs/Float32MultiArray message on /ndt2/cmd/motor_vel topic.
Finally, you can tilt each propeller publishing a std_msgs/Float32 message on the rotor controller:

	/tilt_motor_1/command
	/tilt_motor_2/command
	/tilt_motor_3/command
	/tilt_motor_4/command
 

