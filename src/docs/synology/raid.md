---
title: RAID Resync
description: Information about building, rebuilding, or resyncing your Synology RAID arrays.
og_title: Synology RAID Resync
---

<!-- Abbreviations -->
*[NAS]: Network-attached storage
*[NCQ]: Native Command Queuing
*[RAID]: Redundant Array of Independent/Inexpensive Disks
*[SSH]: Secure Shell

# RAID Resync

## Resources

* [Blog Post](https://eve.gd/2020/01/03/accelerating-synology-raid-6-reshapes/)
* [General Info](https://www.cyberciti.biz/tips/linux-raid-increase-resync-rebuild-speed.html)

## Improve Speed

If you make these changes, your RAID resync/build times will improve *substatially*.

!!! warning
    Your NAS will be incredibly slow and nearly unresponsive after these changes.

### GUI

1. Open **Storage Manager**
2. Go to **Storage Pool**
3. Go to **Configurations**
4. Select **Customize**
5. Set **Min** to something high like `300` or `600`
6. Set **Max** to something ridiculous like `1500` (it'll likely never go that fast)

-----

### Command Line

!!! note
    You may have a different number instead of `md2` for your main array.
    Use `cat /proc/mdstat` to find out your array number.

1. SSH into your NAS
2. Elevate to root with `sudo -i` if you don't want to type `sudo` before every command
3. Run `echo 32768 > /sys/block/md2/md/stripe_cache_size` if you have a lot of RAM. If you have the default amount of RAM, this might not work well. You can use any power of 2 though, such as `16384` or `8192`. I don't recall what the default is, but I think it's only `4096`.
4. Run `blockdev --setra 65536 /dev/md2`
5. **Optional**: Run `echo max > /sys/block/md2/md/sync_max` (in my case this was already set to `max` and not needed, however)

You can also [play with disabling NCQ](https://www.cyberciti.biz/tips/linux-raid-increase-resync-rebuild-speed.html) during the rebuild, but I found it helped basically none so returned that to default.