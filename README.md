nix-time
========

Time Machine-type incremental backup system for Linux and similar. Uses hardlinks to save space.

(c) David Bourget 2013

LICENSE

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

See http://www.gnu.org/licenses/ for full license details.

SYSTEM REQUIREMENTS

Developed and tested on Ubuntu. Should work on any Linux-like system.

USAGE

Setup and backup process:

1. Copy included nix-time.conf to /etc/
2. Configure the desired backup directory (hereafter $DIR) and time points in /etc/nix-time.conf
3. Copy binary bin/nix-time where desired (hereafter $NIXTIME)
4. Run 'sudo $NIXTIME init' to create directory structure and set permissions
5. Add daily run of $NIXTIME to cron for root user
We run as root so that we can make the snapshots non-writable by other users for security.
6. Add whatever files you want to backup to $DIR (normally, on a daily basis)  

Recovery:

$DIR/snapshots contains numbered directories corresponding to the time points configured. 

