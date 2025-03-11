# System Level Commands

This guide provides detailed information about essential Linux system commands, including system information, user management, and package management tools.

| Command                 | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| [`uname`](#uname)       | Display system information including kernel version       |
| [`uptime`](#uptime)     | Show how long the system has been running                 |
| [`date`](#date)         | Display or set system date and time                       |
| [`who`](#who)           | Show who is logged on                                     |
| [`whoami`](#whoami)     | Print effective user ID                                   |
| [`which`](#which)       | Locate a command in system PATH                           |
| [`id`](#id)             | Print user and group information                          |
| [`sudo`](#sudo)         | Execute a command as another user (typically root)        |
| [`shutdown`](#shutdown) | Bring the system down safely                              |
| [`reboot`](#reboot)     | Restart the system                                        |
| [`apt`](#apt)           | Package management for Debian-based systems               |
| [`yum`](#yum)           | Package management for older RHEL-based systems           |
| [`dnf`](#dnf)           | Next generation package management for RHEL-based systems |
| [`pacman`](#pacman)     | Package management for Arch Linux                         |
| [`portage`](#portage)   | Package management for Gentoo Linux                       |

## System Information Commands

### uname
Display system information
```zsh
~ uname -a                    # Print all system information
~ uname -s                    # Print kernel name
~ uname -r                    # Print kernel release
~ uname -m                    # Print machine hardware name
```

### uptime
Show system running time and load
```zsh
~ uptime                      # Show uptime and load averages
~ uptime -p                   # Show uptime in pretty format
~ uptime -s                   # Show system up since
```

### date
Display or set system date and time
```zsh
~ date                        # Show current date and time
~ date "+%Y-%m-%d"           # Show date in specific format
~ date "+%H:%M:%S"           # Show time in specific format
~ sudo date -s "string"      # Set system date and time
```

## User Information Commands

### who
Show who is logged on
```zsh
~ who                         # List logged in users
~ who -b                      # Time of last system boot
~ who -r                      # Show run level
~ who -a                      # Show all information
```

### whoami
Print effective username
```zsh
~ whoami                      # Show current username
```

### which
Locate a command
```zsh
~ which command              # Show full path of command
~ which -a command          # Show all instances
```

### id
Print user and group information
```zsh
~ id                         # Show current user info
~ id username               # Show specific user info
~ id -g                     # Print effective group ID
~ id -G                     # Print all group IDs
```

## System Control Commands

### sudo
Execute command as another user
```zsh
~ sudo command              # Run command as root
~ sudo -i                   # Start root shell
~ sudo -l                   # List allowed commands
~ sudo -u user command     # Run as specific user
```

### shutdown
Shutdown the system
```zsh
~ sudo shutdown -h now      # Shutdown immediately
~ sudo shutdown -h +5      # Shutdown in 5 minutes
~ sudo shutdown -r now     # Reboot immediately
~ sudo shutdown -c         # Cancel pending shutdown
```

### reboot
Reboot the system
```zsh
~ sudo reboot              # Reboot system
~ sudo reboot -f           # Force reboot
```

## Package Managers

### apt
Debian/Ubuntu package manager
```zsh
~ sudo apt update          # Update package list
~ sudo apt upgrade        # Upgrade all packages
~ sudo apt install pkg    # Install package
~ sudo apt remove pkg     # Remove package
~ apt search pkg         # Search for package
~ apt show pkg           # Show package details
```

### yum
RHEL/CentOS package manager
```zsh
~ sudo yum update         # Update all packages
~ sudo yum install pkg   # Install package
~ sudo yum remove pkg    # Remove package
~ yum search pkg        # Search for package
~ yum info pkg          # Show package info
```

### dnf
Fedora/RHEL package manager
```zsh
~ sudo dnf update         # Update all packages
~ sudo dnf install pkg   # Install package
~ sudo dnf remove pkg    # Remove package
~ dnf search pkg        # Search for package
~ dnf info pkg          # Show package info
```

### pacman
Arch Linux package manager
```zsh
~ sudo pacman -Syu       # Update system
~ sudo pacman -S pkg    # Install package
~ sudo pacman -R pkg    # Remove package
~ pacman -Ss pkg       # Search for package
~ pacman -Si pkg       # Show package info
```

### portage
Gentoo package manager
```zsh
~ sudo emerge --sync     # Update repository
~ sudo emerge -av pkg   # Install package
~ sudo emerge -C pkg    # Remove package
~ emerge -s pkg        # Search for package
~ emerge -i pkg        # Show package info
``` 