# User Switching Scripts

## 0-iamsomeoneelse

**Purpose**: Switch to another user and display their username using the `whoami` command.

**Usage**:
```bash
./0-iamsomeoneelse <username>
```


## 1-run_nginx_as_nginx

**Description**: 
This script takes a username as an argument and uses the `su` (switch user) command to temporarily switch to that user, then executes `


This script reconfigures Nginx to:

Run as the nginx user instead of www-data

Listen on port 8080 instead of 80

🧱 What it does:
Edits Nginx config files to update the user and port

Stops any running Nginx processes

Starts Nginx as the nginx user

Useful for debugging when avoiding permission or port conflicts inside a container.