---
title: File Association
description: Set default program or file extension association via CLI on Windows.
og_title: File Association
---

# File Association

## assoc

The new Windows GUI for associating cert file extensions (.nfo, .7z, etc.) is a horrible,
awful, useless mess of utter garbage.

Enter: the `assoc` command. This can only be run from Command Prompt, it does not work
in PowerShell. Must run as admin.

If you type just `assoc`, you will get a list of all extensions with an associated
program and what that associated program is.

To set a new association, you do something like this:

```bat
assoc .nfo="C:\Program Files\Notepad++\notepad++.exe"
```
