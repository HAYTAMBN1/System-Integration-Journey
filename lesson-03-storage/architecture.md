# 🏗️ Storage & Partitioning Architecture

## 1. Overview
This project demonstrates the configuration of a secondary storage device within a Linux (Ubuntu 24.04 LTS) environment. The setup focuses on logical data separation by creating multiple partitions on a single physical disk.

---

## 2. Hardware Representation
* **Host Type:** VMware Virtual Machine
* **Disk Name:** `/dev/sdb`
* **Total Capacity:** 20 GiB

---

## 3. Logical Structure (The Dual-Partition Setup)
The disk was initialized using a **GPT (GUID Partition Table)** to ensure modern standards and compatibility.

| Partition | Device Path | Size | File System | Mount Point | Purpose |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Partition 1** | `/dev/sdb1` | ~10 GiB | ext4 | `/data` | Primary data storage |
| **Partition 2** | `/dev/sdb2` | ~10 GiB | ext4 | `/backup` | System & data backups |

---

## 4. Visual Flow
Below is a simplified representation of how the disk is seen by the Linux Kernel:

[Physical Disk: /dev/sdb (20GB)]
      |
      +-- [Partition 1: /dev/sdb1 (10GB)] --> [Mounted at: /data]
      |
      +-- [Partition 2: /dev/sdb2 (10GB)] --> [Mounted at: /backup]

---

## 5. Persistence Layer
The mounting process is automated via the `/etc/fstab` configuration file, ensuring that both partitions are available immediately upon system boot with the following parameters:
* **Options:** `defaults`
* **Dump/Pass:** `0 2`
