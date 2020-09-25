# e.DO Manual Control using ROS2

## Team Members
**Ayush Shrestha - Team Lead**  
**Scott Howard - Implementation Lead**  
**Adam Erdman - Integration Lead**  
**Seth Buchinger - Documentation Lead**  

## Goals / Objectives
* Convert wrapper class for e.DO robot previously developed by Jack Shelata
[Link to Jack's GitHub](https://github.com/jshelata/eDO_manual_ctrl)
* Confirm manual control capabilities on the COMAU e.DO robot using the NVIDIA Jetson control module

-----
# JShelata's README

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

This package has been run and tested on Ubuntu 16.04 LTS and ROS Kinetic. In order to use the jog mode, the Ncurses library must be installed on your Linux machine.

e.DO Software Version: 2.1.0


### Installing

Clone/save this repository into the "src" folder in a catkin workspace directory. Use catkin_make from your catkin workspace directory to build.

Clone/save directory into src folder

```
cd catkin_ws/src/
git clone https://github.com/jshelata/eDO_manual_ctrl.git
```

Build the package

```
cd catkin_ws
catkin_make
```

Connect to your e.DO's WiFi network and set the ROS_MASTER_URI of your machine to the e.DO's IP address and the ROS_IP to your machine's IP on the e.DO WiFi network. NOTE: You can also add these two lines to the bottom of your .bashrc in your home directory.

```
export ROS_MASTER_URI=http://192.168.12.1:11311
export ROS_IP=192.168.12.68
```

Source your setup.bash file within your catkin workspace.

```
source devel/setup.bash
```

Run the node.

```
rosrun edo_manual_ctrl edo_manual_ctrl
```
#### LAN Connection

If you prefer to access the e.DO over your own LAN using an Ethernet cable, you mush change the ROS_MASTER_URI and ROS_IP within the e.DO as well as on your own machine.

Connect to e.DO via ssh using e.DO's IP on your LAN. NOTE: It may be helpful to reserve an IP on your router for the e.DO.
```
ssh edo@10.42.0.49
```
The e.DO's password is "raspberry".

Next, you'll need to edit the "ministarter" file in the home directory. Change the IP address in lines 20 and 21 to e.DO's IP address on the LAN. Save and close the file and restart e.DO. Change the ROS_MASTER_URI as explained above to the new IP address and the ROS_IP to you machine's IP address on the LAN.


## Build Dependencies


* **Jack's**
* [Ncurses](https://www.cyberciti.biz/faq/linux-install-ncurses-library-headers-on-debian-ubuntu-centos-fedora/) - Used for asynchronous jog control
* [ROS Kinetic](http://wiki.ros.org/kinetic.Installation)
* [eDO_core_msgs](https://github.com/Comau/eDO_core_msgs) - Must be cloned in catkin_ws/src/
* C++11 - Used to sleep to give time for e.DO to process commands

* **Changes for Current Team**
* [Ros Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)
* [Ros2 Eloquent](https://index.ros.org/doc/ros2/Installation/Eloquent/Linux-Install-Debians/)


## Reference

* **Jack Shelata** - [jack@jackshelata.com](mailto:jack@jackshelata.com)

## License

This project is licensed under the MIT License - see [LICENSE.md](LICENSE.md) file for details


