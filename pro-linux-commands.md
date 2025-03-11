# Pro Linux Commands

This guide provides detailed information about essential Linux text processing commands, including pattern matching, stream editing, and text manipulation.

| Command | Description |
|---------|-------------|
| [`awk`](#awk) | Pattern scanning and text processing language |
| [`sed`](#sed) | Stream editor for filtering and transforming text |
| [`grep`](#grep) | Search text patterns using regular expressions |

### awk
Pattern scanning and text processing language
```zsh
~ awk '/INFO/' logfile.txt                    # Print lines containing "INFO"
~ awk '{print $1, $2}' logfile.txt           # Print first two fields
~ awk -F':' '/TRACE/ {print $3}' logfile.txt # Print third field of lines with "TRACE"
~ awk '/03\/22 08:51:11/ {count++} END {print count}' logfile.txt  # Count occurrences
```

Example output:
```
03/22 08:51:06 INFO   :.....mailslot_create: creating mailslot for RSVP
03/22 08:51:06 INFO   :....mailbox_register: mailbox allocated for rsvp
03/22 08:51:06 INFO   :.....mailslot_create: creating mailslot for RSVP via UDP
```

### sed
Stream editor for filtering and transforming text
```zsh
~ sed 's/INFO/INFORMATION/g' logfile.txt     # Replace all INFO with INFORMATION
~ sed -n '/TRACE/p' logfile.txt             # Print only lines containing TRACE
~ sed '1,5d' logfile.txt                    # Delete lines 1-5
~ sed '/^$/d' logfile.txt                   # Remove empty lines
```

Example output:
```
03/22 08:51:06 INFORMATION   :.....mailslot_create: creating mailslot for RSVP
03/22 08:51:06 INFORMATION   :....mailbox_register: mailbox allocated for rsvp
03/22 08:51:06 INFORMATION   :.....mailslot_create: creating mailslot for RSVP via UDP
```

### grep
Search text patterns using regular expressions
```zsh
~ grep "INFO" logfile.txt                    # Search for lines containing INFO
~ grep -i "info" logfile.txt                # Case-insensitive search
~ grep -n "TRACE" logfile.txt               # Show line numbers
~ grep -c "mailslot_create" logfile.txt     # Count matching lines
```

Example output:
```
03/22 08:51:06 TRACE  :..entity_initialize: interface 127.0.0.1, entity for rsvp allocated
03/22 08:51:06 TRACE  :......mailslot_create: ready to accept informational socket connection
03/22 08:52:50 TRACE  :......rsvp_event_mapSession: Session=9.67.116.99:1047:6 does not exist
``` 