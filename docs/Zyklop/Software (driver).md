## keyboard control

use https://github.com/Bento-Robotics/virtual_joystick

## joystick/gamepad control

In the near future the keyboard control software will support joystick operations.  
For now, plug in a joystick and make sure it shows up:

```console
$ ls /dev/input
eventX eventY <...> jsX <...>    # (X = number)
```

and run

```shell
rosrun joy joy_node _autorepeat_rate:=10
```

> joy isn't installed by default.  
> If it can't be found, install `apt install ros-noetic-joy`

## View cameras

To visualise all sensors (including cameras), use RViz

```shell
rviz
```

Then open the cameras' image topic as *image*, **not cameras** and enjoy the view!