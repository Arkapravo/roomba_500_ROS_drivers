roomba_500_ROS_drivers
======================

ROS drivers for the roomba 500 series robots

Fork in
-------

These files are forked in from ISR - University of Coimbra repository of ROS packages,https://code.google.com/p/isr-uc-ros-pkg/,       
(1) _roomba_robot_ -- http://isr-uc-ros-pkg.googlecode.com/svn/stacks/roomba_robot/trunk/roomba_500_series/ (revision 484)   
(2) _serial_communication_ -- http://isr-uc-ros-pkg.googlecode.com/svn/stacks/serial_communication/ (revision 484)   

Installation
------------
ROS Electric or ROS Fuerte installation (http://ros.org/wiki) is needed for these packages. Build and install; _serial_communication_ first and then _roomba_robot_  with the following respectively,

~~~~~~~~~~~~~~~~~~~
rosmake cereal_port
~~~~~~~~~~~~~~~~~~~
and 

~~~~~~~~~~~~~~~~~~~~~~~~~
rosmake roomba_500_series
~~~~~~~~~~~~~~~~~~~~~~~~~

and make sure that these are on the ROS PATH. 

Controlling the robot
----------------------
* Step One

Connect the Roomba with the computer using a FTDI USB cable (http://store.iheartengineering.com/ihe-0202-0000-0000.html), Bluetooth connectivity will also suffice. To check for the port and connection of the FTDI USB cable, type in    
  
~~~~~~~~~~~~~~~~
dmesg | grep tty
~~~~~~~~~~~~~~~~

 in the terminal window, it should give output as this,

 ![Image Alt](https://lh3.googleusercontent.com/-_ENNma4SY58/UNzHydm9jaI/AAAAAAAACMc/9DuX1gaMLQo/s748/roomba-b.png)

* Step Two

Switch on the robot, the CLEAN button will have a light on

 ![Image Alt](https://lh5.googleusercontent.com/-n5mU-b1D3rc/UNzHyTT7uLI/AAAAAAAACMg/za72x4dNqmk/s450/roomba-e.jpg)

* Step Three

Start an instance of the master and in another terminal window type in  

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
rosrun roomba_500_series roomba560_node
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

the above node is specifically made for Roomba 560 robot, for any other model consider trying out the following,
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
rosrun roomba_500_series roomba500_light_node
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  
  that should make the lights of the robot go off and give an output as this,

 ![Image Alt](https://lh4.googleusercontent.com/-HRD10oHRNHE/UNzHyR7C9UI/AAAAAAAACMk/bDIPcuvgLhg/s641/roomba-a.png)

Now the robot can be controlled by ROS nodes, try teleoperation etc.

Testing on Roomba 560
---------------------

By Arkapravo Bhaumik (arkapravobhaumik@gmail.com) and Koushik Kabiraj (koushik.atti@gmail.com)

On a ROS Electric installation (Ubuntu 10.04 LTS, Ubuntu 11.04 and Ubuntu 11.10)

 ![Image Alt](https://lh3.googleusercontent.com/-SHfhVb0WSBA/UPJI3loCziI/AAAAAAAACP0/eb5BD0kY-wY/s640/roomba_pic.jpg)

Testing on Roomba 521
---------------------

By Devasena Prasad (devasena.prasad@gmail.com)

On a ROS Groovy installation (Ubuntu 12.04)

* Permission for USB must be changed using 

~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo chmod 777 /dev/ttyUSB*
~~~~~~~~~~~~~~~~~~~~~~~~~~~

* roomba500_light_node works fine
