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
~ voltagex$ brew install voltagex/ffmpeg-with-zvbi/ffmpeg --with-faac --with-libzvbi
==> Installing ffmpeg from voltagex/ffmpeg-with-zvbi
```

This enables proper dvb teletext (subtitles) support.

Probably won't be updated as I'm only borrowing a Mac, but the patch isn't that difficult.

Full credit to the original authors.
