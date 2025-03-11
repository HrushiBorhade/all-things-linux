# Process Management Commands

This guide provides detailed information about essential Linux process management commands, including process monitoring, control, and system resource usage.

| Command | Description |
|---------|-------------|
| [`ps`](#ps) | Report process status |
| [`top`](#top) | Display and update sorted process information |
| [`fuser`](#fuser) | Identify processes using files or sockets |
| [`kill`](#kill) | Terminate processes |
| [`nohup`](#nohup) | Run a command immune to hangups |
| [`free`](#free) | Display amount of free and used memory |
| [`vmstat`](#vmstat) | Report virtual memory statistics |

### ps
Report process status
```zsh
~ ps                     # Show current shell processes
~ ps aux                # Show all processes in BSD format
~ ps -ef                # Show all processes in full format
~ ps -u username        # Show user's processes
~ ps -p pid             # Show process with specific PID
```

Example output:
```
  PID TTY          TIME CMD
 1234 pts/0    00:00:00 bash
 5678 pts/0    00:00:00 ps
```

### top
Display and update sorted process information
```zsh
~ top                   # Show real-time process information
~ top -u username      # Show specific user's processes
~ top -p pid          # Monitor specific process
~ top -b              # Batch mode output
```

Example output:
```
top - 14:28:48 up  6:30,  2 users,  load average: 0.52, 0.58, 0.59
Tasks: 213 total,   1 running, 212 sleeping,   0 stopped,   0 zombie
%Cpu(s):  5.9 us,  2.0 sy,  0.0 ni, 91.7 id,  0.3 wa,  0.0 hi,  0.1 si
MiB Mem :  15951.3 total,   9635.5 free,   3521.4 used,   2794.4 buff/cache
```

### fuser
Identify processes using files or sockets
```zsh
~ fuser filename        # Show processes using file
~ fuser -v filename    # Verbose output
~ fuser -k filename    # Kill processes using file
~ fuser -n tcp port    # Show processes using TCP port
```

Example output:
```
/dev/sda1:            1234  5678  (root)  (user)
```

### kill
Terminate processes
```zsh
~ kill pid              # Terminate process gracefully
~ kill -9 pid          # Force terminate process
~ kill -l              # List available signals
~ killall processname  # Kill all processes by name
```

Example output:
```
~ kill -l
 1) SIGHUP   2) SIGINT   3) SIGQUIT  4) SIGILL   5) SIGTRAP
 6) SIGABRT  7) SIGBUS   8) SIGFPE   9) SIGKILL 10) SIGUSR1
```

### nohup
Run a command immune to hangups
```zsh
~ nohup command &       # Run command in background
~ nohup command > log.txt 2>&1 & # Run with output redirection
~ nohup ./script.sh &   # Run script in background
```

Example output:
```
nohup: ignoring input and appending output to 'nohup.out'
[1] 1234
```

### free
Display amount of free and used memory
```zsh
~ free                  # Show memory usage
~ free -h              # Human readable format
~ free -s 5            # Update every 5 seconds
~ free -t              # Show total line
```

Example output:
```
              total        used        free      shared  buff/cache   available
Mem:          15951        3521        9635         524        2794       11905
Swap:          2047           0        2047
```

### vmstat
Report virtual memory statistics
```zsh
~ vmstat                # Show virtual memory stats
~ vmstat 1 5           # Update every 1 second, 5 times
~ vmstat -s            # Show memory statistics
~ vmstat -d            # Show disk statistics
```

Example output:
```
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 9635348 289676 2571912  0    0     0     0    1    2  6  2 92  0  0
``` 