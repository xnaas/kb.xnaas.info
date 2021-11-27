---
title: FFmpeg
description: A complete, cross-platform solution to record, convert and stream audio and video.
og_title: FFmpeg
---

# FFmpeg

## Resources

**Compilation**

  * [Compile FFmpeg with non-free software](https://git.io/JMOFQ) (Linux)

**Reading**

  * [FFmpeg documentation](https://ffmpeg.org/ffmpeg.html)
  * [H.264 encoding guide](https://trac.ffmpeg.org/wiki/Encode/H.264)
  * [H.265/HEVC encoding guide](https://trac.ffmpeg.org/wiki/Encode/H.265)
  * [AAC encoding guide](https://trac.ffmpeg.org/wiki/Encode/AAC)

**Help**

  * [FFmpeg forums](https://ffmpeg.zeranoe.com/forum)
  * [/r/ffmpeg](https://www.reddit.com/r/ffmpeg)

## Scripts & Snippets

### Scripts

#### Map + Metadata Fix

```bash
for f in *.mkv; do ffmpeg -i "$f" -metadata title="" -map 0:t -map 0:0 -map 0:1 -map 0:2 \
-metadata:s:v title="" -metadata:s:a title="" -metadata:s:s title="" \
-metadata:s:v language=eng -metadata:s:a language=eng -metadata:s:s language=eng \
-c copy "fixed/${f%.mkv}.mkv"; done
```

#### re-encode

```bash
for f in *.mkv; do ffmpeg -i "$f" -metadata title="" \
-preset:v high -level 4.1 -crf 24 -preset slow -tune thing-here \
-c:a libfdk_aac -b:a 256k -c:s copy "encoded/${f%.mkv}.mkv"; done
```

#### remux

```bash
for f in *.mp4; do ffmpeg -i "$f" -i "${f%.mp4}.srt" \
-metadata title="" -metadata:s:v:0 language=eng -metadata:s:s:0 language=eng \
-c:v copy -c:a libfdk_aac -b:a 128k -c:s copy "muxed/${f%.mp4}.mkv"; done
```

#### unpack b-frames

```bash
for f in *.avi; do ffmpeg -i "$f" -codec copy -bsf:v mpeg4_unpack_bframes "unpacked/${f%.avi}.avi"; done
```

#### Hardware Encoding

```bash
for f in *.mkv;do ffmpeg -hwaccel vaapi -hwaccel_device /dev/dri/renderD128 \
-hwaccel_output_format vaapi -i "$f" -vf 'scale_vaapi=format=nv12' \
-c:v hevc_vaapi -rc_mode CQP -global_quality 25 -profile:v main -c:a copy \
-c:s copy "hevc/${f%.mkv}.mkv";done
```

### Snippets

#### Common Video Encoding Preset

```
-preset:v high -level 4.1 -crf 24 -preset slow -tune thing-here
```

This snippet is good for transcoding a video into [H.264](https://w.wiki/3vgV)
with pretty decent device compatibility. You can adjust the crf number down
to `18` for a closer-to-lossless output at the cost of filesize. If `24` is
too low quality for what you're transcoding, `20` or `22` is usually decent.

!!! info "tune"
    You can add a [tune](https://trac.ffmpeg.org/wiki/Encode/H.264#Tune)
    with `-tune [type]` to further customize the output.

#### Common Audio Encoding Preset

```
-c:a libfdk_aac -b:a 256k
```

Adjust `256k` for the number of audio channels you have.

[libfdk_aac](http://wiki.hydrogenaud.io/index.php?title=Fraunhofer_FDK_AAC) is
regarded as one of the best audio options available in FFmpeg to output to.
libfdk_aac is not part of FFmpeg by default and requires FFmpeg to be
[compiled a specific way](https://git.io/JMOFQ) to include non-free software.
Compatibility with [AAC](https://w.wiki/4TTv) is fantastic and you can get very
good sound quality at lower bitrates than options like [MP3](https://w.wiki/3mCX).

!!! info "bitrate/channels"
    As a rule of thumb, for audible transparency, use 64 kBit/s for each channel
    (e.g. 128 kBit/s for stereo, 384 kBit/s for 5.1 surround sound).

#### Map Attachments

```
-map 0:t
```

This snippet makes sure that all already embedded attachments in a file are copied
over. FFmpeg does **not** do this by default.

#### Change default track

```
-disposition:[s|a|v]:0 default
```

This snippet helps you map a specific subtitle, audio, or video channel as the default.

!!! note
    Change `0` to the actual track number for that type.
