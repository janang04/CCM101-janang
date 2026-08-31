# Infrastructure Report

## Server Information

The Linux server provided through the KillerCoda Playground was investigated using standard Linux commands. The following information was observed from the environment.

| Item | Observed Information |
|---|---|
| Operating System | Ubuntu 24.04.4 LTS (Noble Numbat) |
| Kernel Version | 6.8.0-138-generic |
| CPU Model | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| CPU Cores | 1 virtual CPU core |
| Total RAM | 1.9 GiB |
| Hostname | `ubuntu` |

## Storage Information

The server uses a 20 GB virtual disk named `vda`.

| Storage Item | Observed Information |
|---|---|
| Virtual Disk | `vda` — 20 GB |
| Main Partition | `vda1` — 19 GB |
| Main Filesystem | ext4 |
| Root Mount Point | `/` |
| Boot Partition | `vda16` — 913 MB, ext4, mounted at `/boot` |
| EFI Partition | `vda15` — 106 MB, vfat, mounted at `/boot/efi` |

The main 19 GB partition is mounted at `/` and currently has approximately 5.4 GB used and 13 GB available.

## Network Information

The server has multiple network interfaces.

| Network Item | Observed Information |
|---|---|
| Hostname | `ubuntu` |
| Primary Interface | `enp1s0` |
| Primary IP Address | `172.30.1.2/24` |
| Docker Interface | `docker0` |
| Docker IP Address | `172.17.0.1/16` |
| Loopback Interface | `lo` — `127.0.0.1/8` |

The `enp1s0` interface is active and provides the primary network connection for the Linux environment. The `docker0` interface is present but was shown as down during the investigation.

## Mounted File Systems

The `df -hT` command showed the following mounted filesystems:

| Filesystem | Type | Size | Used | Available | Mount Point |
|---|---|---:|---:|---:|---|
| `tmpfs` | tmpfs | 191M | 996K | 190M | `/run` |
| `/dev/vda1` | ext4 | 19G | 5.4G | 13G | `/` |
| `tmpfs` | tmpfs | 952M | 84K | 952M | `/dev/shm` |
| `tmpfs` | tmpfs | 5.0M | 0 | 5.0M | `/run/lock` |
| `/dev/vda16` | ext4 | 881M | 117M | 703M | `/boot` |
| `/dev/vda15` | vfat | 105M | 6.2M | 99M | `/boot/efi` |

## Commands Used

The following Linux commands were used to investigate the server:

```bash
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
