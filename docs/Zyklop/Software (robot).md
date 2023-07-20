## SSH

To execute commands on the robot, use ssh
> :warning: connect to Wi-Fi first (see Hardware)!

```shell
ssh root@192.168.1.200
```

This will change your prompt to

```console
root@Zyklop:~#
```

## ROS nodes

To start everything just paste all this and let it finish.

```shell
~/rosbot/startScripts/skidStart.sh 
~/rosbot/startScripts/roscoreStart.sh 
rosrun cv_camera cv_camera_node&
```

To see what's happening you can run `screen -r <name>`  
e.g. `screen -r skid`
> `screen -ls` will show all running screens