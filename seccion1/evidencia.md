#------------------------**Section 1**----------------------------------


1. What is LUKS and what is its relationship with dm-crypt in the Linux kernel? 
Explain the role of the device mapper in the encryption process

.“It is by far the most common means of encrypting block devices used in various Linux-based systems.” (Llc, s. f.).
They work together: when a LUKS volume is unlocked, it uses the password to obtain 
the master key and configure dm-crypt. The device mapper acts as an intermediary
layer that creates a virtual device and directs read and write operations,
allowing dm-crypt to intercept the data and encrypt or decrypt it before it reaches the physical disk.

2. What is the difference between full disk encryption (FDE) and filesystem-level encryption? 
Mention 2 advantages and 2 limitations of each.

Full Disk Encryption (FDE) treats the entire storage device as a single encrypted block, 
effectively blinding an attacker to everything including the OS and 
file metadata while providing seamless "set-it-and-forget-it" protection against physical theft.

---FDE – Advantages:
Transparent: Once unlocked, the system works normally without user intervention. 
Strong protection for data at rest (e.g., if the device is stolen, everything is encrypted). 
---FDE – Limitations:
Data is accessible once the system is unlocked (no per-file/user protection). 
Requires entering a password at boot (or using a key), which can complicate automation. 

---Filesystem-level encryption – Advantages:
Fine-grained control: you can encrypt specific files or user data only. 
Supports multi-user environments with separate keys per user. 
---Filesystem-level encryption – Limitations:
More complex to manage (key handling, configuration). 
Metadata (like filenames, sizes, or structure) may still be exposed depending on the method.

3. What is LVM and what are its three abstraction layers (PV, VG, LV)? 
What advantages does LVM offer compared to traditional partitioning in a server environment? 

“In the context of storage, a Logical Volume Manager (LVM) is a framework that 
allows space to be allocated on mass storage devices in a more flexible way than 
conventional partitioning schemes.” (Santos & Santos, 2025).
By using three distinct abstraction layers: Physical Volumes (PV), which are the raw disks or partitions initialized for LVM; Volume Groups (VG), which pool 
the capacity of multiple PVs into a single storage "reservoir"; and Logical Volumes (LV), 
which are the virtual partitions carved out of the VG and formatted with a filesystem.

4. Explain what happens during the boot process of a system with LUKS + LVM: at 
What point is the decryption password requested and what role does GRUB play in this process?

In a system using LUKS + LVM, the boot process starts with the firmware (BIOS/UEFI) loading GRUB, which is usually installed on an unencrypted /boot partition 
because it needs to read the kernel and initramfs (It is a small, compressed, temporary 
file system that loads the Linux kernel into RAM during boot) without decryption.
GRUB loads the Linux kernel and the initramfs into memory and then hands control over to the kernel.
The decryption password is requested during the early userspace stage, when the 
initramfs runs it uses tools like cryptsetup to unlock the LUKS-encrypted partition. 
Once unlocked, the system gains access to the underlying physical volume, allowing 
LVM to activate its volume groups and logical volumes.



 
**List of Captures**:
1. Download and install VirtualBox
2. Create a profile in VirtualBox with Debian
3. Download the ISO of Debian13
4. Install Debian13 with the graphical installer
5. Set a password (any)
6. Encrypt the disk
7. Create logical volumes
8. Enter the LUKS encryption password
9. Select the default options
10. Review
11. Installing and insert the password
12. Run "lsblk"
13. Fix permission issues
14. Run "sudo pvs"
15. Run "sudo vgs"
16. Run "sudo lvs"
