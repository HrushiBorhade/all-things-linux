# Compression Commands

This guide provides detailed information about essential Linux compression commands, including file archiving, compressing, and decompressing.

| Command | Description |
|---------|-------------|
| [`zip`](#zip) | Package and compress files |
| [`gzip`](#gzip) | Compress files using Lempel-Ziv coding |
| [`gunzip`](#gunzip) | Decompress files compressed with gzip |
| [`tar`](#tar) | Tape archiving utility |
| [`untar`](#untar) | Extract files from tar archive |


### zip
Package and compress files
```zsh
~ zip archive.zip file1 file2     # Create zip archive
~ zip -r archive.zip directory    # Recursively zip directory
~ zip -e archive.zip file         # Create encrypted zip
~ zip -u archive.zip file         # Update existing zip
```

### gzip
Compress files using Lempel-Ziv coding
```zsh
~ gzip file                    # Compress file (creates .gz)
~ gzip -k file                # Keep original file
~ gzip -r directory          # Recursively compress directory
~ gzip -9 file               # Maximum compression
```

### gunzip
Decompress files compressed with gzip
```zsh
~ gunzip file.gz              # Decompress file
~ gunzip -k file.gz          # Keep compressed file
~ gunzip -r directory        # Recursively decompress
~ gunzip -l file.gz          # List compression info
```

### tar
Tape archiving utility
```zsh
~ tar -cvf archive.tar files     # Create tar archive
~ tar -czvf archive.tar.gz files # Create compressed archive
~ tar -cjvf archive.tar.bz2 files # Create bzip2 archive
~ tar -tvf archive.tar           # List contents
```

### untar
Extract files from tar archive
```zsh
~ tar -xvf archive.tar           # Extract tar archive
~ tar -xzvf archive.tar.gz       # Extract gzipped archive
~ tar -xjvf archive.tar.bz2      # Extract bzip2 archive
~ tar -xvf archive.tar -C /path  # Extract to specific directory
``` 