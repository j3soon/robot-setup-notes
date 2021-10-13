# Iclebo Kobuki

## Quick Access

- [About Kobuki](http://kobuki.yujinrobot.com/about2/)
- [Kobuki on GitHub](https://github.com/yujinrobot/kobuki)
- [Kobuki on ROS](https://wiki.ros.org/kobuki)
- [Kobuki User Guide](http://docs.google.com/document/export?format=pdf&id=15k7UBnYY_GPmKzQCjzRGCW-4dIP7zl_R_7tWPLM0zKI)

## Before Installing

Install ROS Melodic.

## Quick Start

You can refer to [this GitHub repo](https://github.com/gaunthan/Turtlebot2-On-Melodic) and follow the instructions

Note that Kobuki is a type of TurtleBot, so all turtlebot scripts can be used.

Specifically, the installation instructions is as follows:

```sh
mkdir -p ~/turtlebot2_ws/src
cd ~/turtlebot2_ws
catkin_make
curl -sLf https://raw.githubusercontent.com/gaunthan/Turtlebot2-On-Melodic/master/install_basic.sh | bash
catkin_make
# Bring up kobuki in new terminal
source ./devel/setup.bash
roslaunch turtlebot_bringup minimal.launch
# Control kobuki in new terminal
source ./devel/setup.bash
roslaunch turtlebot_teleop keyboard_teleop.launch
```

## Troubleshooting

See ROS Troubleshooting document.
