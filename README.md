# DJI-Ronin-RS2-Log-and-Replay
based on the Ronin SDK this simple two script python set reads and logs gimbal yaw, roll, pitch, and focus position, and then can replay the movement based on the log. Used as a cinematography and vfx moco tool by Basichis and Harmon separately. Originally developed by Cornelius von Einem.

Made in collaboration and consultation by [Cornelius von Einem](https://github.com/ceinem), Casey Basichis, [Riley Harmon](https://rileyharmon.com), and DJI Engineers 

based previously on [dji_rs2_ros_controller](https://github.com/ceinem/dji_rs2_ros_controller) and the [R SDK Demo Software](https://terra-1-g.djicdn.com/851d20f7b9f64838a34cd02351370894/DJI%20R%20SDK/SDK%20demo%20software.zip).

Python3 using Ubuntu 20.04 Focal Fossa

see ronin-play and ronin-record for required python dependencies to install

[CANable Pro](https://openlightlabs.com) with candlelight firmware or similar adapters ([canUSB](https://www.canusb.com)) for pure socket can connection. 

Custom 3D printed RS2 CAN connector or DJI R Focus Wheel


1) Create a bin folder in your home directory, add all files to bin directory
2) use nano to edit your .bashrc file -   
```
$ nano ~/.bashrc
```


3) add the following line to the .bashrc end of file. it will allow you to simply type the name of the python scripts and bash scripts for bringing up the can device in the terminal to excute
```
export PATH=$PATH:~/bin
```


4) run `sudo can-up`  in terminal to initialize the can device (you'll need to edit this file depending on your type of can device interface)
5) run ronin-record to record the movements to the log
6) move the ronin using joystick or force mobile
7) use CTRL-C to end the program
8) run ronin-play to playback the movement


## Required dependencies
```
pip3 install python-can
pip3 install icecream
pip3 install pandas
```

