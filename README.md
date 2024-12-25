# PX4 Humble Setup

_Smart People Makes Mistakes & Learn from them_
Here is PX4 Autopilot Docker Image with ROS2 Desktop + Dev, PX4 Firmware, VS Code (code) and Geddit installed. This link contains access to MPC + INDI (Under Work), Geometric Controller (Under Work) and PID Controller (Working) method for *Controlling Drone with Single Motor Failure*
[text](https://cciitpatna-my.sharepoint.com/:f:/g/personal/rna_iitp_ac_in/Et0g3G1f9bpKguhR8y3V2wYBTXDJ9vnErMwq8Y9xCrkqlA?e=b6h8W7)

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Testing](#testing)
- [License](#license)

## Prerequisites

Before you begin, ensure you have the following installed:
- **Docker Installation**: [Installation guide](https://docs.docker.com/engine/install/ubuntu/)
- **Super User Permission**: [Setting SUDO](https://docs.docker.com/engine/install/linux-postinstall/)

## Installation

First download the desired image .tar file from the link provided

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
  humble/px4-setup
```

Following commands can be used to start and execute the container,
```bash
docker start <container_name>
docker exec -it <container_name> bash
```

NOTE: <container_name> and <terminal_username> are expected to be renamed with the desired names.