# YDLIDAR ROS2 Package Download and Build


## Step1: Create a ROS2 workspace, if there is no workspace, othereise Skip to Step2


### Linux
```	bash
mkdir -p ~/ydlidar_ros2_ws/src
cd ~/ydlidar_ros2_ws/src
```


## Step2: Clone ydlidar ros2 package
```bash
git clone https://github.com/dhrubasaha08/ydlidar_ros2
```


## Step3: Build ydlidar_ros2 package
```bash
cd ..
colcon build --symlink-install
```


## Step4: Configure LiDAR [paramters](params/ydlidar.yaml)
```yaml
ydlidar_node:
  	ros__parameters:
  		port: /dev/ttyUSB0
  		frame_id: laser_frame
   		ignore_array: ""
    		baudrate: 128000
    		samp_rate: 5
    		resolution_fixed: true
    		singleChannel: false    
    		auto_reconnect: true
    		reversion: true
    		isToFLidar: false
    		angle_max: 180.0
    		angle_min: -180.0
    		max_range: 10.0    
    		min_range: 0.01
    		frequency: 10.0
```
Note: How to configure paramters, see [here](paramters.md)


## Step5: Create serial port Alias[/dev/ydlidar]
```bash
chmod 0777 src/ydlidar_ros2/startup/*
sudo sh src/ydlidar_ros2/startup/initenv.sh
```
Note: After completing the previous operation, replug the LiDAR again.


## Step6: Run ydlidar_ros2 node

```bash
ros2 run ydlidar ydlidar_node
```
```bash
ros2 run ydlidar ydlidar_client
```
OR
```bash
ros2 launch ydlidar ydlidar_launch.py
```
```bash
ros2 run ydldiar ydlidar_client
```	 
OR 
```bash
ros2 topic echo /scan
```
