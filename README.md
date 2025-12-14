![MIT License](https://img.shields.io/badge/license-MIT-blue)

# Installing and Optimizing Windows 10 on an Unsupported 2013 Intel MacBook

## Overview

This project documents the complete process of installing and running Windows 10 on a 2013 Intel-based MacBook without using Apple Boot Camp. The system was converted into a full Windows machine by removing macOS entirely and manually handling firmware, boot, and driver limitations.

The goal of this project was to repurpose older Apple hardware into a stable, cooler, and more flexible system for development, productivity, and gaming.

---

## ⚠️ Disclaimer

This setup is **not officially supported by Apple**.
Proceed at your own risk.

Always back up important data before attempting a full operating system replacement. Hardware compatibility may vary across different MacBook models.

---

## Why This Project Exists

On this MacBook model, macOS Big Sur is the last supported version. This caused several limitations:

* Many modern applications are unsupported or cannot be installed
* Xcode and other development tools are unavailable
* Gaming support is extremely limited
* High background activity leads to overheating
* Users are locked into Apple’s ecosystem and upgrade path

Rather than abandoning functional hardware or investing in expensive new Apple devices, this project explores an alternative: **running Windows 10 natively on unsupported Apple hardware**.

---

## Motivation and Use Cases

This project was driven by practical needs:

* Better thermal performance and reduced overheating
* Improved battery life
* Ability to run modern development tools
* Native support for applications unavailable on macOS
* Freedom to install and configure any software
* Native gaming support (e.g., Valorant, Assassin’s Creed, Far Cry)
* Full control over the operating system

This approach turns an aging MacBook into a versatile daily-use machine.

---

## System Specifications

* **Model:** MacBook Pro (2013)
* **CPU:** Intel Core i7-4850HQ @ 2.30 GHz
* **RAM:** 16 GB DDR3
* **Storage:** Apple SSD SM0512F
* **GPU:** NVIDIA GeForce GT 750M
* **Network:** Broadcom 802.11ac Network Adapter

---

## Technical Approach

### Boot Method

Common tools such as Rufus and BalenaEtcher failed to create a bootable USB compatible with Apple’s EFI firmware.
[Ventoy](https://www.ventoy.net/en/download.html) was selected due to its strong EFI support and flexibility with ISO booting.

### Installation Strategy

* macOS was completely removed
* Windows 10 was installed in EFI mode
* Boot Camp was not used at any stage
* All drivers were installed manually

### Driver Handling

Apple officially supports only Windows 8 for this hardware through Boot Camp.
To resolve missing drivers after installation, official Apple drivers were manually downloaded from Apple’s support website and installed individually.

---

## Installation Guide

### Step 1: Create Bootable USB

* Download the official Windows 10 ISO
* Install Ventoy on a USB drive
* Copy the Windows ISO to the USB

### Step 2: Boot on MacBook

* Insert the USB drive
* Power on the MacBook while holding the **Option (⌥)** key
* Select the Ventoy USB from the boot menu
* Choose the Windows ISO

### Step 3: Install Windows

* Perform a clean installation
* Delete all existing macOS partitions
* Complete Windows setup normally

### Step 4: Install Drivers

* Download [Apple drivers](https://support.apple.com/en-us/106378) from the official support site. More information and desired [MacBook drivers are listed on their page](https://support.apple.com/en-us/106378) as well
* Transfer drivers to the MacBook
* Install drivers manually
* Restart and verify hardware functionality

---

## Challenges Faced

* Boot Camp does not support Windows 10 on this model
* Missing drivers after OS installation
* USB boot failures using common tools
* Apple EFI firmware quirks
* Limited official documentation for this setup

Each issue was resolved through testing, research, and persistence.

---

## Results and Performance

After installation and optimization:

* System runs cooler than macOS
* Battery life improved under normal workloads
* Full hardware functionality restored
* Stable daily-use performance achieved

### Software and Gaming Support

The system now supports:

* Modern development tools (Visual Studio, Docker, WSL)
* Productivity applications
* Messaging apps (e.g., WhatsApp)
* Native gaming via DirectX without emulation

---

## Why Windows Over macOS (On This Hardware)

macOS enforces:

* OS version restrictions
* Limited application compatibility
* Poor gaming support
* Hardware upgrade dependency

Windows provides:

* Greater software compatibility
* Better backward support
* More control over system configuration
* Stronger utilization of older hardware

This project demonstrates that macOS is not always the optimal choice for older Apple devices.

---

## What I Learned

* Apple EFI firmware behavior and limitations
* Manual driver management on unsupported systems
* Differences in OS-level performance and thermals
* Importance of documentation and reproducibility
* Practical problem-solving without official support

---

## Future Improvements

* Automate driver installation
* Add thermal and performance benchmarks
* Include screenshots and diagrams
* Explore recovery or dual-boot options

---

## Final Thoughts

This project reflects independent problem-solving, system-level understanding, and practical engineering decisions. It focuses on extending hardware lifespan, improving usability, and reclaiming control from vendor restrictions.
