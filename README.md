# FFmpeg

### Input
```bash
ffmpeg -i 
```
```bash
ffmpeg -hwaccel cuda -i
```

### Options
Trim:
```bash
-ss  -to 
```
Offset:
```bash
-itsoffset
```
Output MP3:
```bash
~/Downloads/theme.mp3
```
Output Subtitles:
```bash
~/Downloads/eng.ass
```
Output Video (no encode):
```bash
-c copy ~/Downloads/output.mp4
```
Output Video (re-encode):
```bash
-async 1 ~/Downloads/output.mp4
```
