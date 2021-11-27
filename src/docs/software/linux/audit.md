---
title: Auditing
description: Monitor what's happening on your system.
og_title: Linux File Auditing
---

# Auditing

## Resources

* [Find which process is modifying a file @ StackExchange](https://unix.stackexchange.com/a/99091)
* [auditctl manpage](https://man7.org/linux/man-pages/man8/auditctl.8.html)

## Monitor File

If you want to see what the hell is changing a file on your system, like
`/etc/resolv.conf` then do the following for Debian-based distros:

```bash
sudo apt install auditd
sudo auditctl -w /etc/resolv.conf -p wa
```

What we're doing is installing `auditd` and configuring it to monitor for writes
and attribute changes on a specific file.

To test that the monitoring is working, run:

```bash
sudo touch /etc/resolv.conf
sudo ausearch -f /etc/resolv.conf | more
```

It should return a long result like this:

```bash
----
time->Sat Aug  1 08:25:51 2020
type=PROCTITLE msg=audit(1596288351.207:72): proctitle=746F756368002F657463
2F7265736F6C762E636F6E66
type=PATH msg=audit(1596288351.207:72): item=1 name="/etc/resolv.conf" inod
e=914843 dev=08:12 mode=0100644 ouid=0 ogid=0 rdev=00:00 nametype=NORMAL ca
p_fp=0000000000000000 cap_fi=0000000000000000 cap_fe=0 cap_fver=0
type=PATH msg=audit(1596288351.207:72): item=0 name="/etc/" inode=913921 de
v=08:12 mode=040755 ouid=0 ogid=0 rdev=00:00 nametype=PARENT cap_fp=0000000
000000000 cap_fi=0000000000000000 cap_fe=0 cap_fver=0
type=CWD msg=audit(1596288351.207:72): cwd="/root"
type=SYSCALL msg=audit(1596288351.207:72): arch=c000003e syscall=257 succes
s=yes exit=3 a0=ffffff9c a1=7ffe5d513992 a2=941 a3=1b6 items=2 ppid=10519 p
id=14052 auid=1000 uid=0 gid=0 euid=0 suid=0 fsuid=0 egid=0 sgid=0 fsgid=0
tty=pts0 ses=18171 comm="touch" exe="/usr/bin/touch" subj==unconfined key=(
null)
```

Once you've confirmed that the monitoring is working, all you have to do is wait
and check with `sudo ausearch -f /etc/resolv.conf` every now and then until you
finally get a result.

Once you've got the information you need, you can remove the monitoring
with `sudo auditctl -D`. Note: this removes *all* monitors you've configured.
