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

### Anime4k Upscale ([Shaders](https://github.com/mpv-player/mpv/files/11138365/shaders.zip))
For CPU encoding:
```
ffmpeg -y -vsync 0 -i "input.mp4" -init_hw_device vulkan -vf format=yuv420p10,hwupload,libplacebo=w=3840:h=2160:upscaler=ewa_lanczos:custom_shader_path=shaders/Anime4K_ModeA.glsl,hwdownload,format=yuv420p10 "output.mp4"
```
For nvenc encoding:
```
ffmpeg -y -vsync 0 -i "input.mp4" -init_hw_device vulkan -vf format=yuv420p10,hwupload,libplacebo=w=3840:h=2160:upscaler=ewa_lanczos:custom_shader_path=shaders/Anime4K_ModeA.glsl,hwdownload,format=yuv420p10 -c:v hevc_nvenc -cq 24 -bf 5 -refs 5 -preset p7 "output.mp4"
```
