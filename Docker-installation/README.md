Docker Installation Guide for Linux
This guide provides instructions to install Docker on a Linux system using the official Docker installation script.
Prerequisites

A Linux distribution (e.g., Ubuntu, Debian, CentOS, or Fedora)
Sudo privileges or root access
Internet connection

Installation Steps

Download the Docker Installation Script
Run the following command to download the official Docker installation script:
sudo curl -fsSL https://get.docker.com -o get-docker.sh


Execute the Installation Script
Execute the downloaded script to install Docker:
sudo sh get-docker.sh


Verify Installation
After the installation completes, verify that Docker is installed correctly by checking its version:
docker --version

You should see output similar to:
Docker version 27.3.1, build ce12230



Post-Installation (Optional)
To run Docker commands without sudo, add your user to the docker group:
sudo usermod -aG docker $USER

Log out and back in, or run newgrp docker to apply the group changes.
Reference
For more details, refer to the official Docker installation repository:

Docker Install Repository

Notes

This guide is specific to Linux systems.
Ensure your system is up-to-date before installation (sudo apt update or equivalent for your package manager).
The installation script automatically detects your Linux distribution and installs the appropriate Docker version.
