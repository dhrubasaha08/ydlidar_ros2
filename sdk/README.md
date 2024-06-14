
YDLIDAR SDK [![Build Status](https://travis-ci.org/cansik/sdk.svg?branch=samsung)](https://travis-ci.org/cansik/sdk) [![Build status](https://ci.appveyor.com/api/projects/status/2w9xm1dbafbi7xc0?svg=true)](https://ci.appveyor.com/project/cansik/sdk) [![codebeat badge](https://codebeat.co/badges/3d8634b7-84eb-410c-b92b-24bf6875d8ef)](https://codebeat.co/projects/github-com-cansik-sdk-samsung)
=====================================================================


Introduction
-------------------------------------------------------------------------------------------------------------------------------------------------------

YDLIDAR(https://www.ydlidar.com/) series is a set of high-performance and low-cost LIDAR sensors, which is the perfect sensor of 2D SLAM, 3D reconstruction, multi-touch, and safety applications.

If you are using ROS (Robot Operating System), please use our open-source [ROS Driver]( https://github.com/ydlidar/ydlidar_ros) .

Prerequisites
-------------------------------------------------------------------------------------------------------------------------------------------------------
* Linux
* Windows 7/10, Visual Studio 2015/2017
* C++11 compiler


Licence
-------------------------------------------------------------------------------------------------------------------------------------------------------

The SDK itself is licensed under BSD [license](license)

Release Notes
-------------------------------------------------------------------------------------------------------------------------------------------------------
| Title      |  Version |  Data |
| :-------- | --------:|  :--: |
| SDK     |  1.4.5 |   2020-01-04  |


- [feature] Supports new and old protocol tof lidar.
- [feature] Display of version number and serial number of single communication lidar.





Dataset 
-------------------------------------------------------------------------------------------------------------------------------------------------------
|LIDAR      | Model  |  Baudrate |  SampleRate(K) | Range(m)  		   |  Frequency(HZ) | Intenstiy(bit) | SingleChannel | voltage(V)|
| :-------- |:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| X4        | 6	   |  128000   |   5            |  0.12~10     		| 5~12(PWM)      | false          | false    	  | 4.8~5.2   |
| X2    | 6	   |  115200   |   3            |  0.10~8.0     	| 4~8(PWM)       | false          | true    		  | 4.8~5.2   |

Note: PWM option speed control requires external PWM wave.

How to build YDLIDAR SDK samples
---------------
```bash
git clone https://github.com/ydlidar/sdk
mkdir build
cd build
cmake ../sdk
make			###linux
vs open Project.sln	###windows
```

How to run YDLIDAR SDK samples
---------------
```bash
$ cd samples
```
linux:
```bash
./ydlidar_test
Please enter the lidar serial port:/dev/ttyUSB0
```

You should see YDLIDAR's scan result in the console:

	[YDLIDAR]:SDK Version: 1.4.5
	[YDLIDAR]:Lidar running correctly ! The health status: good
	[YDLIDAR] Connection established in [/dev/ttyUSB0][512000]:
	Firmware version: 1.3
	Hardware version: 1
	Model: TG30
	Serial: 2020010200010001
	[YDLIDAR INFO] Current Sampling Rate : 20K
	[YDLIDAR INFO] Current Scan Frequency : 15.000000Hz
	[YDLIDAR INFO] Now YDLIDAR is scanning ......
	Scan received: 1329 ranges
	Scan received: 1329 ranges
