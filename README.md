# ROS Pan Tilt Camera

This documentation covers all the required information, equipment and software for the ROS Pan Tilt Camera system.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. The instructions will also guide you through the hardware use and construction.

### Prerequisites

Prior to installation the following software components are required:
 - Operating System: **[Ubuntu 16.04 LTS](http://releases.ubuntu.com/16.04/)**
 - ROS Version: **[ROS Kinetic Kame](http://wiki.ros.org/kinetic)**
 
The following hardware components are also required:
 - Camera: **[Logitech C920 Web Camera](https://www.logitech.com/en-gb/product/hd-pro-webcam-c920)**
 - Motors: **[Dynamixel AX-12](https://www.trossenrobotics.com/dynamixel-ax-12-robot-actuator.aspx) (x2)**
 - Dynamixel Controller: **[USB2Dynamixel Adapter](https://www.trossenrobotics.com/robotis-bioloid-usb2dynamixel.aspx)** 
 - Dynamixel 3 Pin Cables: **[Dynamixel Cable](https://www.trossenrobotics.com/p/200mm-3-pin-dynamixel-compatible-cables-10-pack) (x3)**
 -  3D Printed Parts:
	 - Base Part: **[STL Model](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/Base.stl)**
	 - Tilt Bracket: **[STL Model](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/Joint.stl)**
	 - Camera Mount: **[STL Model](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/CamMount.stl)**

### Construction

 1.  Using screws, mount a [Dynamixel AX-12](https://www.trossenrobotics.com/dynamixel-ax-12-robot-actuator.aspx) motor into the [Base Part](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/Base.stl). 
	
  <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step1a.jpg?raw=true" width="300" height="300"> <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step1b.jpg?raw=true" width="300" height="300">

 2. Using screws, connect the [Tilt Bracket](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/Joint.stl) to the top of the Base Motor. 
	
  <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step2a.jpg?raw=true" width="300" height="300"> <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step2b.jpg?raw=true" width="300" height="300">

 3. Using screws, connect the final [Dynamixel AX-12](https://www.trossenrobotics.com/dynamixel-ax-12-robot-actuator.aspx) to the [Tilt Bracket](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/Joint.stl). Ensure that the non-driven side of the motor is free to rotate.    
   
  <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step3a.jpg?raw=true" width="300" height="300"> <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step3b.jpg?raw=true" width="300" height="300">
   
 4. Screw the [Camera Mount](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/CamMount.stl) to the top of the Tilt Motor. 

  <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step4.jpg?raw=true" width="300" height="300">
 
 6. Feed a [Dynamixel Cable](https://www.trossenrobotics.com/p/200mm-3-pin-dynamixel-compatible-cables-10-pack) through the cable managment hole in the base and connect the two motors together.
 
 7. Add an additional [Dynamixel Cable](https://www.trossenrobotics.com/p/200mm-3-pin-dynamixel-compatible-cables-10-pack) to the base motor and secure with a single zip tie.
 
 8. Slot the [Logitech C920 Web Camera](https://www.logitech.com/en-gb/product/hd-pro-webcam-c920) into the bracket and use double sided tape to secure if required.
 
  <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step7.jpg?raw=true" width="300" height="300">
 
 9. Connect the remaining electronics as show, ensuring that the [USB2Dynamixel Adapter](https://www.trossenrobotics.com/robotis-bioloid-usb2dynamixel.aspx) switch is set to TTL mode.

  <img src="https://github.com/Jonsmith9847/ROCO318/blob/master/images/step8.jpg?raw=true" width="300" height="300">

## Installing the project

### Clone the files

 1. Download the repository:
```git clone https://github.com/Jonsmith9847/ROCO318.git```
2. Navigate to the workspace:
```cd catkin_ws/```
3. Source the bash file:
```source devel/setup.bash```
4. Build the project:
```catkin_make```

### Webcam Installation
 1. Start ROS in a new terminal:
```roscore```
2. Identify the webcam you want to use:
```ls /dev/video*```
3. Edit /catkin_ws/src/usb_cam/launch/usb_cam-test.launch if necessary to select the correct camera.
	i.e. edit video device "/dev/video1" to "/dev/video0"
4. Navigate to the src folder:
```cd catkin_ws/src```
5. Launch the usb cam node:
```roslaunch usb_cam/launch/usb_cam-test.launch```
6. Start RVIZ in a new terminal:
```rviz```
7. In RVIZ add a new Image view. 
Add > Image > Ok
![RVIZcam1.png](https://github.com/Jonsmith9847/ROCO318/blob/master/images/RVIZcam1.png?raw=true)
9. Set Image Topic to /usb_cam/image_raw
![RVIZcam2.png](https://github.com/Jonsmith9847/ROCO318/blob/master/images/RVIZcam2.png?raw=true)
## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## CAD Models

The CAD Model for the project was produced using [Fusion360](https://www.autodesk.co.uk/products/fusion-360/overview#banner]). The final design includes the following models:
**Dynamixel AX-12 [https://www.trossenrobotics.com/dynamixel-ax-12-robot-actuator.aspx]**
**Logitech C920 Webcam [[https://grabcad.com/library/logitech-hd-pro-webcam-c920-1](https://grabcad.com/library/logitech-hd-pro-webcam-c920-1)]**


<img src="https://github.com/Jonsmith9847/ROCO318/blob/master/Renders/Front.jpg?raw=true" width="300" height="300"><img src="https://github.com/Jonsmith9847/ROCO318/blob/master/Renders/Side.jpg?raw=true" width="300" height="300"><img src="https://github.com/Jonsmith9847/ROCO318/blob/master/Renders/IsometricFront.jpg?raw=true" width="300" height="300"><img src="https://github.com/Jonsmith9847/ROCO318/blob/master/Renders/IsometricRear.jpg?raw=true" width="300" height="300"><img src="https://github.com/Jonsmith9847/ROCO318/blob/master/Renders/Top.jpg?raw=true" width="300" height="300"><img src="https://github.com/Jonsmith9847/ROCO318/blob/master/Renders/Bottom.jpg?raw=true" width="300" height="300">

STL Files and Fusion 360 files can be found in the following location:
[https://github.com/Jonsmith9847/ROCO318/tree/master/CAD%20Files](https://github.com/Jonsmith9847/ROCO318/tree/master/CAD%20Files)
## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Jonathan Smith** - *Entire Project* - [Jonsmith9847](https://github.com/Jonsmith9847)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc

## Notes:
