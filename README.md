# Bash/Linux Utils
This folder contains code snippets for bash/linux/unix

### 1) Print number of directories inside specified path
```bash
>>> cd /path/to/dir
>>> ls | wc -l  # not recursively
>>> ls -lR | grep "^d" | wc -l  # recursively (i.e. include subdirs)
```

### 2) Print top X folders in terms of disk space usage (e.g. top 5)
```bash
>>> du -a /path/to/dir/ | sort -n -r | head -n 5
```

### 3) Check ubuntu version
```bash
>>> lsb_release -a
```

### 4) Copy/Synchronize directories with rsync
```bash
# dry-run trial mode (i.e. no changes are made)
>>> rsync -vrazhn /path/to/src/ /path/to/dst/ --delete --ignore-existing

# real command (i.e. actual modifications are made)
>>> rsync -vrazh /path/to/src/ /path/to/dst/ --delete --ignore-existing  --progress
```
- v: verbose
- r: recursively
- a: archive mode; allows copying files recursively and also preserves symbolic links
- z: compress file data
- h: human-readable, output numbers in a human-readable format
- n: dry-run; performs a trial run with no changes made
- delete: delete extraneous files from destination dirs
- ignore-existing: skip updating files that already exist on destination dirs
- progress: show data transfer progress

### 5) Check disk space taken by one directory
```bash
>>> du -hs /path/to/dir
```

### 6) Install an SSH key on a server as an authorized key
```bash
# generate key (in case you don't have one)
>>> ssh-keygen
# copy ssh key to server; its purpose is to provide access without requiring a password for each login
>>> ssh-copy-id user@server
```

### 7) Check number of CPUs available
```bash
>>> lscpu
```
“CPU(s): XX” represents the number of logical cores, which equals “Thread(s) per core” × “Core(s) per socket” × “Socket(s)”. One socket is one physical CPU package (which occupies one socket on the motherboard); each socket hosts a number of physical cores, and each core can run one or more threads

### 8) Install .deb file
```bash
>>> sudo dpkg -i package_file.deb
```
