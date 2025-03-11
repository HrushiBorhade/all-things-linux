# Basic Linux Commands

This guide provides detailed information about essential Linux basic commands, including file operations, directory management, and text manipulation.

| Command | Description |
|---------|-------------|
| [`ls`](#ls) | List directory contents |
| [`cd`](#cd) | Change directory |
| [`pwd`](#pwd) | Print working directory |
| [`mkdir`](#mkdir) | Make directories |
| [`rm`](#rm) | Remove files or directories |
| [`rmdir`](#rmdir) | Remove empty directories |
| [`cat`](#cat) | Concatenate and display files |
| [`zcat`](#zcat) | Display compressed files |
| [`touch`](#touch) | Create empty files or update timestamps |
| [`head`](#head) | Display first lines of files |
| [`tail`](#tail) | Display last lines of files |
| [`less`](#less) | View file contents page by page |
| [`more`](#more) | View file contents one screen at a time |
| [`cp`](#cp) | Copy files and directories |
| [`mv`](#mv) | Move/rename files and directories |
| [`wc`](#wc) | Print word, line, character, and byte counts |
| [`ln`](#ln) | Create hard and soft links |
| [`cut`](#cut) | Remove sections from lines of files |
| [`tee`](#tee) | Read from stdin and write to stdout and files |
| [`sort`](#sort) | Sort lines in text files |
| [`clear`](#clear) | Clear terminal screen |
| [`diff`](#diff) | Compare files line by line |
| [`df`](#df) | Report file system disk space usage |
| [`du`](#du) | Estimate file space usage |

### ls
List directory contents
```zsh
~ ls                     # List files in current directory
~ ls -l                 # Long format listing
~ ls -a                 # Show hidden files
~ ls -lh                # Human readable file sizes
~ ls -R                 # Recursive listing
```

### cd
Change directory
```zsh
~ cd /path/to/dir       # Change to specific directory
~ cd ..                # Go up one directory
~ cd ~                 # Go to home directory
~ cd -                 # Go to previous directory
```

### pwd
Print working directory
```zsh
~ pwd                   # Show current directory path
~ pwd -P               # Show physical path (resolve symlinks)
```

### mkdir
Make directories
```zsh
~ mkdir dir1                    # Create single directory
~ mkdir -p dir1/dir2/dir3      # Create parent directories
~ mkdir -m 755 dir1            # Create with specific permissions
```

### rm
Remove files or directories
```zsh
~ rm file1                # Remove single file
~ rm -r dir1             # Remove directory and contents
~ rm -f file1            # Force remove without confirmation
~ rm -i file1            # Interactive removal
```

### rmdir
Remove empty directories
```zsh
~ rmdir dir1             # Remove empty directory
~ rmdir -p dir1/dir2     # Remove directory and parents
```

### cat
Concatenate and display files
```zsh
~ cat file1              # Display file contents
~ cat file1 file2        # Concatenate multiple files
~ cat -n file1           # Show line numbers
~ cat > file1            # Create new file from input
```

### zcat
Display compressed files
```zsh
~ zcat file.gz           # View compressed file
~ zcat -f file.gz        # Force decompression
```

### touch
Create empty files or update timestamps
```zsh
~ touch file1            # Create empty file/update timestamp
~ touch -a file1         # Update access time only
~ touch -m file1         # Update modification time only
```

### head
Display first lines of files
```zsh
~ head file1             # Show first 10 lines
~ head -n 5 file1        # Show first 5 lines
~ head -c 100 file1      # Show first 100 bytes
```

### tail
Display last lines of files
```zsh
~ tail file1             # Show last 10 lines
~ tail -n 5 file1        # Show last 5 lines
~ tail -f file1          # Follow file updates
```

### less
View file contents page by page
```zsh
~ less file1             # View file content
~ less -N file1          # Show line numbers
~ less -S file1          # Disable line wrapping
```

### more
View file contents one screen at a time
```zsh
~ more file1             # View file content
~ more -d file1          # Show commands
~ more +10 file1         # Start from line 10
```

### cp
Copy files and directories
```zsh
~ cp file1 file2         # Copy file
~ cp -r dir1 dir2        # Copy directory recursively
~ cp -p file1 file2      # Preserve attributes
~ cp -i file1 file2      # Interactive copy
```

### mv
Move/rename files and directories
```zsh
~ mv file1 file2         # Move/rename file
~ mv -i file1 file2      # Interactive move
~ mv dir1 dir2           # Move/rename directory
```

### wc
Print word, line, character, and byte counts
```zsh
~ wc file1               # Show lines, words, bytes
~ wc -l file1            # Count lines only
~ wc -w file1            # Count words only
~ wc -c file1            # Count bytes only
```

### ln
Create hard and soft links
```zsh
~ ln file1 link1         # Create hard link
~ ln -s file1 link1      # Create symbolic link
~ ln -f file1 link1      # Force link creation
```

### cut
Remove sections from lines of files
```zsh
~ cut -d: -f1 file1      # Cut by delimiter
~ cut -c1-5 file1        # Cut by characters
~ cut -b1-5 file1        # Cut by bytes
```

### tee
Read from stdin and write to stdout and files
```zsh
~ echo "test" | tee file1     # Write to file and display
~ echo "test" | tee -a file1  # Append to file
```

### sort
Sort lines in text files
```zsh
~ sort file1             # Sort lines alphabetically
~ sort -n file1          # Sort numerically
~ sort -r file1          # Sort in reverse
~ sort -u file1          # Sort and remove duplicates
```

### clear
Clear terminal screen
```zsh
~ clear                  # Clear screen
~ clear -x               # Don't clear scrollback buffer
```

### diff
Compare files line by line
```zsh
~ diff file1 file2       # Show differences
~ diff -u file1 file2    # Unified format
~ diff -i file1 file2    # Ignore case differences
```

### df
Report file system disk space usage
```zsh
~ df                     # Show disk usage
~ df -h                  # Human readable sizes
~ df -T                  # Show filesystem type
```

### du
Estimate file space usage
```zsh
~ du                     # Show directory sizes
~ du -h                  # Human readable sizes
~ du -s                  # Summary only
~ du -a                  # Show file sizes too
``` 