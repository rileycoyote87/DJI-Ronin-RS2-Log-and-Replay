# DJI-Ronin-RS2-Log-and-Replay
based on the Ronin SDK this simple two script python set reads and logs gimbal yaw, roll, pitch, and focus position, and then can replay the movement based on the log. Used as a cinematography and vfx moco tool by Basichis and Harmon separately. Originally developed by Cornelius von Einem.

Made in collaboration and consultation by Cornelius von Einem, Casey Basichis, Riley Harmon, and DJI Engineers 

based previously on https://github.com/ceinem/dji_rs2_ros_controller

Python3 using Ubuntu Focal Fossa

see ronin-play and ronin-record for required python dependencies to install

CANable Pro with candlelight firmware for pure socket can connection

Custom 3D printed RS2 can connector or DJI R Focush Wheel


1) Create a Bin folder in your home directory, add all files to bin directory
2) use nano to edit your .bashrc file - $ nano ~/.bashrc
3) add the following line to the .bashrc end of file. it will allow you to simply type the name of the python scripts and bash scripts for bringing up the can device in the terminal to excute
export PATH=$PATH:~/bin
4) run sudo can-up in terminal to initialize the can device (you'll need to edit this file depending on your type of can device interface)
5) run ronin-record to record the movements to the log
6) move the ronin using joystick or force mobile
7) use CTRL-C to end the program
8) run ronin-play to playback the movement
