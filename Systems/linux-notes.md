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
[Filesystem Hierarchy Standard](https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.pdf)

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

---
# Cheatsheet
- [Link](http://www.cs.cmu.edu/~213/recitations/fwunixref.pdf)
Unix/Linux Command Reference .com
File Commands
ls – directory listing
ls -al – formatted listing with hidden files
cd dir – change directory to dir
cd – change to home
cd - – change back to previous directory
pwd – show current directory
mkdir dir – create a directory dir
rm file – delete file
rm -r dir – delete directory dir
rm -f file – force remove file
rm -rf dir – force remove directory dir *
cp file1 file2 – copy file1 to file2
cp -r dir1 dir2 – copy dir1 to dir2; create dir2 if it
doesn't exist
mv file1 file2 – rename or move file1 to file2
if file2 is an existing directory, moves file1 into
directory file2
ln -s file link – create symbolic link link to file
touch file – create or update file
cat > file – places standard input into file
more file – output the contents of file
head file – output the first 10 lines of file
tail file – output the last 10 lines of file
tail -f file – output the contents of file as it
grows, starting with the last 10 lines
Process Management
ps – display your currently active processes
top – display all running processes
kill pid – kill process id pid
killall proc – kill all processes named proc *
jobs – lists stopped or background jobs
bg – resume a stopped job in the background
fg – brings the most recent job to foreground
fg n – brings job n to the foreground
File Permissions
chmod octal file – change the permissions of file
to octal, which can be found separately for user,
group, and world by adding:
● 4 – read (r)
● 2 – write (w)
● 1 – execute (x)
Examples:
chmod 777 – read, write, execute for all
chmod 755 – rwx for owner, rx for group and world
For more options, see man chmod.
SSH
ssh [-p port] user@host – connect to host as user,
optionally on custom port port
scp [-P port] user@host:path1 path2 – copy the
remote file at path1 to local location path2
ssh-copy-id user@host – add your key to host for
user to enable a keyed or passwordless login
Searching
grep pattern files – search for pattern in files
grep -r pattern dir – search for pattern in dir
command | grep pattern – search for pattern in the
output of command
locate file – find all instances of file
System Info
date – show the current date and time
cal – show this month's calendar
uptime – show current uptime
w – display who is online
whoami – who you are logged in as
finger user – display information about user
uname -a – show kernel information
cat /proc/cpuinfo – cpu information
cat /proc/meminfo – memory information
man command – show the manual for command
df – show disk usage
du – show directory space usage
free – show memory and swap usage
whereis app – show possible locations of app
which app – show which app will be run by default
type app – show which app or builtin will be run
Compression
tar cf file.tar files – create a tar named
file.tar containing files
tar xf file.tar – extract the files from file.tar
tar czf file.tar.gz files – create a tar with
Gzip compression
tar xzf file.tar.gz – extract a tar using Gzip
tar cjf file.tar.bz2 – create a tar with Bzip2
compression
tar xjf file.tar.bz2 – extract a tar using Bzip2
gzip file – compresses file and renames it to
file.gz
gzip -d file.gz – expands file.gz back to file
Network
ping host – ping host and output results
whois domain – get whois information for domain
dig domain – get DNS information for domain
dig -x host – reverse lookup host
wget file – download file
wget -c file – continue a stopped download
Installation
Install from source:
./configure
make
make install
dpkg -i pkg.deb – install a package (Debian)
rpm -Uvh pkg.rpm – install a package (RPM)
Shortcuts
Ctrl+C – halts the current command
Ctrl+Z – stops the current command, resume with
fg in the foreground or bg in the background
Ctrl+D – log out of current session, similar to exit
Ctrl+W – erases one word in the current line
Ctrl+U – erases the whole line
Ctrl+R – type to bring up a recent command
!! - repeats the last command
exit – log out of current session
* use with extreme caution.
