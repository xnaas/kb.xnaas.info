---
title: AutoHotKey
description: Collection of useful scripts and info related to AHK.
og_title: AutoHotKey
---

<!-- Abbreviations -->
*[AHK]: AutoHotKey

# AutoHotKey

## Resources

* [AHK downloads](https://www.autohotkey.com/download/)
* [AGK forums](https://www.autohotkey.com/boards/)
* [AHK GitHub](https://github.com/Lexikos/AutoHotkey_L/)
* [My Scripts](https://dl.xnaas.info/Software/AutoHotKey/scripts/) (private)
* [Notepad++ & AHK](https://github.com/jNizM/ahk_notepad-plus-plus)

## Scripts & Snippets

### SendMode

It's usually good to add this line to the top of any AHK script, but it's not
always the ideal option. See
[the AHK docs](https://www.autohotkey.com/docs/commands/Send.htm#SendInput)
for more information.

```ahk
SendMode Input
```

### Common Replacements

Here are some common replacements you might be interested in using.
`>!` denotes ++ralt++.

```ahk
>!t::Send ™
>!e::Send é
>!c::Send ¢
>!m::Send µ
>!.::Send •
```

### Version

This will tell you what version of AHK is running.

```ahk
Msgbox % "v" A_AhkVersion " " (A_PtrSize = 4 ? 32 : 64) "-bit " (A_IsUnicode ? "Unicode" : "ANSI")
```

### Always on Top

This allows you to toggle whether a window is always on top of other windows or not.
The keybinding set here is ++lctrl+space++.

```ahk
<^Space:: WinSet, AlwaysOnTop, Toggle, A
```

### Toggle Hidden

This toggles whether hidden items are hidden or not in File Explorer.
The keybinding set here is ++win+h++.

```ahk
; WINDOWS KEY + H TOGGLES HIDDEN FILES 
#h:: 
RegRead, HiddenFiles_Status, HKEY_CURRENT_USER, Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced, Hidden 
If HiddenFiles_Status = 2  
RegWrite, REG_DWORD, HKEY_CURRENT_USER, Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced, Hidden, 1 
Else  
RegWrite, REG_DWORD, HKEY_CURRENT_USER, Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced, Hidden, 2 
WinGetClass, eh_Class,A 
If (eh_Class = "#32770" OR A_OSVersion = "WIN_VISTA") 
send, {F5} 
Else PostMessage, 0x111, 28931,,, A 
Return
```

### Tray Icons

If you have many AHK scripts and don't want them all having the same green H
tray icon, you can add a line like this to set it to something else.

```ahk
Menu, Tray, Icon, shell32.dll, 75
```
