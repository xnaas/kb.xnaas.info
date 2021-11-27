---
title: Batch Files
description: Windows scripting.
og_title: Windows Batch Files
---

# Batch Files

## Resources

* ["Windows Commands" @ Microsoft Docs](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
* ["Batch file" @ Wikipedia](https://en.wikipedia.org/wiki/Batch_file)

## Scripts & Snippets

### Clear Credential Manager

#### Script

```batch
cmdkey.exe /list > "%TEMP%\List.txt"
findstr.exe Target "%TEMP%\List.txt" > "%TEMP%\tokensonly.txt"
FOR /F "tokens=1,2 delims= " %%G IN (%TEMP%\tokensonly.txt) DO cmdkey.exe /delete:%%H
del "%TEMP%\List.txt" /s /f /q
del "%TEMP%\tokensonly.txt" /s /f /q
timeout /t 8
```

#### What/Why?

This script will automatically clear Credential Manager for you so you don't have
to go and manually clear potentially dozens or hundreds of saved credentials from
a Windows box.

### Windows 10 Pro → Enterprise

#### Snippet

```batch
cscript.exe c:\windows\system32\slmgr.vbs /ipk NPPR9-FWDCX-D2C8J-H872K-2YT43
```

#### What?

This command will turn any Windows 10 Pro install into a Windows 10 Enterprise install.
^No\ reboot\ required!^

Source: [Windows 10 Edition Upgrade @ Microsoft Docs](https://docs.microsoft.com/en-us/windows/deployment/upgrade/windows-10-edition-upgrades#upgrade-using-a-command-line-tool)

#### Why?

Sometimes you're working in an Enterprise environment and have a machine that just has to be reimaged with normal, Pro edition Windows on it. This command allows you to convert it to Enterprise afterwards, bind it to your domain, and make sure you're getting the proper licensing.
