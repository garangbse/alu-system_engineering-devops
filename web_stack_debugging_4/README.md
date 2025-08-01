# Web Stack Debugging 4

This repository contains a Puppet script that fixes nginx performance issues by increasing file descriptor limits to handle more concurrent connections.

## How it works

The Puppet script performs three sequential operations:

1. **Increase ULIMIT**: Modifies `/etc/default/nginx` to change the file descriptor limit from 15 to 4096
2. **Set Hard Limit**: Adds nginx-specific soft and hard limits to `/etc/security/limits.conf` 
3. **Restart Service**: Restarts nginx to apply the configuration changes

The script uses the `notify` parameter to ensure operations execute in the correct order, with each step triggering the next one only when changes are made.

## Usage

Run the Puppet script to automatically configure nginx for better performance under high load conditions.