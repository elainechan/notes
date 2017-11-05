# Linux Notes

## Components
### Kernel
* glue between hardware and applications
    * Generic proprietary apps (Adobe Flash drivers)
    * Generic free apps (bash, LibreOffice, X Window System)
    * Distribution-specific apps (Package Management, configuration utilities)
    * Manuals for app commands, configs, etc.
    * Support services, commercial, community, etc.

### Distribution
* collection of software making up a Linux-based OS
* includes kernel, C/C++ compiler, gdb debugger, system libraries, etc.
    * Debian
        * Ubuntu
        * Linux Mint
    * Fedora
        * RHEL
            * CentOS (binary-compatible)
            * Oracle Linus
    * SUSE

### Boot loader
* program that boots the OS
    * GRUB
    * ISOLINUX

### Service
* program that runs as a background process

### Filesystem
* method for storing and organizing files

### X Window system
* provides standard toolkit and protocols to build GUIs
    * GUI
        * Desktop
        * Window Manager
        * X Window System / X11
    * Console
        * CLI/Shell
        * Kernel
        * Hardware

### Desktop environment
* GUI on top of OS
    * GNOME, KDE, Xfce, Fluxbox

### Command line
* Interface for typing commands on top of OS
* Shell
    * command line interpreter
    * interprets the command line input
    * instructs the OS to perform necessary tasks and commands
---
## Boot Process

### Control Flow
1. Power on
2. Basic Input/Output System (BIOS) or Power-on Self-test (POST)
3. Boot loader (e.g. GRUB)
    * load kernel image and initial RAM disk or filesystem into memory
    * filesystem contains critical files and device drivers needed to start the system) 
4. Kernel
    * runs `sbin/init`
    * systemd command `systemctl` used for most tasks
