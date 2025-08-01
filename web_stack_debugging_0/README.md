# Apache Hello Holberton Script

This bash script configures and runs an Apache web server to serve a simple "Hello Holberton" webpage.

## What This Script Does

The script performs the following operations:

1. **Starts Apache Service**: Initializes the Apache2 web server
2. **Creates Web Content**: Generates a simple HTML page with "Hello Holberton" message
3. **Runs Apache in Foreground**: Keeps the Apache server running continuously (ideal for containerized environments)

## Script Breakdown

```bash
#!/usr/bin/env bash
# Shebang line - tells the system to execute this script using bash

service apache2 start
# Starts the Apache2 web server service

echo "Hello Holberton" > /var/www/html/index.html
# Creates an index.html file in Apache's default document root
# The > operator overwrites any existing content

apache2ctl -D FOREGROUND
# Runs Apache in foreground mode, preventing the process from daemonizing
# This keeps the container/script running continuously
```

## Prerequisites

- Apache2 installed on the system
- Sufficient permissions to:
  - Start system services
  - Write to `/var/www/html/` directory
  - Run Apache control commands

## Usage

Make the script executable and run it:

```bash
chmod +x your-script-name.sh
sudo ./your-script-name.sh
```

## Expected Result

After running the script, you can access `http://localhost` (or your server's IP) and see the message "Hello Holberton" displayed in your web browser.

## Container Usage

This script is particularly useful in Docker containers where you need Apache to run in the foreground to keep the container alive. The `FOREGROUND` directive prevents Apache from running as a background daemon, which would cause the container to exit immediately.

## Notes

- The script requires root/sudo privileges to start Apache and write to system directories
- Any existing `/var/www/html/index.html` file will be overwritten
- The server will continue running until manually stopped (Ctrl+C) or the container is terminated