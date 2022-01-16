# Bash/Linux Utils
This folder contains code snippets for bash/linux/unix

### 1) Print number of directories inside specified path
```bash
>>> cd /path/to/dir
>>> ls | wc -l
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
>>> rsync -vrazh /path/to/src/ /path/to/dst/ --delete --ignore-existing
```
- v: verbose
- r: recursively
- a: archive mode; allows copying files recursively and also preserves symbolic links
- z: compress file data
- h: human-readable, output numbers in a human-readable format
- n: dry-run; performs a trial run with no changes made
