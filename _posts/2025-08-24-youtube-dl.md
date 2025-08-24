---
title: How to download from youtube via python(yt_dlp)
tags:
  - youtbue
  - yt_dlp
  - python
excerpt: Download Video/Playlist/Music from Youtube in best quality with embedded subtitles via python(yt_dlp)
---

If you are interested, you can find the latest update in [utdl repository](https://github.com/meysamasgari/utdl)

Here is a summary of the main functionality.

## Description

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/images/yt-dlp-diagram.jpg" alt="" width="100%">
    <figcaption>Download from Youtube via yt_dlp)</figcaption>
</figure>

# MAC OS
## Installation
```
1. check python (https://www.python.org/downloads/)
python3 --version 

2. install yt_dlp
sudo curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp
sudo chmod a+rx /usr/local/bin/yt-dlp

3. download ffmpeg binary file (https://www.ffmpeg.org/download.html)
note: no install needed. just it's binary is enough. give the binary path in command
```

## Example 1 (Dowload video/playlist with subtitle using cookies)
```terminal
yt-dlp "https://www.youtube.com/watch?v=9w8QYW5Wsh0"\
    --cookies-from-browser chrome\
    --no-check-certificates\
    --ffmpeg-location "/Users/meysam/Documents/Develop/utdl/ffmpeg"\
    --no-keep-fragments\
    --write-subs --embed-subs\
    -o "/Users/meysam/Downloads/%(title)s_%(ext)s.mp4"\
    -f 'bv*[ext=mp4][height>720]+ba' 
```

## Example 2 (Dowload a section of video)
```terminal
yt-dlp "https://www.youtube.com/watch?v=MNw9x53Ybos"\
    --cookies-from-browser chrome\
    --no-check-certificates\
    --ffmpeg-location "/Users/meysam/Documents/binary"\
    --no-keep-fragments\
    --write-subs --embed-subs\
    -o "/Users/meysam/Downloads/youtube/%(title)s_%(ext)s.mp4"\
    --download-sections "*2:00-3:00" --force-keyframes-at-cuts\
    -f 'bv*[ext=mp4][height>480]+ba'
```

## Example 3 (Dowload music)
```terminal
yt-dlp "https://www.youtube.com/watch?v=f2AnmLp3wvo"\
    --cookies-from-browser chrome\
    --no-keep-fragments\
    -o "/Users/meysam/Downloads/youtube/%(title)s_%(ext)s.mp3"\
    -f 'ba'
```
# WINDOWS OS
## Installation
```
1. check python (https://www.python.org/downloads/)
python3 --version 

2. download and install yt-dlp.exe (https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp.exe)
note: it is not executable. You can use it as coomand

3. download and install ffmpeg.exe file (https://www.ffmpeg.org/download.html)
note: install is needed
```

## Example 1 (Dowload video/playlist with subtitle using cookies)
```cmd
.\yt-dlp.exe "https://www.youtube.com/watch?v=MNw9x53Ybos" `
    --cookies \\Mac\Home\Downloads\www.youtube.com_cookies.txt `
    --no-check-certificates `
    --no-keep-fragments `
    --write-subs --embed-subs `
    -o "\\Mac\Home\Downloads\%(title)s_%(ext)s.mp4" `
    -f 'bv*[ext=mp4][height>480]+ba'
```
## Example 2 (Dowload a section of video)
```cmd
.\yt-dlp.exe "https://www.youtube.com/watch?v=MNw9x53Ybos" `
    --cookies \\Mac\Home\Downloads\www.youtube.com_cookies.txt `
    --no-check-certificates `
    --no-keep-fragments `
    --write-subs --embed-subs `
    -o "\\Mac\Home\Downloads\%(title)s_%(ext)s.mp4" `
    --download-sections "*2:00-3:00" `
	--force-keyframes-at-cuts `
    -f 'bv*[ext=mp4][height>480]+ba'
```
## Example 3 (Dowload music)
```cmd
.\yt-dlp.exe "https://www.youtube.com/watch?v=y-d9WbR0emI" `
    --cookies \\Mac\Home\Downloads\www.youtube.com_cookies.txt `
    --no-keep-fragments `
    -o "\\Mac\Home\Downloads\%(title)s_%(ext)s.mp3" `
    -f 'ba'
```

# note (always update yt_dlp before downloading)
```
1- install or update certifi on your os -> python3 -m pip install certifi
2- update yt-dlp to latest version -> yt-dlp -Uv
```


