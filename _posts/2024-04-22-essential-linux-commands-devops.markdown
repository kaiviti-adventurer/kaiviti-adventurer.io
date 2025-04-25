---
layout: post
title: "20 Essential Linux Commands Every Junior DevOps Engineer Should Know"
date: 2024-04-22
categories: tech
tags: [linux, devops, commands, terminal, basics]
image: /assets/images/tech/linux-commands.jpeg
---

As you embark on your DevOps journey, mastering Linux commands is crucial for your day-to-day operations. Whether you're managing servers, troubleshooting issues, or automating tasks, these commands will be your constant companions. In this post, I'll share the top 20 Linux commands that every junior DevOps engineer should know, complete with practical examples and real-world applications.

## Why These Commands Matter

In DevOps, you'll frequently work with Linux servers, containers, and automation scripts. Understanding these commands will help you:
- Navigate and manage file systems efficiently
- Monitor system resources and processes
- Manage users and permissions
- Handle network configurations
- Troubleshoot issues effectively

Let's dive into the essential commands!

## File System Navigation and Management

### 1. pwd (Print Working Directory)
Shows your current location in the file system.
```bash
$ pwd
/home/user/projects
```

### 2. ls (List Directory Contents)
Lists files and directories. Essential flags include `-l` (detailed list), `-a` (show hidden files), and `-h` (human-readable sizes).
```bash
# List all files with details
$ ls -lah

# List only directories
$ ls -d */
```

### 3. cd (Change Directory)
Navigate between directories. Master these shortcuts:
```bash
# Go to home directory
$ cd ~

# Go up one level
$ cd ..

# Go to previous directory
$ cd -
```

### 4. mkdir (Make Directory)
Create directories. The `-p` flag creates parent directories if they don't exist.
```bash
# Create a single directory
$ mkdir logs

# Create nested directories
$ mkdir -p projects/app/config
```

## File Operations

### 5. cp (Copy)
Copy files and directories. Use `-r` for recursive copying of directories.
```bash
# Copy a file
$ cp source.txt destination.txt

# Copy a directory and its contents
$ cp -r source_dir destination_dir
```

### 6. mv (Move)
Move or rename files and directories.
```bash
# Move a file
$ mv file.txt /path/to/destination/

# Rename a file
$ mv oldname.txt newname.txt
```

### 7. rm (Remove)
Delete files and directories. Be careful with this command!
```bash
# Remove a file
$ rm file.txt

# Remove a directory and its contents
$ rm -r directory/

# Force remove without confirmation (use with caution!)
$ rm -rf directory/
```

## Text Processing and Viewing

### 8. cat (Concatenate)
View file contents or combine files.
```bash
# View file contents
cat config.yaml
# Combine files
cat file1.txt file2.txt > combined.txt
```

### 9. grep (Global Regular Expression Print)
Search for patterns in files.
```bash
# Search for a word in a file
$ grep "error" log.txt

# Search recursively in all files
$ grep -r "TODO" .

# Case-insensitive search
$ grep -i "warning" log.txt
```

### 10. tail (View End of File)
View the end of files. Crucial for log monitoring.
```bash
# View last 10 lines
tail app.log
# Follow file updates in real-time
tail -f /var/log/syslog
```

## Process Management

### 11. ps (Process Status)
View running processes.
```bash
# Show all processes
$ ps aux

# Show process tree
$ ps -ef
```

### 12. top/htop
Monitor system processes in real-time.
```bash
# Launch top
$ top

# Launch htop (if installed)
$ htop
```

### 13. kill (Terminate Process)
Stop processes using their PID.
```bash
# Terminate process gracefully
kill <PID>
# Force terminate
kill -9 <PID>
```

## System Information

### 14. df (Disk Free)
Check disk space usage.
```bash
# Show disk space in human-readable format
$ df -h

# Show file system type
$ df -T
```

### 15. du (Disk Usage)
Check directory size.
```bash
# Show directory size in human-readable format
$ du -h directory/

# Show total size only
$ du -sh directory/
```

## Network Operations

### 16. netstat
Network statistics and connections.
```bash
# Show all listening ports
$ netstat -tulpn

# Show all active connections
$ netstat -an
```

### 17. curl
Transfer data from or to a server.
```bash
# Download a file
$ curl -O https://example.com/file.txt

# Send a GET request
$ curl https://api.example.com

# Send a POST request
$ curl -X POST -d "data" https://api.example.com
```

## File Permissions

### 18. chmod (Change Mode)
Modify file permissions.
```bash
# Make a file executable
$ chmod +x script.sh

# Set specific permissions
$ chmod 755 file.txt
```

### 19. chown (Change Owner)
Change file ownership.
```bash
# Change owner
$ sudo chown user:group file.txt

# Change recursively
$ sudo chown -R user:group directory/
```

## Package Management

### 20. apt/apt-get (Package Manager)
Manage software packages (Ubuntu/Debian).
```bash
# Update package list
sudo apt update
# Install package
sudo apt install docker.io
# Remove package
sudo apt remove package_name
```

## Summary and Best Practices

Remember these key points:
- Always use `--help` or `man` command to learn more about command options
- Be extremely careful with `rm` and `chmod` commands
- When in doubt, make backups before major operations
- Use tab completion to avoid typing errors
- Create aliases for frequently used commands

## Looking Forward

This post covered the essential Linux commands for DevOps beginners. In our next post, we'll dive into Bash scripting, where we'll learn how to combine these commands to create powerful automation scripts. We'll cover:
- Writing your first Bash script
- Variables and control structures
- Error handling
- Best practices for DevOps automation

Stay tuned for more DevOps tutorials and tips!

## Additional Resources

To help you further master Linux commands, here are some excellent video tutorials:

### 1. Linux Command Line Basics
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/IVquJh3DXUA" title="Linux Command Line Basics" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### 2. Advanced Linux Commands for DevOps
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZtqBQ68cfJc" title="Advanced Linux Commands for DevOps" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### 3. Linux File System and Permissions
<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/HIXzJ3Rz9po" title="Linux File System and Permissions" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

<style>
.video-container {
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
    max-width: 100%;
    margin: 20px 0;
}

.video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>

---

## Share Your Thoughts!

If you found this guide helpful, please show your support by clicking the reaction buttons below (👍, ❤️, or 🎉). Your feedback helps me create better content!

Have questions about these commands? Want to share your own tips? Drop a comment below! I'd love to hear about your experiences with Linux commands and how you're using them in your DevOps journey.

Don't forget to bookmark this page for future reference. Stay tuned for our next blog post where we'll dive into Bash scripting for automation! 