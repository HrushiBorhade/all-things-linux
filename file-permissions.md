# File Permission Commands

This guide provides detailed information about essential Linux file permission commands, including viewing, modifying, and managing file permissions and ownership.

| Command | Description |
|---------|-------------|
| [`ls`](#ls) | List directory contents with permissions |
| [`chmod`](#chmod) | Change file mode/permissions |
| [`chown`](#chown) | Change file owner and group |
| [`chgrp`](#chgrp) | Change group ownership |
| [`umask`](#umask) | Set default permissions mask |


### ls
List directory contents with permissions
```zsh
~ ls -l                      # List files with permissions
~ ls -la                     # Include hidden files
~ ls -ld directory          # Show directory permissions
```

### chmod
Change file mode/permissions
```zsh
~ chmod 755 file            # Set rwx for owner, rx for group/others
~ chmod u+x file            # Add execute permission for owner
~ chmod g-w file            # Remove write permission for group
~ chmod o=r file            # Set read-only for others
~ chmod -R 644 directory    # Recursively set permissions
```

### chown
Change file owner and group
```zsh
~ sudo chown user file              # Change file owner
~ sudo chown user:group file        # Change owner and group
~ sudo chown -R user directory      # Recursively change owner
~ sudo chown :group file            # Change only group
```

### chgrp
Change group ownership
```zsh
~ sudo chgrp group file            # Change file group
~ sudo chgrp -R group directory    # Recursively change group
~ chgrp --reference=file1 file2    # Use same group as file1
```

### umask
Set default permissions mask
```zsh
~ umask                     # Display current umask
~ umask 022                # Set umask (files: 644, dirs: 755)
~ umask -S                 # Show umask in symbolic notation
~ umask u=rwx,g=rx,o=rx    # Set using symbolic notation
``` 