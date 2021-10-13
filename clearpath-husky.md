# Clearpath Husky

## Quick Access

- [Husky UGV on YouTube](https://www.youtube.com/watch?v=H6lcvtpEYzs&list=PLC3Ml17CGYHLO7svKm41CWGdFCE7xs3dQ)
- [Husky UGV \| Robot Setup & Configuration](https://youtu.be/wA8UTF0mKBY?list=PLC3Ml17CGYHLO7svKm41CWGdFCE7xs3dQ)
- [Husky UGV User Manual](https://levelfivesupplies.com/wp-content/uploads/2020/08/Husky-UGV-User-Manual.pdf)
- [Husky Tutorial for ROS Kinetic](https://www.clearpathrobotics.com/assets/guides/kinetic/husky/index.html)
- [Husky Tutorial for ROS Melodic](https://www.clearpathrobotics.com/assets/guides/melodic/husky/index.html)
- [Husky Tutorial for ROS Noetic](https://www.clearpathrobotics.com/assets/guides/noetic/husky/index.html)
- [Husky Examples on GitHub](https://github.com/husky/husky)

## Before Installing

Install ROS Melodic.

Check if you have a on-board MINI-ITX computer.

## Quick Start

- If you want to control Husky through the on-board computer, follow [this YouTube guide](https://youtu.be/wA8UTF0mKBY?list=PLC3Ml17CGYHLO7svKm41CWGdFCE7xs3dQ).
- If you want to control Husky directly by a Jetson board / PC (i.e. without using the on-board computer), follow [the steps here](https://clearpathrobotics.com/assets/guides/melodic/husky/jetson_xavier.html#step-3-installing-the-software).

The following step is required if the on-board computer is not used.

```sh
mkdir -p ~/husky_ws/src
cd ~/husky_ws/src

cd ~/husky_ws
# The original script below will mess up the network configuration, so we use a modified version instead.
# https://raw.githubusercontent.com/clearpathrobotics/ros_computer_setup/main/install.sh
wget -c https://raw.githubusercontent.com/j3soon/ros_computer_setup/main/install.sh
bash install.sh
# Select the corresponding options, and reboot when finished
rostopic echo /status # to confirm the installation (may encounter issue on Jetson, mentioned in the troubleshooting section)

sudo apt install -y "ros-melodic-husky*"
sudo apt install -y ros-melodic-joy
sudo apt install -y ros-melodic-teleop-twist-joy
sudo apt install -y ros-melodic-teleop-twist-joystick-drivers
sudo apt install -y ros-melodic-teleop-twist-keyboard

cd ~/husky_ws/
catkin_make
source ./devel/setup.bash
# (1) Control with keyboard
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
# (2.1) Control with Joystick
rosrun joy joy_node
# (2.2) Open another terminal
cd ~/husky_ws/
source ./devel/setup.bash
rosrun teleop_twist_joy teleop_node
# Control with Joy Stick (Logitech, State X (not D), Mode light off. Hold A and Left Thumb for Direction)
# (The controls may differ on different environments, so you can try out something like holding L1/R1 and control with Left Thumb etc.)
```

More examples are provided in [this repo](https://github.com/husky/husky).

## Troubleshooting

- [ROS Service Error on Jetson](https://answers.ros.org/question/379136/control-husky-ugv-directly-through-jetson-xavier/)
- [JoyStick Configuration](https://wiki.ros.org/joy/Tutorials/ConfiguringALinuxJoystick)
- May need to run `systemctl restart ros.service` when Husky has `COMM` error.
- `jstest` and `jstest-gtk` for testing JoyStick.
- See ROS Troubleshooting document.
