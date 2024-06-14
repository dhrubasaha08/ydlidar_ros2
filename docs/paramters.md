# ROS2 Paramters Table


## Paramters Description

| Parameter         | Type                    | Description                                         |
|-----------------------|------------------------|-----------------------------------------------------|
| `port`        		| String                 	| port of lidar (ex. /dev/ttyUSB0)                         		|
| `baudrate`     	| int                      	| baudrate of lidar (ex. 128000 or 115200)           				|
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


## Baudrate Table

| LiDAR                					| baudrate               | 
|-----------------------------------------------|-----------------------|
|X2		| 115200			|
|X4                   					| 128000			|


## SingleChannel Table

| LiDAR                							| singleChannel       | 
|-----------------------------------------------------------|-----------------------|
|X4 	| false			|
|X2                   						| true			|


## isToFLidar Table

| LiDAR                									| isToFLidar             | 
|-----------------------------------------------------------------------|-----------------------|
|X4/X2	| false			|


## Sampling Rate Table

| LiDAR                		| samp_rate             | 
|-----------------------------|------------------------|
|X4         		| 5				 |


## Frequency Table

| LiDAR                					| frequency             | 
|-----------------------------------------------|------------------------|
|X4 			| Not Support		 |

Note: For unsupported LiDARs, adjusting the scanning frequency requires external access to PWM speed control.
