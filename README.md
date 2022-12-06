# DJI Ronin RS2/3 Pro - Log and Replay Movements

LICENSE USE

Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)
https://creativecommons.org/licenses/by-nc/4.0/

based on the Ronin SDK this simple two script python set reads and logs gimbal yaw, roll, pitch, and focus motor position, and then will replay the movement based on the log. Used as a cinematography and vfx motion control tool.

Made in collaboration and consultation by [Cornelius von Einem](https://github.com/ceinem), Casey Basichis, [Riley Harmon](https://rileyharmon.com), and DJI Engineers 

based on [dji_rs2_ros_controller](https://github.com/ceinem/dji_rs2_ros_controller) and the [R SDK Demo Software](https://terra-1-g.djicdn.com/851d20f7b9f64838a34cd02351370894/DJI%20R%20SDK/SDK%20demo%20software.zip).

Python3 using Ubuntu 20.04 Focal Fossa

see ronin-play and ronin-record for required python dependencies to install

[CANable Pro](https://openlightlabs.com) with candlelight firmware or similar adapters ([canUSB](https://www.canusb.com)) for pure socket can connection. 

Custom 3D printed RS2 CAN connector or DJI R Focus Wheel ([connection diagram](https://terra-1-g.djicdn.com/851d20f7b9f64838a34cd02351370894/Ronin%E7%B3%BB%E5%88%97/External%20interface%20diagram.pdf)) 

3D Print STL file for custom can connector instead of Focus Wheel included, glue in and solder with these [pogo pins](https://www.traceparts.com/els/precidip/en/product/precidip-straight-slc-connector-low-profile-solder-tail-double-row-8-contacts-a-6-mm-b-4-mm?CatalogPath=PRECIDIP%3APRECIDIP.010.040&Product=10-11052011-114081&PartNumber=813-S1-008-10-014101)


1) Create a bin folder in your home directory, add all files to bin directory, make sure all files have permission as executable
2) use nano to edit your .bashrc file    
```
$ nano ~/.bashrc
```


3) add the following line to the .bashrc end of file. it will allow you to simply type the name of the python scripts and bash scripts for bringing up the can device in the terminal to excute
```
export PATH=$PATH:~/bin
```
save the .bashrc file and either re-source it or close the terminal and open a new terminal window


4) run `sudo can-up`  in terminal to initialize the can device (you'll need to edit this file depending on your type of can device interface)
5) run `ronin-record` in terminal to record the movements to the log
6) move the ronin using joystick or force mobile
7) use `CTRL-C` in terminal to end the program
8) run `ronin-play` in termal to playback the movement
9) run `can-down` to de-initialize the can controller


## Required dependencies
```
pip3 install python-can
pip3 install icecream
pip3 install pandas
pip3 install pyserial
pip3 install playsound
```

