## SSH

To execute commands on the robot, use ssh
> :warning: connect to usb-ethernet first (see Hardware)!

```shell
ssh bento@192.168.55.1
```

This will change your prompt to

```console
bento@Box:~$
```

All following commands are to be run on the jetson

## ROS nodes

I recommend starting everything in separate terminal windows, since everything is buggy and prone to crashing

ROS isn't natively installed on the jetson, so you will need to execute all ROS-related things in a container

### enable

Before you do anything ROS related, run

```shell
~/enable.sh
```

this will turn on the enable signal for the motor controllers

### ethernet (CAN) gateway

```shell
ros2 launch edu_robot bento-box.launch.py
```
It should generate a fluent spam of text.
If the spam isn't continuous, it is likely it bugged out.
Just restart it if it does this

### cameras

run
```shell
ros2 launch /root/cameras/tri_usb_cams.launch.py
```
one camera will 'crash' if only two are plugged in.