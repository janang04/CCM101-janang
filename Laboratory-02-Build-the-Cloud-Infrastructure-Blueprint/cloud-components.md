# Cloud Infrastructure Components

Cloud infrastructure is composed of different resources that work together to provide computing services. The following resources were observed in the Ubuntu Linux environment running in the KillerCoda Playground.

## Observed Resource Summary

| Infrastructure Component | Observed Resource in KillerCoda |
|---|---|
| Compute | 1 virtual CPU core using an Intel Xeon E312xx processor |
| Storage | 20 GB virtual disk with a 19 GB ext4 main partition |
| Networking | Active `enp1s0` interface using IP address `172.30.1.2` |
| Operating System | Ubuntu 24.04.4 LTS with Linux kernel `6.8.0-138-generic` |

## 1. Compute Resources

**Observed Resource:** 1 virtual CPU core using an Intel Xeon E312xx (Sandy Bridge, IBRS update) processor

**Purpose:** Compute resources provide the processing capability required to execute instructions, perform calculations, and run applications and services.

**Importance in Cloud Computing:** Compute resources are essential for running cloud workloads. The amount of computing capacity can be adjusted depending on the processing requirements of an application or service.

**Relation to KillerCoda:** The `lscpu` and `nproc` commands showed that the KillerCoda environment has an Intel Xeon E312xx processor and one available CPU core. The CPU provides the processing power needed to execute commands and run applications within the Linux environment.

## 2. Storage Resources

**Observed Resource:** 20 GB virtual disk with a 19 GB ext4 main partition

**Purpose:** Storage resources provide space for operating system files, applications, logs, and other data.

**Importance in Cloud Computing:** Storage allows cloud systems to save and retrieve data. It is important for maintaining application files, databases, backups, and other information that needs to persist.

**Relation to KillerCoda:** The `lsblk` command identified a 20 GB virtual disk named `vda`. The main partition, `vda1`, has a capacity of 19 GB, uses the ext4 filesystem, and is mounted at `/`. The environment also contains partitions mounted at `/boot` and `/boot/efi`.

## 3. Networking Resources

**Observed Resource:** Active `enp1s0` network interface with IP address `172.30.1.2/24`

**Purpose:** Networking resources enable communication between computers, servers, applications, and other connected resources.

**Importance in Cloud Computing:** Networking provides the connectivity required for users and cloud services to communicate. It also allows different resources and applications within an infrastructure to exchange information.

**Relation to KillerCoda:** The `hostname -I` and `ip -br addr` commands showed that the primary network interface is `enp1s0`, with the IP address `172.30.1.2/24`. A `docker0` interface with the address `172.17.0.1/16` was also present in the environment.

## 4. Operating System

**Observed Resource:** Ubuntu 24.04.4 LTS with Linux kernel `6.8.0-138-generic`

**Purpose:** The operating system manages the server's hardware and software resources and provides the environment where applications, processes, and commands can run.

**Importance in Cloud Computing:** An operating system provides the foundation for running applications and managing resources such as processing, memory, storage, and networking. It allows cloud workloads to operate within a controlled software environment.

**Relation to KillerCoda:** The `/etc/os-release` file confirmed that the environment is running Ubuntu 24.04.4 LTS, while the `uname -r` command showed the Linux kernel version `6.8.0-138-generic`. This operating system provides the environment used to investigate and operate the virtual server.
