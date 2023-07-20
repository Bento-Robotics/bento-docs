## joystick/gamepad control

**Currently only joystick input is tested.**
> Keyboard control is possible through modification of `edu_robot_control` to use the `virtual_joystick` package instead
> of a real joystick

### check joystick

Plug in a joystick and make sure it shows up:

```console
$ ls /dev/input
eventX eventY <...> jsX <...>    # (X = number)
```

### launch node

and run the file that matches your setup

```shell
ros2 launch edu_robot_control bento_remote_joystick.launch.py
```

*or*

```shell
ros2 launch edu_robot_control bento_remote_gamepad.launch.py
```

> joy isn't installed by default.  
> If it can't be found, install `apt install ros-humble-joy`

<br>
> :warning: If you get an 'out of bounds' error, then your joystick has fewer buttons than the config asks for.

### remapping

To remap the joystick you can edit a config file:

```shell
nano <edu_robot_control install location>/edu_robot_control/parameter/bento_joystick.yaml 
```

*or*

```shell
nano <edu_robot_control install location>/edu_robot_control/parameter/bento_gamepad.yaml 
```

## View cameras

To visualise all sensors (including cameras), use RViz

```shell
rviz2
```

Then open the cameras' image topic as *image*, **not camer