# NVIDIA Jetson

## Quick Access

- [NVIDIA Jetson Page](https://developer.nvidia.com/embedded-computing)
- [NVIDIA Jetson Modules](https://developer.nvidia.com/embedded/jetson-modules)
- [Getting Started](https://developer.nvidia.com/embedded/learn/getting-started-jetson)
- [NVIDIA Jetson FAQ](https://developer.nvidia.com/embedded/faq)
- [NVIDIA Jetson Forum](https://forums.developer.nvidia.com/c/agx-autonomous-machines/jetson-embedded-systems/70)
- [NVIDIA SDK Manager Download](https://developer.nvidia.com/nvsdk-manager) (Free membership required)
- [Jetson Download Center](https://developer.nvidia.com/embedded/downloads)
- [JetPack SDK](https://developer.nvidia.com/embedded/jetpack)

## Before Purchasing

Check the specs of different [Jetson Modules](https://developer.nvidia.com/embedded/jetson-modules).

In general, `AGX Xavier` > `Xavier NX` > `TX2` > `Nano`.

You may also want to purchase a compatible wireless network card.

## Quick Start

For older boards, you can use [the raw image here](https://developer.nvidia.com/embedded/jetpack) and install it on a SD card. Plug the SD card on the Jetson board after installation and boot it up.

For AGX Xavier (newer boards), follow the steps:

1. Use [NVIDIA SDK Manager](https://developer.nvidia.com/nvsdk-manager) following [the User Guide](https://developer.nvidia.com/embedded/learn/getting-started-jetson#documentation) of your board, in the Jetpack section. (SDK Manager does not support Ubuntu 20.04, Use Ubuntu 18.04 instead)

   You may want to install Jetpack 4.4.1 for better compatibility. DeepStream is optional, depending on your usages.

2. Set Jetson board to `Recovery Mode` (Hold `Recovery` button, hold `Power` button, then release them both) and refresh the SDK Manager, your board module should pop up.
   If you have trouble recognizing the board interface or buttons, see the bottom of the board. It has tiny texts showing `Power`, `Force Recovery`, `Reset`, etc.
3. Start the installation in SDK Manager.
4. After the OS is installed on the board, a prompt will pop up on your PC.
5. Now set up the OS on the Jetson board (may need to plug in a keyboard, mouse, and monitor). Set up the network (Wifi/Ethernet) on your Jetson board and use `ifconfig` to find your Jetson local IP.
6. Type in the Jetson IP, username, and password on the prompt on your PC. The SDK Manager will now install the SDKs and tools on the Jetson baord.
7. Install the SD card on your Jetson board (not required for AGX Xavier) and boot it up.

Detailed steps can be found in [the SDK Manager Documentation](https://docs.nvidia.com/sdk-manager/install-with-sdkm-jetson/index.html).

Follow [the tutorials](https://developer.nvidia.com/embedded/learn/getting-started-jetson#tutorials) for further instructions.

## Environment Setup

You may want to VNC or SSH into the board without plugging in keyboard & mouse & monitor.

### VNC

The easiest way to setup a headless VNC on Jetson is to follow [this thread](https://forums.developer.nvidia.com/t/jetson-nano-vnc-headless-connections/77399/2) that installs VinoVNC. You can then connect to Jetson with any VNC client (e.g., [RealVNC](https://www.realvnc.com/en/connect/download/viewer/)) from your PC.

If you encountered some issue, [this thread](https://forums.developer.nvidia.com/t/setting-up-vnc-server-solved/65428) may be useful.

The VNC screen resolution can be changed by `xrandr` and `xorg.conf`, following [this guide](https://wiki.ubuntu.com/X/Config/Resolution).

### SSH

Install `openssh-server`.

```sh
sudo apt install openssh-server
```

### OpenCV

If you encountered issues when installing OpenCV, see [this thead](https://forums.developer.nvidia.com/t/install-opencv-for-python3-in-jetson-nano/74042) and [this thread](https://forums.developer.nvidia.com/t/installing-opencv4-on-xavier-solved/65436).

It can also be used in a virtual environment as mentioned in [this post](https://stackoverflow.com/q/56224015).

In general, you don't need to compile OpenCV by yourself.

### PyTorch

Install [the wheels provided by NVIDIA](https://forums.developer.nvidia.com/t/pytorch-for-jetson-version-1-9-0-now-available/72048).

If you have trouble installing `torchvision`, see [this thread](https://github.com/pytorch/vision/issues/1963).

### ROS

- [Getting Started with ROS on Jetson Xavier NX](https://www.stereolabs.com/blog/ros-and-nvidia-jetson-xavier-nx/)
- [Solution for cv_bridge issue](https://github.com/ros-perception/vision_opencv/issues/329#issuecomment-638798709)

## Troubleshooting

If you have questions, ask on the [NVIDIA Jetson Forum](https://forums.developer.nvidia.com/c/agx-autonomous-machines/jetson-embedded-systems/70)
