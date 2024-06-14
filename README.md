# YDLIDAR ROS2 PACKAGE V1.4.5

## How to [install ROS2](https://index.ros.org/doc/ros2/Installation)
[ubuntu]()

[windows]()

## How to Create a ROS2 workspace
[Create a workspace]()

## How to build YDLIDAR ros2 package
Note: Download and Build details [here](docs/ydlidar.md)

## How to run YDLIDAR ros2 package

### 1. Run YDLIDAR node and view using test application
```bash
ros2 run ydlidar ydlidar_node
```
```bash
ros2 run ydlidar ydlidar_client
```
Note: You should see YDLIDAR's scan result in the console

### 2.Run YDLIDAR node and view using test application by launch

```bash
launch
(ros2 pkg prefix ydlidar)/share/ydlidar/launch/ydlidar.py
```
OR
```bash
ros2 run ydldiar ydlidar_client 
```
OR
```bash
ros2 topic echo /scan
```
OR
```bash
ros2 launch ydlidar ydlidar_launch.py
```

## Dataset
|LIDAR      | Model  |  Baudrate |  SampleRate(K) | Range(m)  		   |  Frequency(HZ) | Intenstiy(bit) | SingleChannel | voltage(V)|
| :-------- |:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| X4        | 6	   |  128000   |   5            |  0.12~10     		| 5~12(PWM)      | false          | false    	  | 4.8~5.2   |
| X2/X2L    | 6	   |  115200   |   3            |  0.10~8.0     	| 4~8(PWM)       | false          | true    		  | 4.8~5.2   |

Note: PWM option speed control requires external PWM wave.

## Configuration
[ydlidar.yaml](params/ydlidar.yaml)

## ros2-interfaces

<center>

| Topic                | Type                    | Description                                      |
|----------------------|-------------------------|--------------------------------------------------|
| `scan`               | sensor_msgs/LaserScan   | 2D laser scan of the 0-angle ring                |

| Parameter         | Type                    | Description                                         |
|-----------------------|------------------------|-----------------------------------------------------|
| `port`        		| String                 	| port of lidar (ex. /dev/ttyUSB0)                         		|
| `baudrate`     	| int                      	| baudrate of lidar (ex. 128000,115200)           				|
| `frame_id`      	| String                	| TF frame of sensor, default: `laser_frame`    		|
| `singleChannel`  	| bool                     	| Whether LiDAR is a single-channel, default: false	|
| `resolution_fixed` | bool                     	| Fixed angluar resolution, default: true                    	|
| `auto_reconnect` | bool                  	| Automatically reconnect the LiDAR, default: true    	|
| `reversion`     	| bool                  	| Reversion LiDAR, default: true  					|
| `isToFLidar`       	| bool                  	| Whether LiDAR is TOF Type, default: false  		|
| `angle_min`       	| float                 	| Minimum Valid Angle, defalut: -180.0     			|
| `angle_max`       	| float                  	| Maximum Valid Angle, defalut: 180.0      			|
| `range_min`       	| float                  	| Minimum Valid range, defalut: 0.01m      			|
| `range_max`       	| float                  	| Maximum Valid range, defalut: 64.0m      			|
| `ignore_array`      | String                  	| LiDAR filtering angle area, default: ""      			|
| `samp_rate`       	| int                  	| sampling rate of lidar, default: 9      				|
| `frequency`       	| float                  	| scan frequency of lidar,default: 10.0      			|

</center>

## Parameters
port (string, default: /dev/ydlidar)

`serial port name used in your system. `

baudrate (int, default: 128000 or 115200)

`serial port baud rate.`
    
| LiDAR                					| baudrate               | 
|-----------------------------------------------|-----------------------|
|X2 		| 115200			|
|X4                   					| 128000			|

frame_id (string, default: laser_frame)

`frame ID for the device.`

singleChannel (bool, default: false)

`indicated whether the LIDAR is single communication(X2) lidar.`
    
| LiDAR                							| singleChannel       | 
|-----------------------------------------------------------|-----------------------|
|X4 	| false			|
|X2                   						| true			|

resolution_fixed (bool, default: true)

`indicated whether the LIDAR has a fixed angular resolution.`

auto_reconnect (bool, default: true)

`indicated whether the LIDAR auto reconnection.`

reversion (bool, default: false)

`indicated whether the LIDAR data rotation 180°.`
    
| LiDAR                								| reversion              | 
|-----------------------------------------------------------------|-----------------------|
|X2/X4                   			| false			|


isToFLidar (bool, default: false)

`indicated whether the LIDAR is TOF(TX8) lidar.`
    
| LiDAR                									| isToFLidar             | 
|-----------------------------------------------------------------------|-----------------------|
|X4/X2 	| false			|


angle_min (double, default: -180)

`Min valid angle (°) for LIDAR data.`

angle_max (double, default: 180)

`Max valid angle (°) for LIDAR data.`

range_min (double, default: 0.08)

`Min valid range (m) for LIDAR data.`

range_max (double, default: 32.0)

`Max valid range (m) for LIDAR data.`

ignore_array (string, default: "")

`Set the current angle range value to zero.`
    
` Note: ignore 10 to 20 and 50 to 80, ex: "10, 20, 50, 80"`

samp_rate (int, default: 9)

`the LIDAR sampling frequency.`
    
| LiDAR                		| samp_rate             | 
|-----------------------------|------------------------|
|X4         		| 5				 |


frequency (double, default: 10)

`the LIDAR scanning frequency.`

Note: Specific LiDAR paramter configuration, refer to [Dataset](#dataset)
