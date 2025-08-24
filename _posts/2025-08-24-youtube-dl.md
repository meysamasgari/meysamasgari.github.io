---
title: Youtube downloader via yt_dlp
tags:
  - youtbue
  - yt_dlp
  - python
excerpt: Download Video/Playlist/Music from Youtube in best quality with embedded subtitles via python(yt_dlp)
---

If you are interested, you can find the latest update in [utdl](https://github.com/meysamasgari/utdl)

Here is a summary of the main functionality.

## Description

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


