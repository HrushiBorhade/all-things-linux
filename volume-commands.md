# Linux Volume Commands

This guide provides detailed information about essential Linux volume management commands, including disk partitioning, logical volume management, and filesystem operations.

| Command | Description |
|---------|-------------|
| [`fdisk`](#fdisk) | Manipulate disk partition table |
| [`parted`](#parted) | A more powerful partition manipulation tool |
| [`lsblk`](#lsblk) | List block devices |
| [`mount`](#mount) | Mount a filesystem |
| [`umount`](#umount) | Unmount a filesystem |
| [`mkfs`](#mkfs) | Build a Linux filesystem |
| [`fsck`](#fsck) | Check and repair a Linux filesystem |
| [`lvm`](#lvm) | Logical Volume Manager tools |
| [`blkid`](#blkid) | Locate/print block device attributes |
| [`findmnt`](#findmnt) | Find a filesystem |

### fdisk
Manipulate disk partition table
```zsh
~ fdisk -l                    # List all partitions
~ fdisk /dev/sda             # Start fdisk on specific device
~ fdisk -l /dev/sda          # Show partitions on specific device
~ fdisk -s /dev/sda1         # Show size of a partition
```

Example output:
```
Disk /dev/sda: 500 GB, 500107862016 bytes
255 heads, 63 sectors/track, 60801 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes

   Device Boot      Start         End      Blocks   Id  System
/dev/sda1   *           1          13      104391   83  Linux
/dev/sda2              14       60801    487725345   8e  Linux LVM
```

### parted
A more powerful partition manipulation tool
```zsh
~ parted -l                   # List all partitions
~ parted /dev/sda print      # Show partition table
~ parted /dev/sda mklabel    # Create new partition table
~ parted /dev/sda mkpart     # Create new partition
```

Example output:
```
Model: ATA SAMSUNG HD502HJ (scsi)
Disk /dev/sda: 500GB
Sector size (logical/physical): 512B/512B
Partition Table: gpt

Number  Start   End     Size    File system  Name  Flags
 1      1049kB  500GB   500GB   ext4         root
```

### lsblk
List block devices
```zsh
~ lsblk                      # List all block devices
~ lsblk -f                  # Show filesystem information
~ lsblk -m                  # Show permissions info
~ lsblk -o NAME,SIZE,TYPE   # Custom output format
```

Example output:
```
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0   500G  0 disk 
├─sda1   8:1    0   100M  0 part /boot
└─sda2   8:2    0 499.9G  0 part /
```

### mount
Mount a filesystem
```zsh
~ mount /dev/sda1 /mnt      # Mount device to directory
~ mount -t ext4 /dev/sda1   # Mount with specific filesystem
~ mount -a                  # Mount all in fstab
~ mount | grep sda          # Show mounted devices
```

Example output:
```
/dev/sda1 on /boot type ext4 (rw,relatime,data=ordered)
/dev/sda2 on / type ext4 (rw,relatime,data=ordered)
```

### umount
Unmount a filesystem
```zsh
~ umount /mnt               # Unmount by directory
~ umount /dev/sda1         # Unmount by device
~ umount -f /mnt           # Force unmount
~ umount -a                # Unmount all
```

Example output:
```
umount: /dev/sda1 unmounted successfully
```

### mkfs
Build a Linux filesystem
```zsh
~ mkfs.ext4 /dev/sda1       # Create ext4 filesystem
~ mkfs -t ext4 /dev/sda1    # Alternative syntax
~ mkfs.xfs /dev/sda2        # Create XFS filesystem
~ mkfs.vfat /dev/sda3       # Create FAT filesystem
```

Example output:
```
mke2fs 1.45.5 (07-Jan-2020)
Creating filesystem with 131072 4k blocks and 32768 inodes
Filesystem UUID: f7f3c453-7c1f-4e48-a28f-a1d3d7234554
```

### fsck
Check and repair a Linux filesystem
```zsh
~ fsck /dev/sda1            # Check filesystem
~ fsck -f /dev/sda1        # Force check
~ fsck -y /dev/sda1        # Auto-repair
~ fsck -t ext4 /dev/sda1   # Check specific filesystem
```

Example output:
```
fsck from util-linux 2.34
e2fsck 1.45.5 (07-Jan-2020)
/dev/sda1: clean, 11/32768 files, 8500/131072 blocks
```

### lvm
Logical Volume Manager tools
```zsh
~ pvcreate /dev/sda2        # Create physical volume
~ vgcreate vg0 /dev/sda2    # Create volume group
~ lvcreate -L 10G vg0       # Create logical volume
~ lvdisplay                 # Show logical volumes
```

Example output:
```
  --- Volume group ---
  VG Name               vg0
  System ID            
  Format                lvm2
  Metadata Areas        1
  Metadata Sequence No  2
  VG Access            read/write
```

### blkid
Locate/print block device attributes
```zsh
~ blkid                     # Show all block devices
~ blkid /dev/sda1          # Show specific device
~ blkid -L root            # Search by label
~ blkid -U uuid            # Search by UUID
```

Example output:
```
/dev/sda1: UUID="f7f3c453" TYPE="ext4" PARTUUID="1234-5678"
/dev/sda2: UUID="abcd-efgh" TYPE="swap" PARTUUID="8765-4321"
```

### findmnt
Find a filesystem
```zsh
~ findmnt                   # List all mounted filesystems
~ findmnt /dev/sda1        # Show where device is mounted
~ findmnt -t ext4          # List ext4 filesystems
~ findmnt -S UUID=value    # Find by UUID
```

Example output:
```
TARGET   SOURCE    FSTYPE OPTIONS
/        /dev/sda2 ext4   rw,relatime
├─/boot  /dev/sda1 ext4   rw,relatime
└─/home  /dev/sda3 ext4   rw,relatime
``` 