# Linux File system

## Everything is a file

In Linux, the philosophy "everything is a file" is one of the most powerful and elegant design principles. This abstraction means that every system resource - whether it's hardware, processes, or actual data - is represented and accessed through the filesystem hierarchy. Here's how this principle manifests:

1. Regular Files
- Text files, images, programs
- What most people traditionally think of as "files"
- Stored in the filesystem with a specific location/path

2. Directories
- Special files that can contain other files
- Also represented as files themselves
- Even the root directory (/) is a file

3. Device Files (/dev directory)
- Hard drives: /dev/sda, /dev/sdb
- Terminals: /dev/tty0
- Random number generator: /dev/random
- Null device: /dev/null
- Even your mouse (/dev/input/mouse0) and keyboard are represented as files

4. Process Information (/proc directory)
- Each running process has its own directory under /proc
- Process ID 1234 would be at /proc/1234
- Contains files representing memory usage, environment variables, command line arguments
- CPU information: /proc/cpuinfo
- Memory information: /proc/meminfo

5. System Configuration (/sys directory)
- Hardware information
- Kernel parameters
- Device configurations
- Power management settings

6. Network Interfaces
- Network interfaces are configured through files
- /etc/network/interfaces or NetworkManager configuration files

Practical Implications:

1. Unified I/O Operations
```bash
# Reading from a file
cat myfile.txt

# Reading from a device
cat /dev/random

# Reading process information
cat /proc/cpuinfo

# All use the same read operation!
```

2. Redirection Works Universally
```bash
# Save hardware info to a file
cat /proc/cpuinfo > hardware_info.txt

# Send file content to a device
echo "test" > /dev/tty1

# Feed random data to a program
program < /dev/random
```

3. Permissions Apply Consistently
```bash
# Check permissions on a regular file
ls -l myfile.txt

# Check permissions on a device file
ls -l /dev/sda

# Both use the same permission system
```

4. File Operations are Universal
```bash
# Copy from a device to a file
cp /dev/input/mouse0 mouse_events.log

# Write to a network interface configuration
echo "nameserver 8.8.8.8" > /etc/resolv.conf
```

Benefits of This Design:

1. Simplicity
- One consistent interface for all system resources
- Same commands and tools work everywhere
- Reduces the need for special APIs

2. Flexibility
- Easy to create new resource types
- Consistent access methods
- Simple to script and automate

3. Security
- Unified permission system
- Consistent access control
- Easy to audit and manage

4. Interoperability
- Programs can interact using standard file operations
- No need for complex protocols or interfaces
- Easy to chain commands together

This principle is so powerful that even Windows and macOS have adopted aspects of it, though not to the same extent as Linux. Understanding this concept is crucial for effective Linux system administration and development, as it underlies many of the operating system's most powerful features and capabilities.

When you grasp that everything is a file in Linux, many complex operations become simpler to understand and manage. You can use familiar file operations to interact with hardware, monitor processes, configure the system, and manage resources in a consistent and predictable way.
## Directory explained

```bash
# Root directory listing with descriptions
/
├── bin -> usr/bin     # Essential command binaries
├── boot              # Boot loader files, kernel, initrd
├── dev               # Device files
├── etc               # System configuration files
├── home              # User home directories
├── lib -> usr/lib    # Essential shared libraries
├── media             # Mount points for removable media
├── mnt               # Temporary mount points
├── opt               # Optional application software packages
├── proc              # Virtual filesystem for kernel info
├── root              # Home directory for root user
├── run               # Run-time variable data
├── sbin -> usr/sbin  # System binaries
├── srv               # Data for services provided by system
├── sys               # Virtual filesystem for system info
├── tmp               # Temporary files
├── usr               # User utilities and applications
└── var               # Variable files (logs, mail, etc.)

```


- `/bin` (Binary): 

- This directory contains essential command binaries that need to be available in single-user mode. 
- In modern Linux systems, `/bin` is typically symbolically linked to `/usr/bin`. 
- These commands are used by both the system administrator and users. Examples include ls, cp, and pwd.

- `/boot`: This crucial directory contains everything required for the boot process. Here you'll find:
- The kernel itself (usually named `vmlinuz-[version]`)
- Initial RAM disk (`initrd` or `initramfs`)
- Boot loader configuration files (`GRUB`)
- System map files

- `/dev` (Devices): This directory contains device files, which are special files that represent system hardware. For example:
- `/dev/sda` represents your first hard drive
- `/dev/tty1` represents the first terminal
- `/dev/null` is a special file that discards all data written to it
These aren't actual files but interfaces for the kernel to communicate with hardware.

`/etc` (Etcetera): This directory contains system-wide configuration files. Some key files include:
- /etc/passwd (user account information)
- /etc/fstab (filesystem mount configuration)
- /etc/hosts (system host names)
- /etc/network/ (network configuration)
Any system-wide configuration changes are typically made here.

`/home`:
This directory contains user home directories. Each user gets their own subdirectory (e.g., /home/john) where they can store their personal files, configuration files (dotfiles), and custom settings.

`/lib` (Library):
Contains essential shared libraries needed by the /bin and /sbin programs. In modern systems, it's usually symbolically linked to /usr/lib. These libraries are crucial for basic system functionality.

`/media` and `/mnt`:
Both directories are used for mounting filesystems:
- `/media` is typically used for removable media (USB drives, CD-ROMs)
- `/mnt` is used for temporarily mounted filesystems

`/opt` (Optional):
This directory is reserved for add-on application software packages. For example, proprietary software like Google Chrome might install here. It's designed to contain self-contained directories that don't split their components across the filesystem.

`/proc` (Process):
A virtual filesystem that provides information about running processes and system resources. It doesn't exist on disk but in memory. For example:
- `/proc/cpuinfo` shows CPU information
- `/proc/meminfo` displays memory usage
- Each running process has its own directory named after its process ID

`/root`:
The home directory for the root user (system administrator). Unlike regular users' home directories, this is located at the root level for accessibility in case /home can't be mounted.

`/run`:
Contains run-time variable data like currently running system services' PID files and lock files. This directory is typically cleared on reboot.

`/sbin` (System Binary):
Contains essential system binaries that are used for system administration tasks. Usually linked to /usr/sbin in modern systems. These commands are typically used by the system administrator.

`/srv` (Service):
Holds data for services provided by the system. If you're running a web server, for instance, you might store your web files in /srv/www.

`/sys` (System):
Another virtual filesystem like /proc that provides information about devices, drivers, and some kernel features. It's part of the sysfs interface to the kernel.

`/tmp` (Temporary):
Directory for temporary files. Programs can create temporary files here that don't need to persist between reboots. Many systems clear this directory on boot.

`/usr` (Unix System Resources):
Contains the majority of user utilities and applications. It has its own hierarchy:
- /usr/bin: User commands
- /usr/lib: Libraries
- /usr/local: Locally installed software
- /usr/share: Architecture-independent data

`/var` (Variable):
Contains variable data files including:
- System log files (/var/log)
- Mail queues (/var/mail)
- Print spools (/var/spool)
- Temporary files needed across reboots
- Web server files (/var/www)
