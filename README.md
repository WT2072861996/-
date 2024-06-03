# Hackintosh Installation Guide

## Introduction
This guide will walk you through the process of installing macOS on a PC (commonly known as creating a Hackintosh). Please note that installing and using a Hackintosh may violate Apple's macOS licensing agreement. Ensure you use this guide within the legal boundaries and have a legitimate copy of macOS.

## Preparations

### Hardware Requirements
- Intel CPU (4th generation or newer recommended)
- Compatible motherboard (UEFI supported motherboard recommended)
- At least 8GB of RAM
- Dedicated GPU (AMD or compatible NVIDIA card recommended)
- An empty hard drive or partition (at least 50GB)

### Software Requirements
- A legitimate copy of macOS (e.g., downloaded from Apple's Mac App Store)
- A USB flash drive with at least 16GB of space
- [Clover EFI bootloader](https://github.com/CloverHackyColor/CloverBootloader)
- [OpenCore bootloader](https://github.com/acidanthera/OpenCorePkg) (optional)
- [GibMacOS](https://github.com/corpnewt/gibMacOS) tool

## Steps

### Step 1: Create macOS Installation USB

1. Download and run [GibMacOS](https://github.com/corpnewt/gibMacOS):
    - Clone or download the repository and run `gibMacOS.bat` (Windows) or `gibMacOS.command` (macOS).
    - Download the macOS installation files (e.g., `macOS Catalina` or `macOS Big Sur`).

2. Create a macOS installation USB using terminal commands:
    ```bash
    sudo /Applications/Install\ macOS\ Sonoma.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
    ```
    (Replace `Install\ macOS\ Sonoma.app` with the actual path to the installation file, and `MyVolume` with the name of your USB drive)

### Step 2: Install Bootloader

1. Download and install [Clover EFI bootloader](https://github.com/CloverHackyColor/CloverBootloader):
    - Install Clover EFI on your USB drive.
    - Copy the `Clover` folder to the EFI partition.

2. Configure the `config.plist` file:
    - Use Clover Configurator or PlistEdit Pro to edit the `config.plist`.
    - Set appropriate patches and parameters according to your hardware configuration.

### Step 3: Install macOS

1. Boot into BIOS/UEFI settings on your PC:
    - Enable AHCI mode.
    - Disable secure boot.
    - Set the USB drive as the primary boot device.

2. Boot from the USB drive and select macOS installation:
    - Use Clover to boot into the macOS installer.
    - Follow the on-screen instructions to install macOS.

### Step 4: Post-Installation Configuration

1. After installing macOS, reboot into the USB drive and select the installed macOS system.

2. Reinstall Clover on your macOS system drive:
    - Copy the `Clover` folder to the EFI partition of the system drive.

3. Install necessary kexts (drivers):
    - For example, `Lilu.kext`, `WhateverGreen.kext`, and other kexts suitable for your hardware.

### Step 5: Debugging and Optimization

1. Ensure all hardware is functioning correctly:
    - Sound card, network, GPU, etc.

2. Use tools like Hackintool or IORegistryExplorer for debugging and optimization.

## Conclusion
Installing a Hackintosh is a challenging task, but by following these steps and performing proper debugging, you can enjoy the powerful features of macOS on non-Apple hardware.

## Disclaimer
This guide is for educational and research purposes only. Please ensure you use this guide within legal boundaries and respect Apple's software licensing agreements.

## License
This project is licensed under the MIT License. For more details, see the [LICENSE](LICENSE) file.
