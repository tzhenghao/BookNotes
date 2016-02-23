Technical reasons to use Embedded Linux:
	1. SSL/SSH
	2. Apache + other web servers
	3. C library
	4. Berkeley sockets - access to high performance network stack
	5. Standards based - open source


Features:
	1. Manage tasks, isolate them from the kernel and each other.
	2. Uniform interface for system's hardware resources.
	3. OS internal data structures are off limits to user programs.
	4. MMU - virtual memory-management system

Level of indirection from MMU - can handle or pass along to the offending process.
Without it, may go unnoticed until some other part of the program fails because its memory has been corrupted by another process.

System Calls - create an entry in a vector that points to an entry point for the routine.
	- Data from application's memory space gets copied over to kernel memory space.

Peripheral Support

SELinux - NSA introduced concepts like:
	1. Data protection
	2. Program isolation
	3. Security policies
	4. Mandatory Access Control (MAC) model - least priviledge concept

Pluggable Authentication Modules (PAM)
Use LDAP to decide who has access to a device.

May want to recompile boot loader to remove functionality to conserve space and increase boot time

GRUB and LILO ARE NOT bootloaders. They are just loaders.

Boot loader contained in BIOS of the machine read these programs from a certain sector of a disk.

System that uses flash memory for storage mounts a RAM-based file system for temporary storage because:
	1. It's faster
	2. Flash memory has smaller duty cycle than RAM.

Small C library implementations with uClibc being most common.
