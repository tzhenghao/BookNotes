magic SysRq key

Magic SysRq is invoked with the combination of the Alt and SysRq keys on the PC keyboard, or with other special keys on other platforms (see Documentation/sysrq.txt for details), and is available on the serial console as well. A third key, pressed along with these two, performs one of a number of useful actions:

r Turns off keyboard raw mode; useful in situations where a crashed application (such as the X server) may have left your keyboard in a strange state.

k Invokes the “secure attention key” (SAK) function. SAK kills all processes run- ning on the current console, leaving you with a clean terminal.

s Performs an emergency synchronization of all disks. 

u Umount. Attempts to remount all disks in a read-only mode. This operation, usually invoked immediately after s, can save a lot of filesystem checking time in cases where the system is in serious trouble. 

b Boot. Immediately reboots the system. Be sure to synchronize and remount the disks first. 

p Prints processor registers information. t Prints the current task list.

m Prints memory information 

Sysrq operations

Live hang  - driver is stuck in a loop but the system as a whole is still functioning.

Precaution - When chasing system hangs, mount all disks as read-only (or unmount them).
	- No risk of damaging the filesystem.

Using GDB
Compile kernel with CONFIG_DEBUG_INFO option set to get symbols.

Kdb Kernel Debugger

User-Mode Linux (UML) - with own arch/um subdirectory.

Linux Trace Toolkit (LTT) - allows tracing of events in the kernel.
