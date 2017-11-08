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

## Linux Requirements
[Source](https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.pdf)

### Root Filesystem
* `bin` - Essential command binaries
* `boot` - Static files of the boot loader
* `dev` - Device files
* `etc` - Host-specific system configuration
* `lib` -  Essential shared libraries and kernel modules
* `media` - Mount point for removable media
* `mnt` - Mount point for mounting a filesystem temporarily
* `opt` - Add-on application software packages
* `run` - Data relevant to running processes
* `sbin` - Essential system binaries
* `srv` - Data for services provided by this system
* `tmp` - Temporary files
* `usr` - Secondary hierarchy
* `var` - Variable data

### Essential User Command Binaries
* `cat`  Utility to concatenate files to standard output
* `chgrp`  Utility to change file group ownership
* `chmod`  Utility to change file access permissions
* `chown`  Utility to change file owner and group
* `cp`  Utility to copy files and directories
* `date`  Utility to print or set the system data and time
* `dd`  Utility to convert and copy a file
* `df`  Utility to report filesystem disk space usage
* `dmesg`  Utility to print or control the kernel message buffer
* `echo`  Utility to display a line of text
* `false`  Utility to do nothing, unsuccessfully
* `hostname`  Utility to show or set the system's host name
* `kill`  Utility to send signals to processes
* `ln`  Utility to make links between files
* `login`  Utility to begin a session on the system
* `ls`  Utility to list directory contents
* `mkdir`  Utility to make directories
* `mknod`  Utility to make block or character special files
* `more`  Utility to page through text
* `mount`  Utility to mount a filesystem
* `mv`  Utility to move/rename files
* `ps`  Utility to report process status
* `pwd`  Utility to print name of current working directory
* `rm`  Utility to remove files or directories
* `rmdir`  Utility to remove empty directories
* `sed`  The 'sed' stream editor
* `sh`  POSIX compatible command shell
* `stty`  Utility to change and print terminal line settings
* `su`  Utility to change user ID
* `sync`  Utility to flush filesystem buffers
* `true`  Utility to do nothing, successfully
* `umount`  Utility to unmount file systems
* `uname`  Utility to print system information

## Optional Command Binaries
* `csh`  The C shell (optional)
* `ed`  The 'ed' editor (optional)
* `tar`  The tar archiving utility (optional)
* `cpio`  The cpio archiving utility (optional)
* `gzip`  The GNU compression utility (optional)
* `gunzip`  The GNU uncompression utility (optional)
* `zcat`  The GNU uncompression utility (optional)
* `netstat`  The network statistics utility (optional)
* `ping`  The ICMP network test utility (optional)
