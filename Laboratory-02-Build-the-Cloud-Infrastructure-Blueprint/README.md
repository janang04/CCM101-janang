# Laboratory 02: Build the Cloud Infrastructure Blueprint

## About the Laboratory

In this laboratory, I explored the basic components of cloud infrastructure using an Ubuntu Linux server from the KillerCoda Playground. I used Linux terminal commands to investigate the server's CPU, RAM, storage, network configuration, hostname, and operating system.

I also learned how the main cloud infrastructure components work together and compared similar services from AWS, Microsoft Azure, and Google Cloud Platform.

## What I Learned

After completing this laboratory, I learned how to:

- Investigate a Linux-based virtual server.
- Identify compute, storage, networking, and operating system resources.
- Read and interpret Linux terminal output.
- Document infrastructure information using Markdown.
- Compare services from AWS, Azure, and Google Cloud.
- Create a basic cloud infrastructure diagram.
- Organize technical files and evidence in GitHub.

## My KillerCoda Server

The following information was collected directly from the Ubuntu environment provided by KillerCoda.

| Resource | My Observation |
|---|---|
| Operating System | Ubuntu 24.04.4 LTS |
| Kernel Version | `6.8.0-138-generic` |
| CPU | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| CPU Cores | 1 virtual CPU core |
| RAM | 1.9 GiB |
| Disk | 20 GB virtual disk |
| Main Partition | 19 GB ext4 |
| Hostname | `ubuntu` |
| Network Interface | `enp1s0` |
| Primary IP | `172.30.1.2/24` |

For the complete investigation results, see the [Infrastructure Report](infrastructure-report.md).

## Main Cloud Infrastructure Components

The investigation focused on four major components:

### Compute

The KillerCoda environment provides one virtual CPU core using an Intel Xeon E312xx processor. Compute resources are responsible for processing instructions and running applications.

### Storage

The environment contains a 20 GB virtual disk. The main 19 GB partition uses the ext4 filesystem and is mounted at `/`.

### Networking

The primary network interface is `enp1s0`, which has the IP address `172.30.1.2/24`. A Docker interface was also detected during the investigation.

### Operating System

The server runs Ubuntu 24.04.4 LTS with Linux kernel `6.8.0-138-generic`. The operating system provides the environment where the server's applications and commands operate.

More detailed explanations can be found in [cloud-components.md](cloud-components.md).

## Linux Commands

I used several Linux commands to investigate the server:

```text
cat /etc/os-release
uname -r
lscpu
nproc
free -h
lsblk
df -hT
hostname
hostname -I
ip -br addr
