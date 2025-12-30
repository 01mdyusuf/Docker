<img width="1213" height="402" alt="image" src="https://github.com/user-attachments/assets/864a8851-0e7a-4c41-8c2a-09a7dd6b9590" />

---
# Docker & Virtualization Basics

This repository contains beginner-friendly notes on Docker, Virtualization, Containers, and related DevOps concepts.



## What You Will Learn
- What is Virtualization?
- Difference: VM vs Docker
- What is Docker Engine & dockerd
- Docker Images, Containers, Docker Hub
- How to install Docker in Ubuntu

---

## Table of Contents
1️Introduction to Virtualization  
2️ Docker Basics  
3️ Docker Installation  
4️ Docker Components  
5️ Examples

---

👇 **It's Continue Below**

---
# Docker
My personal notes and cheat sheet on Docker and virtualization fundamentals... Read it asp....

**Befor starting Docker we have to understand virtualization and its working for better understanding**

# Virtualization 
Virtualization is the technology that allows creation of virtual machines and environments by dividing hardware resources through software.

- It allows one physical computer to behave like multiple computers.

<img width="220" height="190" alt="image" src="https://github.com/user-attachments/assets/767d4724-f739-4036-ae2c-f10152a26071" />

# Working 
A software called a **Hypervisor** divides the main system’s resources **(CPU, RAM, Storage)** so multiple operating systems can run at the same time.

<img width="431" height="285" alt="image" src="https://github.com/user-attachments/assets/41209f7d-8e5b-49c8-b295-09db15b2dba7" />

# Role of Hypervisor
- Creates Virtual Machines (VMs)
- Allocates system resources to each VM
- Keeps VMs isolated from each other
- Ensures VMs run smoothly and securely

# Types of Hypervisors
**1️Type 1 (Bare Metal)**
  - Installed directly on the hardware
  - Faster and more powerful
  - Used in big servers
    
**2️Type 2 (Hosted)**
  - Installed on an existing OS
  - Easier to use for personal computers

<img width="478" height="322" alt="image" src="https://github.com/user-attachments/assets/66fbf8b2-3df4-4f79-aa89-9558a2b68302" />

# Docker
- Docker is a **containerization** platform.
- Instead of running a full OS like a VM, **Docker runs applications in lightweight, isolated environments** called containers.
- Example:
 - Running a Node.js application in a container without installing Node.js on your main PC.

# Working
**1️You download or create a Docker image**
  - Blueprint of app + all things needed
    
**2️Docker uses that image to start a container**
  - Container is the running app
    
**3️Each container is separated from other containers**
  - Safe & no conflicts
    
**4️All containers share the host OS kernel**
  - That’s why Docker is fast and lightweight
    
**5️You can start, stop, delete containers anytime easily**

<img width="1213" height="378" alt="image" src="https://github.com/user-attachments/assets/0cc888a4-2a7a-475d-9408-1e5e4a379348" />


# Terms&Components of Docker
**Docker Image**
- An image is a read-only blueprint to create containers
- You can run many containers from one image
  
**Docker Container**
- A lightweight mini-environment to run applications
- Faster and smaller than a Virtual Machine
- Shares system resources with the host OS
  
**Docker Engine**
- Docker Engine is the complete Docker system that includes the Docker daemon (dockerd), Docker CLI, and Docker API.
- It provides everything required to build, run, and manage containers.
  
**Docker Daemon**
- Also called **dockerd**
- A background service inside Docker Engine
- It creates and manages containers, images, networks

**Docker client**
- It is user interface responsible for interacting with docker containers.

**Docker Hub**
- Docker Hub is an online store for Docker images.
- You can download ready-made images from there.
- You can also upload your own images to share with others.

# Why docker..?
If you are a developer or a system administrator, you undoubtedly come across a situation where you need to run multiple applications within same server or within multiple servers and chances are, you face conflicts while running applications. Suppose you need to run two different applications, one with a library JRE version 1.7 and other with JRE version 1.8, both in a same physical or virtual server. This will cause version conflicts on your server. Using docker containers developers can eliminate such situations and run many applications seamlessly and simultaneously.

<img width="577" height="503" alt="image" src="https://github.com/user-attachments/assets/7ac34299-8a9f-4441-ba93-cc605d53fc3d" />

---

# To install docker engine :

Docker is available for different platforms. To install docker in ubuntu, you can follow the instructions as :

---

### Update the apt package index ###

$ sudo apt-get update

- Always update before installing.
  
---

### Install packages to allow apt to use a repository over HTTPS ###

$ sudo apt install ca-certificates curl gnupg lsb-release

- This allows apt to use Docker’s repo securely.
  
---    
### Add Docker’s official GPG key ####

$ sudo mkdir -p /etc/apt/keyrings curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

- This ensures packages you install come from Docker.
  
---  
### Add the Docker repository ###

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \ https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/

  - Now Ubuntu knows where to fetch Docker from.
    
---
### Update apt package index and install docker ###

$ sudo apt update
$ sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

**This installs**
- docker-ce (Engine)
- docker-ce-cli (command line)
- containerd.io (container runtime)
  
---
### Test your Docker ###

$ sudo docker run hello-world
- If Docker is installed correctly, this will pull and run a test container.
