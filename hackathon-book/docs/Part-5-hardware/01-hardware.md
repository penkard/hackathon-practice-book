---
id: hardware-setup
title: Section 6: Hardware Requirements
sidebar_label: 6. Hardware Setup
---

# **Hardware Requirements**

Physical AI sits at the intersection of three heavy computational loads: **Physics Simulation**, **Computer Vision**, and **Generative AI**. This requires specific hardware.

## **6.1 The "Digital Twin" Workstation**

To run NVIDIA Isaac Sim and Gazebo effectively, you need a high-performance machine.

* **GPU:** NVIDIA **RTX 4070 Ti (12GB)** or higher.
    * *Requirement:* Ray Tracing (RTX) is mandatory for Isaac Sim. 12GB VRAM is the minimum to load complex USD assets.
* **CPU:** Intel Core i7 (13th Gen+) or AMD Ryzen 9.
* **RAM:** **64 GB DDR5** (32 GB is absolute minimum).
* **OS:** **Ubuntu 22.04 LTS**. (ROS 2 Humble/Iron is native to Linux).

## **6.2 The "Physical AI" Edge Kit**

For the "Brain" of the physical robot (or your desk prototype), we use embedded supercomputers.

* **Compute:** **NVIDIA Jetson Orin Nano (8GB)**.
    * Capable of 40 TOPS (Trillion Operations Per Second) for AI inference.
* **Vision:** **Intel RealSense D435i** (Camera + IMU).
* **Voice:** ReSpeaker USB Mic Array.

## **6.3 Robot Lab Options**

* **Option A (Proxy):** **Unitree Go2 Edu**. A quadruped that supports ROS 2 perfectly. Best for budget labs.
* **Option B (Humanoid):** **Unitree G1**. A fully capable humanoid for advanced Sim-to-Real transfer.

## **6.4 Cloud Alternatives**

If local RTX hardware is unavailable, use **AWS g5.2xlarge** instances.
* **Pros:** Instant access to 24GB VRAM (A10G GPU).
* **Cons:** Latency makes real-time robot control difficult; strictly for simulation and training.