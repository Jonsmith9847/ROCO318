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
 -  Motors: **[Dynamixel AX-12](https://www.trossenrobotics.com/dynamixel-ax-12-robot-actuator.aspx) (x2)**
 -  3D Printed Parts:
	 - Base Part: **[STL Model](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/Base.stl)**
	 - Tilt Bracket: **[STL Model](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/Joint.stl)**
	 - Camera Mount: **[STL Model](https://github.com/Jonsmith9847/ROCO318/blob/master/CAD%20Files/CamMount.stl)**



### Installing

A step by step series of examples that tell you how to get the system running.

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

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

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

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

1. roscore
2. cd catkin_ws/src
3. ls -ltrh /dev/video*


Source the environment: 
 `source /opt/ros/kinetic/setup.bash`

Setup the work space folders:
```
mkdir -p ~/catkin_ws/src`
cd ~/catkin_ws/
catkin_make
```
Source the bash file:
``source devel/setup.bash``

Clone usb_cam package: (into src)
``git clone https://github.com/ros-drivers/usb_cam.git``

Edit launch file to use correct camera (``ls -ltrh /dev/video*``)

``rsolaunch usb_cam usb_cam-test.launch``
