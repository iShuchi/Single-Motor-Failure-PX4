# PX4 Firmware Docker Setup for One Motor Failure

_Smart People Makes Mistakes & Learn from them_
Here is PX4 Autopilot Docker Image with ROS2 Desktop + Dev, PX4 Firmware, VS Code (code) and Geddit installed. This link contains access to MPC + INDI Controller (Under Work), Geometric Controller (Under Work) and PID Controller (Working) method for *Controlling Drone with Single Motor Failure*. These solutions are confidential and only for use of college purposes.

Link is here - [OneDrive Link](https://cciitpatna-my.sharepoint.com/:f:/g/personal/rna_iitp_ac_in/Et0g3G1f9bpKguhR8y3V2wYBTXDJ9vnErMwq8Y9xCrkqlA?e=b6h8W7)
(To Access - Mail to RnA with College Email ID to get password credentials)

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Setup Instructions](#setup-instructions)
- [Testing](#testing)

## Prerequisites

Before you begin, ensure you have the following installed:
- Ubuntu (Dual Booted Setup)
- **Docker Installation**: [Installation guide](https://docs.docker.com/engine/install/ubuntu/)
- **Super User Permission**: [Setting SUDO](https://docs.docker.com/engine/install/linux-postinstall/)

## Installation

Download the desired image .tar file from the link provided.

## Setup Instructions

Since the docker has been installed, enter:
```bash
docker load -i <downloaded_file_name>.tar
docker images
```

Now, from the docker image, run following command to run GUI enabled container for this image;
```bash
docker run -d \
  --name <container_name> \
  --hostname <terminal_username> \
  -e DISPLAY=:0 \
  --gpus all \
  --env DISPLAY=:0 \
  <image_name>
```

Following commands can be used to start and execute the container,
```bash
docker start <container_name>
docker exec -it <container_name> bash
```

NOTE: <any_text> is expected to be renamed with the desired name.

To enable GUI Permission from host, outside docker type;
```bash
xhost +local:
```

## Testing

Clear the build files inside firmware and build again.
```bash
ls
```

This location is preferred location for building all packages. To clean existing build file.
```bash
cd PX4-Autopilot
make clean
make <px4_command> <gazebo_command>
```

NOTE - <px4_command> <gazebo_command> will change whether you are using ROS1 or ROS2.
For Humble Setup,
```bash
make px4_sitl gz_x500
```