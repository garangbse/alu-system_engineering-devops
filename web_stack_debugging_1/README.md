# Nginx Default Site Configuration Script

This bash script manages the Nginx default site configuration by performing three key operations:

## What the script does:

```bash
#!/bin/bash
rm /etc/nginx/sites-enabled/default
ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/default
service nginx restart
```

### Step-by-step breakdown:

1. **`rm /etc/nginx/sites-enabled/default`**
   - Removes the existing default site symlink from the `sites-enabled` directory
   - This effectively disables the current default site configuration

2. **`ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/default`**
   - Creates a new symbolic link from `sites-available/default` to `sites-enabled/default`
   - This re-enables the default site configuration
   - The `-s` flag creates a symbolic (soft) link rather than a hard link

3. **`service nginx restart`**
   - Restarts the Nginx web server to apply the configuration changes
   - This ensures the new/updated configuration takes effect

## Purpose

This script is typically used to:
- Refresh the default Nginx site configuration
- Re-establish the symbolic link if it was corrupted or misconfigured
- Apply changes made to the default site configuration file

## Requirements

- Root/sudo privileges (required for modifying Nginx configuration and restarting services)
- Nginx installed and configured on the system
