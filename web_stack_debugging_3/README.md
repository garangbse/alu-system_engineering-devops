# WordPress 500 Error Fix - Puppet Module

## Overview
This Puppet module fixes a common WordPress 500 Internal Server Error caused by a typo in the `wp-settings.php` file.

## Problem Description
The WordPress site returns a 5xx server error due to a mistyped file extension `.phpp` instead of `.php` in the `/var/www/html/wp-settings.php` file.

## Solution
This Puppet code uses an `exec` resource to automatically correct the typo by:
- Using `sed` command to find and replace all instances of `phpp` with `php`
- Targeting the specific file `/var/www/html/wp-settings.php`
- Restoring the site to return 200 OK status

## Usage
Apply this Puppet manifest to automatically fix the WordPress configuration file and restore normal site functionality.

## Requirements
- Puppet agent installed on the target system
- Write permissions to `/var/www/html/wp-settings.php`
- `sed` utility available in system PATH