# 🏛️ Architectural Guide: Block 01 - The Nervous System
**Hardware Target:** AMD A6-5400K | 8GB RAM | 500GB HDD
**Status:** INITIALIZED

## 1. System Abstract
This block focuses on reclaiming sovereignty over the machine. We are transitioning from a GUI-dependent user to a System Operator.
The goal is to master the Linux Filesystem Hierarchy (FHS) and understand how the Kernel manages physical hardware resources through
the terminal.

## 2. Hardware Constraints (Anzoátegui Constraint)
* **CPU (AMD A6):** Limited to 2 cores. We must monitor context-switching and avoid heavy background daemons.
* **RAM (DDR3):** 8GB total. Target development overhead: < 512MB. 
* **I/O (HDD):** High latency. We prioritize efficient pathing to minimize mechanical head movement on the 500GB platter.

## 3. Component Diagram (The Logic)
```text
[ USER INPUT ] 
      |
[ BASH SHELL ] <--- (Path Resolution)
      |
[ SYSTEM CALLS ] <--- (open, read, write, move)
      |
[ LINUX KERNEL ] <--- (VFS - Virtual File System)
      |
[ HDD HARDWARE ] <--- (Inodes & Data Blocks)
