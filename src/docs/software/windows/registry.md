---
title: Registry
description: Hierarchical database that stores low-level settings for the Microsoft Windows operating system and for applications that opt to use it.
og_title: Windows Registry
---

# Registry

## Resources

  * [Registry @ Microsoft Docs](https://docs.microsoft.com/en-us/windows/win32/sysinfo/registry)
  * [Structure of the Registry @ Microsoft Docs](https://docs.microsoft.com/en-us/windows/win32/sysinfo/structure-of-the-registry)

## Scripts & Snippets

### Supress Windows Update Automatic Reboots

!!! success
    This registry edit makes it so that Windows Updates cannot automatically
    reboot your PC under any circumstances.

```registry
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\MusNotification.exe]
"Debugger"="cmd.exe /c echo %DATE% %TIME% suppressed automatic reboot >> C:\\UpdateOrchestrator.log"
```

Source: [Reddit](https://redd.it/aavocr)

### No Web Search in Start Menu

!!! success
    Just as a general note...there were so many wrong answers to this online.
    This is the *only* solution that actually works.

```registry
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer]
"DisableSearchBoxSuggestions"=dword:00000001
```

### Hide Shortcut Arrows

!!! warning
    This info still needs to be properly imported.

Refer to [How to Change, Remove, or Restore Shortcut Arrow Overlay Icon in Windows 10 @ TenForums](https://www.tenforums.com/tutorials/8974-shortcut-arrow-icon-change-remove-restore-windows-10-a.html).

### Fix File Types (VLC)

!!! success
    This fixes VLC making the "Type" column in File Explorer say
    `[EXT] [Audio|Video|Other] File (VLC)` back to `[EXT] File`. This change is
    purely cosmetic.

```registry
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\VLC.3g2]
@="3G2 File"

[HKEY_CLASSES_ROOT\VLC.3ga]
@="3GA File"

[HKEY_CLASSES_ROOT\VLC.3gp]
@="3GP File"

[HKEY_CLASSES_ROOT\VLC.3gp2]
@="3GP2 File"

[HKEY_CLASSES_ROOT\VLC.3gpp]
@="3GPP File"

[HKEY_CLASSES_ROOT\VLC.669]
@="669 File"

[HKEY_CLASSES_ROOT\VLC.a52]
@="A52 File"

[HKEY_CLASSES_ROOT\VLC.aac]
@="AAC File"

[HKEY_CLASSES_ROOT\VLC.ac3]
@="AC3 File"

[HKEY_CLASSES_ROOT\VLC.adt]
@="ADT File"

[HKEY_CLASSES_ROOT\VLC.adts]
@="ADTS File"

[HKEY_CLASSES_ROOT\VLC.aif]
@="AIF File"

[HKEY_CLASSES_ROOT\VLC.aifc]
@="AIFC File"

[HKEY_CLASSES_ROOT\VLC.aiff]
@="AIFF File"

[HKEY_CLASSES_ROOT\VLC.amr]
@="AMR File"

[HKEY_CLASSES_ROOT\VLC.amv]
@="AMV File"

[HKEY_CLASSES_ROOT\VLC.aob]
@="AOB File"

[HKEY_CLASSES_ROOT\VLC.ape]
@="APE File"

[HKEY_CLASSES_ROOT\VLC.asf]
@="ASF File"

[HKEY_CLASSES_ROOT\VLC.asx]
@="ASX File"

[HKEY_CLASSES_ROOT\VLC.au]
@="AU File"

[HKEY_CLASSES_ROOT\VLC.avi]
@="AVI File"

[HKEY_CLASSES_ROOT\VLC.b4s]
@="B4S File"

[HKEY_CLASSES_ROOT\VLC.bik]
@="BIK File"

[HKEY_CLASSES_ROOT\VLC.bin]
@="BIN File"

[HKEY_CLASSES_ROOT\VLC.caf]
@="CAF File"

[HKEY_CLASSES_ROOT\VLC.cda]
@="CDA File"

[HKEY_CLASSES_ROOT\VLC.cue]
@="CUE File"

[HKEY_CLASSES_ROOT\VLC.divx]
@="DIVX File"

[HKEY_CLASSES_ROOT\VLC.drc]
@="DRC File"

[HKEY_CLASSES_ROOT\VLC.dts]
@="DTS File"

[HKEY_CLASSES_ROOT\VLC.dv]
@="DV File"

[HKEY_CLASSES_ROOT\VLC.dvr-ms]
@="DVR-MS File"

[HKEY_CLASSES_ROOT\VLC.evo]
@="EVO File"

[HKEY_CLASSES_ROOT\VLC.f4v]
@="F4V File"

[HKEY_CLASSES_ROOT\VLC.flac]
@="FLAC File"

[HKEY_CLASSES_ROOT\VLC.flv]
@="FLV File"

[HKEY_CLASSES_ROOT\VLC.gvi]
@="GVI File"

[HKEY_CLASSES_ROOT\VLC.gxf]
@="GXF File"

[HKEY_CLASSES_ROOT\VLC.ifo]
@="IFO File"

[HKEY_CLASSES_ROOT\VLC.iso]
@="ISO File"

[HKEY_CLASSES_ROOT\VLC.it]
@="IT File"

[HKEY_CLASSES_ROOT\VLC.m1v]
@="M1V File"

[HKEY_CLASSES_ROOT\VLC.m2t]
@="M2T File"

[HKEY_CLASSES_ROOT\VLC.m2ts]
@="M2TS File"

[HKEY_CLASSES_ROOT\VLC.m2v]
@="M2V File"

[HKEY_CLASSES_ROOT\VLC.m3u]
@="M3U File"

[HKEY_CLASSES_ROOT\VLC.m3u8]
@="M3U8 File"

[HKEY_CLASSES_ROOT\VLC.m4a]
@="M4A File"

[HKEY_CLASSES_ROOT\VLC.m4p]
@="M4P File"

[HKEY_CLASSES_ROOT\VLC.m4v]
@="M4V File"

[HKEY_CLASSES_ROOT\VLC.mid]
@="MID File"

[HKEY_CLASSES_ROOT\VLC.mka]
@="MKA File"

[HKEY_CLASSES_ROOT\VLC.mkv]
@="MKV File"

[HKEY_CLASSES_ROOT\VLC.mlp]
@="MLP File"

[HKEY_CLASSES_ROOT\VLC.mod]
@="MOD File"

[HKEY_CLASSES_ROOT\VLC.mov]
@="MOV File"

[HKEY_CLASSES_ROOT\VLC.mp1]
@="MP1 File"

[HKEY_CLASSES_ROOT\VLC.mp2]
@="MP2 File"

[HKEY_CLASSES_ROOT\VLC.mp2v]
@="MP2V File"

[HKEY_CLASSES_ROOT\VLC.mp3]
@="MP3 File"

[HKEY_CLASSES_ROOT\VLC.mp4]
@="MP4 File"

[HKEY_CLASSES_ROOT\VLC.mp4v]
@="MP4V File"

[HKEY_CLASSES_ROOT\VLC.mpa]
@="MPA File"

[HKEY_CLASSES_ROOT\VLC.mpc]
@="MPC File"

[HKEY_CLASSES_ROOT\VLC.mpe]
@="MPE File"

[HKEY_CLASSES_ROOT\VLC.mpeg]
@="MPEG File"

[HKEY_CLASSES_ROOT\VLC.mpeg1]
@="MPEG1 File"

[HKEY_CLASSES_ROOT\VLC.mpeg2]
@="MPEG2 File"

[HKEY_CLASSES_ROOT\VLC.mpeg4]
@="MPEG4 File"

[HKEY_CLASSES_ROOT\VLC.mpg]
@="MPG File"

[HKEY_CLASSES_ROOT\VLC.mpga]
@="MPGA File"

[HKEY_CLASSES_ROOT\VLC.mpv2]
@="MPV2 File"

[HKEY_CLASSES_ROOT\VLC.mts]
@="MTS File"

[HKEY_CLASSES_ROOT\VLC.mtv]
@="MTV File"

[HKEY_CLASSES_ROOT\VLC.mxf]
@="MXF File"

[HKEY_CLASSES_ROOT\VLC.nsv]
@="NSV File"

[HKEY_CLASSES_ROOT\VLC.nuv]
@="NUV File"

[HKEY_CLASSES_ROOT\VLC.oga]
@="OGA File"

[HKEY_CLASSES_ROOT\VLC.ogg]
@="OGG File"

[HKEY_CLASSES_ROOT\VLC.ogm]
@="OGM File"

[HKEY_CLASSES_ROOT\VLC.ogv]
@="OGV File"

[HKEY_CLASSES_ROOT\VLC.ogx]
@="OGX File"

[HKEY_CLASSES_ROOT\VLC.oma]
@="OMA File"

[HKEY_CLASSES_ROOT\VLC.opus]
@="OPUS File"

[HKEY_CLASSES_ROOT\VLC.pls]
@="PLS File"

[HKEY_CLASSES_ROOT\VLC.qcp]
@="QCP File"

[HKEY_CLASSES_ROOT\VLC.ra]
@="RA File"

[HKEY_CLASSES_ROOT\VLC.ram]
@="RAM File"

[HKEY_CLASSES_ROOT\VLC.rar]
@="RAR File"

[HKEY_CLASSES_ROOT\VLC.rec]
@="REC File"

[HKEY_CLASSES_ROOT\VLC.rm]
@="RM File"

[HKEY_CLASSES_ROOT\VLC.rmi]
@="RMI File"

[HKEY_CLASSES_ROOT\VLC.rmvb]
@="RMVB File"

[HKEY_CLASSES_ROOT\VLC.rpl]
@="RPL File"

[HKEY_CLASSES_ROOT\VLC.s3m]
@="S3M File"

[HKEY_CLASSES_ROOT\VLC.sdp]
@="SDP File"

[HKEY_CLASSES_ROOT\VLC.snd]
@="SND File"

[HKEY_CLASSES_ROOT\VLC.spx]
@="SPX File"

[HKEY_CLASSES_ROOT\VLC.thp]
@="THP File"

[HKEY_CLASSES_ROOT\VLC.tod]
@="TOD File"

[HKEY_CLASSES_ROOT\VLC.tp]
@="TP File"

[HKEY_CLASSES_ROOT\VLC.ts]
@="TS File"

[HKEY_CLASSES_ROOT\VLC.tta]
@="TTA File"

[HKEY_CLASSES_ROOT\VLC.tts]
@="TTS File"

[HKEY_CLASSES_ROOT\VLC.vlc]
@="VLC File"

[HKEY_CLASSES_ROOT\VLC.vob]
@="VOB File"

[HKEY_CLASSES_ROOT\VLC.voc]
@="VOC File"

[HKEY_CLASSES_ROOT\VLC.vqf]
@="VQF File"

[HKEY_CLASSES_ROOT\VLC.vro]
@="VRO File"

[HKEY_CLASSES_ROOT\VLC.w64]
@="W64 File"

[HKEY_CLASSES_ROOT\VLC.wav]
@="WAV File"

[HKEY_CLASSES_ROOT\VLC.webm]
@="WEBM File"

[HKEY_CLASSES_ROOT\VLC.wma]
@="WMA File"

[HKEY_CLASSES_ROOT\VLC.wmv]
@="WMV File"

[HKEY_CLASSES_ROOT\VLC.wtv]
@="WTV File"

[HKEY_CLASSES_ROOT\VLC.wv]
@="WV File"

[HKEY_CLASSES_ROOT\VLC.wvx]
@="WVX File"

[HKEY_CLASSES_ROOT\VLC.xa]
@="XA File"

[HKEY_CLASSES_ROOT\VLC.xesc]
@="XESC File"

[HKEY_CLASSES_ROOT\VLC.xm]
@="XM File"

[HKEY_CLASSES_ROOT\VLC.xspf]
@="XSPF File"

[HKEY_CLASSES_ROOT\VLC.zip]
@="ZIP File"
```
