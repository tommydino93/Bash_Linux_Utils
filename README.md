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
