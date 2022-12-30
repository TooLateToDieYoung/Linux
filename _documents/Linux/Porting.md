# Introduction
- Bulid a cross-compilation environment.
- Identify the boot loader and port it.
- Configure, compile and port the kernel.
- Bulid the file system and mount the root directory.

---

# Cross-compilation environment

  ## 1. What is a cross-compilation environment?
  - Use local host device to compile a program which is running on another device. 
  - For example, compile a linux program under windows 10.

  ## 2. Why do we need a cross-compilation environment?
  - Local host device computes faster than ported target device.
  - Different hardware cores require specific instruction set.
  - Set up target device before loading its OS.

  ## 3. How can we bulid a cross-compilation environment?
  - Find the appropriate cross-compilation chain for the hardware core of the target device.
  - Suggest to add the cross-compilation commands to the environment variables.
  - Prepare an interface to connect the local host device and the target device.
  - Try to compile the test program and download to target device.

---

# Boot Loader

  ## 1. What is a boot loader?
  - A program that initialize the device before the OS kernel runs.
  - There are many kinds of boot loaders, and the most commonly used one in Linux OS is U-Boot.

  ## 2. How does a boot loader work?
  - Power ON.
  - BIOS set up the hardware, including to reset watch dog, interrupts, configure CPU clock, initialize SDRAM, etc.
  - GRUB loads first sector (typically 512 bytes), called Master Boot Record (MBR) that contains part of the boot loader.
  - Copy part of boot loader to RAM, then set up the heap and stack pointers.
  - Jump to the C entry, check the memory map.
  - Read OS kernel and root file system from FLASH to RAM.
  - Control of the system hands over to kernel. 

---
