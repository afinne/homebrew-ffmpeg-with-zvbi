# homebrew-ffmpeg-with-zvbi
When you really, really need dvb-teletext support


```bash
~ voltagex$ brew tap voltagex/ffmpeg-with-zvbi
==> Tapping voltagex/ffmpeg-with-zvbi
Cloning into '/usr/local/Library/Taps/voltagex/homebrew-ffmpeg-with-zvbi'...
remote: Counting objects: 7, done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 7 (delta 1), reused 7 (delta 1), pack-reused 0
Unpacking objects: 100% (7/7), done.
Checking connectivity... done.
Tapped 2 formulae (32 files, 136K)
~ voltagex$ brew install voltagex/ffmpeg-with-zvbi/ffmpeg --with-faac --with-zvbi
```

This enables proper dvb teletext (subtitles) support.

Before:
```bash
voltagex$ ffmpeg -txt_format text -i somefile.m2ts -c:a copy -c:v libx264 -crf 0 -c:s srt somefile.mkv
ffmpeg version 2.8.4 Copyright (c) 2000-2015 the FFmpeg developers
  built with Apple LLVM version 7.0.2 (clang-700.1.81)
  configuration: --prefix=/usr/local/Cellar/ffmpeg/2.8.4 --enable-shared --enable-pthreads --enable-gpl --enable-version3 --enable-hardcoded-tables --enable-avresample --cc=clang --host-cflags= --host-ldflags= --enable-opencl --enable-libx264 --enable-libmp3lame --enable-libvo-aacenc --enable-libxvid --enable-libfaac --enable-nonfree --enable-vda
  libavutil      54. 31.100 / 54. 31.100
  libavcodec     56. 60.100 / 56. 60.100
  libavformat    56. 40.101 / 56. 40.101
  libavdevice    56.  4.100 / 56.  4.100
  libavfilter     5. 40.101 /  5. 40.101
  libavresample   2.  1.  0 /  2.  1.  0
  libswscale      3.  1.101 /  3.  1.101
  libswresample   1.  2.101 /  1.  2.101
  libpostproc    53.  3.100 / 53.  3.100
Unrecognized option 'txt_format'.
#or
Error while opening encoder for output stream #0:2 - maybe incorrect parameters such as bit_rate, rate, width or height

```

After:
```bash
...
Stream mapping:
  Stream #0:0 -> #0:0 (mpeg2video (native) -> h264 (libx264))
  Stream #0:1 -> #0:1 (copy)
  Stream #0:2 -> #0:2 (dvb_teletext (libzvbi_teletextdec) -> subrip (srt))
Press [q] to stop, [?] for help
frame= 1224 fps= 51 q=0.0 size=  108829kB time=00:00:49.68 bitrate=17945.4kbits/s 
#Winning!
```

Probably won't be updated as I'm only borrowing a Mac, but the patch isn't that difficult.

Full credit to the original authors.
