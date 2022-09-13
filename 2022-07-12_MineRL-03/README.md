### Episode 3 (2022-07-12) : OpenAI VPT for Android Demos &rarr; [YouTube Video](https://youtu.be/S9sAd3DqToE)

* This episode's Colab Notebook : [DiamondJAX_03-VPT-for-AndroidDemos](https://colab.research.google.com/drive/1tUR0Y7fpxF3O_bLfiks6imSzNXJ_BRvK?usp=sharing)
* Includes (_extending the previous Colab_):
    + Calibration of VPT camera moves
      - Seen in previous text output of VPT camera changes: 
        - `0.00, ±0.62, ±1.61, ±3.22, ±5.81, ±10.00` degrees
        - (zero, positive + negative versions &rArr; 11 steps)
      - After calibration step (using Intro Colab+GIMP): 
        - `0.0, ±4.5, ±10.5, ±21.5, ±38.5, ±66.5` pixels
    + `ffmpeg` overlay for `VPT` output actions


#### Notes

* Android phone screen recording : [Good Blog post](https://www.fosslinux.com/46780/cast-video-android-linux.htm)
  + STEP1 : Set up Android USB connection :
```bash
dnf install android-tools
```

* STEP2 : On phone:
    + `Settings - About Phone - Lenovo version : Tap 7 times` (to become developer)
    + `Settings - Advanced Options - Developer Options (new entry!) - USB debugging : Enable`

* STEP3 : With computer:
    * Reconnect USB cable
    * Rerun `adb devices` to see the phone connected
    * May have to turn on/off USB debugging, switch to Transfer files...
        * Until 'Authorized this machine' dialog appears (say Yes) 
    * Make sure `adb devices` is stable : 
        * Potentially change USB port on desktop machine (!) ...

* STEP4 : Install [the scrcpy tool](https://github.com/Genymobile/scrcpy/blob/master/FAQ.md):
    * Android device needs to be at least API 21 (Android 5.0)
    * For Fedora, a [COPR](https://fedoraproject.org/wiki/Category:Copr) package is available: [`scrcpy`](https://copr.fedorainfracloud.org/coprs/zeno/scrcpy/)
    * Download [the repo config file](https://copr.fedorainfracloud.org/coprs/zeno/scrcpy/)
        * ... to `/etc/yum.repos.d/zeno-scrcpy-fedora-34.repo`
    * `dnf install scrcpy` as root user

* STEP5 : Use the `scrcpy` tool
    * Some sample commands first
    * Then the custom-to-your-phone crop/scaling commands
      + What works for me is below : YMMV!

```bash
# And as USER (some sample commands):
scrcpy --max-size 720 --max-fps 20
scrcpy --print-fps  # Shows that ~12FPS is max anyway

# Need to calibrate/crop capture to get the right dimensions
scrcpy 
# INFO: Initial texture: 2336x1080

scrcpy --crop 1080:2336:0:0   # Original (portrait mode order)

# So aspect ratio is wrong... Let's resize : 1080./360*640 = 1920 
# (ie. really want 1920x1080 from the phone, centered, crop is 'portrait')
# (x-offset : (2336-1920)//2 = 208 )

scrcpy --crop 1080:1920:0:208   # Should be correct, but still seems offset...
scrcpy --crop 1080:1920:0:248   # 248 was chosen to 'center' display properly

scrcpy --crop 1080:1920:0:248 --max-size 640 --max-fps 20 --record file00.mp4
# Test the output file is 640x360 using 'ffmpeg -i file00.mp4'
#   Stream #0:0(und): Video: h264 (High) (avc1 / 0x31637661), yuv420p(...), 640x360, 19.78 fps ...

mpv --keep-open=yes file00.mp4

```


#### Other Resources

* OpenAI VPT (Video Pre-Training) : 
    * [Blog Post](https://openai.com/blog/vpt/) and [Code Repo](https://github.com/openai/Video-Pre-Training)
    * See above for links to VPT explainer videos
