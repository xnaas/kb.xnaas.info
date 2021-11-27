---
title: PowerShell
description: PowerShell is a task-based command-line shell and scripting language. PowerShell helps system administrators and power-users rapidly automate tasks that manage operating systems (Linux, macOS, and Windows) and processes.
og_title: PowerShell
---

# PowerShell

??? info "What is PowerShell?"
    PowerShell is a task-based command-line shell and scripting language built
    on .NET. PowerShell helps system administrators and power-users rapidly
    automate tasks that manage operating systems (Linux, macOS, and Windows) and processes.
    
    PowerShell commands let you manage computers from the command line. PowerShell
    providers let you access data stores, such as the registry and certificate store,
    as easily as you access the file system. PowerShell includes a rich expression parser
    and a fully developed scripting language.

## Resources

* [PowerShell @ Microsoft Docs](https://docs.microsoft.com/en-us/powershell)
* [PowerShell @ Wikipedia](https://en.wikipedia.org/wiki/PowerShell)

## Scripts & Snippets

### Disable Beep

#### Code

```ps1
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
if (!(Test-Path -Path "$Profile")) {New-Item -ItemType File -Path "$Profile" -Force}
Add-Content -Value "Set-PSReadlineOption -BellStyle None" -Path "$Profile"
```

#### What?

This series of commands will:

1. Set your execution policy so that you can have a `$profile`
2. Create a profile located at `C:\Users\<username>\Documents\WindowsPowerShell`
    called `Microsoft.PowerShell_profile.ps1`
3. The file contents will be `Set-PSReadlineOption -BellStyle None`

!!! note
    If you already have a `$profile`, you'll want to simply add
    `Set-PSReadlineOption -BellStyle None` to it.

### Disable Startup Message

#### Code

Add `Clear-Host` to your `$profile`. For more information on `$profile`,
see the above section about disabling beep.

#### What?

This removes that obnoxious startup message text:

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6
```

### Windows 10 Pro → Enterprise

#### Code

```bat
cscript.exe c:\windows\system32\slmgr.vbs /ipk NPPR9-FWDCX-D2C8J-H872K-2YT43
```

#### What?

This command, which is technically a
[Windows Command](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
and not PowerShell, will turn any Windows 10 Pro install into a Windows 10 Enterprise
install. ^No\ reboot\ required!^

Source: [Windows 10 Edition Upgrade @ Microsoft Docs](https://docs.microsoft.com/en-us/windows/deployment/upgrade/windows-10-edition-upgrades#upgrade-using-a-command-line-tool)

#### Why?

Sometimes you're working in an Enterprise environment and have a machine that just has
to be reimaged with normal, Pro edition Windows on it. This command allows you to convert
it to Enterprise afterwards, bind it to your domain, and make sure you're getting the proper
licensing.
