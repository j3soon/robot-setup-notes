# Robot Operating System

## Quick Access

- [ROS](https://www.ros.org/)
- [ROS Forum](https://answers.ros.org/)
- [ROS Tutorials](https://wiki.ros.org/ROS/Tutorials)
- [ROS Tutorials on GitHub](https://github.com/ros/ros_tutorials)

## Before Installing

First, make sure which version of ROS is preferred. (i.e., ROS 1 or ROS 2)
- [Changes between ROS 1 and ROS 2](https://design.ros2.org/articles/changes.html)
- [What is the difference between ROS and ROS2?](https://answers.ros.org/question/287470/what-is-the-difference-between-ros-and-ros2/?answer=287472#post-id-287472)

In most cases, if the version is not specified in a open source project, it means ROS 1.

Then, decide which distribution you want to use.
- [ROS distributions](https://wiki.ros.org/Distributions)
  As of 2021, `Noetic` is the newest release, and `Melodic` are used in most open source projects.
- [ROS 2 distributions](https://docs.ros.org/en/foxy/Releases.html)
  As of 2021, `Galactic` is the newest release, and `Foxy` has the latest End-Of-Life date.

## Quick Start for ROS 2

For ROS 2, follow the [installation guide](https://docs.ros.org/en/foxy/Installation.html).

The rest of this article focus on ROS 1 only.

## Quick Start

1. Open the [installation page](https://wiki.ros.org/ROS/Installation).
2. Choose the preferred distribution.
3. Select the preferred platform.
4. Follow the installation instructions.
5. Follow [the tutorials](https://wiki.ros.org/ROS/Tutorials) until `13. Examining the Simple Publisher and Subscriber`.

You should now know how to communicate using ROS between nodes.

For more details, see [the tutorial](https://wiki.ros.org/ROS/Tutorials).

## Environment Setup

To access ROS, make sure to run:

```sh
# ROS
source /opt/ros/<distro>/setup.bash
# For your ROS workspace
source devel/setup.bash
```

## Troubleshooting

- In the Tutorials `6. Understanding ROS Topics`, using `Ctrl+C` to terminate the turtle node may not perform cleanup successfully, you should close the window by clicking the `X` button instead. (See [this post](https://answers.ros.org/question/37939/rosrun-node-is-not-removed-from-rosnode-list-after-exit/?answer=37941#post-id-37941))
- [Topics vs. Services vs. Actions](https://wiki.ros.org/ROS/Patterns/Communication#Communication_via_Topics_vs_Services_vs_X)
- Make sure your `/etc/hosts` contains the correct IP (`ifconfig`).
- Make sure you are running `roscore`, or `ros.service` if you are using `rosrun`.
- `roslaunch` does not need `roscore` running.
- Use `rosnode` and `rostopic` command to quickly isolate where the issue resides.
- Solution to [ROS GPG Key Expiration Incident](https://discourse.ros.org/t/ros-gpg-key-expiration-incident/20669)
- If you encountered `XXX Package not found`, run `apt-get install ros-<distro>-<package>`
- Manually inspect and run the setup scripts to ensure no error occurs.

Some tools for troubleshooting:
- `dmesg -wH` to check the USB port connection.
- `ping -c1 <hostname/IP>` to check if the host is responsive.
- `sudo nmap -sn -PE -T5 -n <IP-CIDR>` to ping multiple hosts at once.
