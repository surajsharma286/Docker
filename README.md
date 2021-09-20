# Docker Basics
This Repository contains the Docker Commands with working examples of Running Docker on AWS EC2.
## Docker Fundamentals
#### VM(Virtual Machine)
 A Virtual machine provides a way to make single physical system work as multiple isolated systems.
 Resulting in Higher infra usage and reduce physical h/w infrastructure overhead.<br>
 How this achieved ?<br>
 Using Hypervisor that runs on your host system.
 Hypervisor split the underlying physical infrastructure into smaller units that can run multiple isolated systems.<br>
#### Benfits of VM<br>
1. Hardware Utilization.
2. Isolation - Running multiple application in Isolated OS.
#### Drawback of VM<br>
1. Each individual Machine or VM is hard to maintain.
2. Overhead of managing whole OS. Install OS,Upgrade,Patch,Install Dependencies for the application that will run on this instance.
#### Containers
Containers enables Virtulization in the sub system level rather than H/W and OS level. Containers utilize namespaces and cgroups to achieve isolation.<br>

Container = Application + OS Dependencies + App Lib.

Container only bring minimal OS and leverage the Host OS. Container has Shell only and no kernel. Container works with Kernel of Host OS.
#### Benefits of Container<br>
1. Portable.
2. Extremely small footprint.
3. Reduced IT management Resources.
4. Quick spinning of Apps.

#### Docker
 Docker is an open source containerization platform. It enables developers to package applications into containers. Most popular container platform.

#### Docker Setup on AWS EC2
1. Provision EC2 instance with Ubuntu using CLI or through console.
2. Run below Commands

    sudo -i 

    apt update -y

    apt install docker.io

    docker --version

#### Docker Basic Commands
#List of Images

    docker images

#List Active Containers

    docker ps

#List All Containers

    docker ps -a

#Run Nginx image

    docker run -d --name=cont1 nginx:latest

#Login to Container

    docker exec -it cont1 /bin/bash

#List the process in container. Top is not supported within Container

    docker exec -it cont1 /bin/bash