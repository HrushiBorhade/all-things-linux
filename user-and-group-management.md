# User and Group Management Commands

This guide provides detailed information about essential Linux user and group management commands, including user creation, modification, and group administration.

| Command | Description |
|---------|-------------|
| [`sudo`](#sudo) | Execute commands with superuser privileges |
| [`useradd`](#useradd) | Create a new user account |
| [`whoami`](#whoami) | Display current user name |
| [`su`](#su) | Switch to another user account |
| [`passwd`](#passwd) | Change user password |
| [`userdel`](#userdel) | Delete a user account |
| [`groupadd`](#groupadd) | Create a new group |
| [`gpasswd`](#gpasswd) | Administer groups |
| [`groupdel`](#groupdel) | Delete a group |


### sudo
Execute commands with superuser privileges
```zsh
~ sudo command               # Execute command as root
~ sudo -i                    # Start a root shell
~ sudo -l                    # List allowed commands
~ sudo -u username command   # Run command as specific user
```

### useradd
Create a new user account
```zsh
~ sudo useradd username                  # Create new user
~ sudo useradd -m username               # Create user with home directory
~ sudo useradd -m -s /bin/bash username  # Create user with specific shell
~ sudo useradd -G group1,group2 username # Create user and add to groups
```

### whoami
Display current user name
```zsh
~ whoami                     # Show current username
~ whoami | id               # Show username and ID information
```

### su
Switch to another user account
```zsh
~ su                        # Switch to root user
~ su username               # Switch to specific user
~ su - username             # Switch with environment
~ su -c 'command'          # Execute single command as root
```

### passwd
Change user password
```zsh
~ passwd                    # Change own password
~ sudo passwd username      # Change another user's password
~ passwd -l username       # Lock user account
~ passwd -u username       # Unlock user account
```

### userdel
Delete a user account
```zsh
~ sudo userdel username            # Delete user
~ sudo userdel -r username         # Delete user and home directory
~ sudo userdel -f username         # Force delete user
```

### groupadd
Create a new group
```zsh
~ sudo groupadd groupname          # Create new group
~ sudo groupadd -g 1000 groupname  # Create group with specific GID
```

### gpasswd
Administer groups
```zsh
~ sudo gpasswd -a username groupname  # Add user to group
~ sudo gpasswd -d username groupname  # Remove user from group
~ sudo gpasswd -M user1,user2 group   # Set group members
```

### groupdel
Delete a group
```zsh
~ sudo groupdel groupname          # Delete group
~ sudo groupdel -f groupname       # Force delete group
``` 