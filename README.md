# ytautogenmeme.bat
### A script that automates the generation of YouTube's "- Topic" like music videos.
## Requirements:
* [Roboto Font (Bold and Regular variant)](https://www.fontsquirrel.com/fonts/roboto)
* [FFMPEG (Linking: Shared)](https://ffmpeg.zeranoe.com/builds/) and for it to be in **"Path"** in the environment variables.

## How to use?
Just run the batch file and enter the asked information. It'll then start to generate the static image and then afterwards the video itself.

## Notes:
The current version of it is not concatenated, which means that it'll take a bit longer to do the processing. I'll fix this in the future (Although pull requests are welcome!).

If you don't have an CUDA supported graphics card or the script somehow fails, you can try to use the libx264 codec instead by changing line 22 from:
```batch
ffmpeg -loop 1 -i final.png -i "%song%" -shortest -vf "scale=1920:1080,setsar=1" -r 1 -c:v h264_nvenc -c:a copy "%songn%.mp4"
```
to:
```batch
ffmpeg -loop 1 -i final.png -i "%song%" -shortest -vf "scale=1920:1080,setsar=1" -r 1 -c:v libx264 -c:a copy "%songn%.mp4"
```

## Videos:
Demo: https://www.youtube.com/watch?v=gSV2oVCdpVQ

Sample Music Video: https://www.youtube.com/watch?v=k5PqN6jW02M
