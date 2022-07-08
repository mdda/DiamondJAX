# DiamondJAX
`
#minecraft,#MineRL,#machinelearning,#deeplearning,#openai,#googlecolab,#jax,#pytorch
`

Repository of useful stuff for the MineRL BASALT Challenge.


### Episode 1 (2022-06-28) : First steps with MineRL &rarr; [YouTube Video](https://youtu.be/8yIrWcyWGek)

* This episode's Colab Notebook : [DiamondJAX_00-SetUp](https://colab.research.google.com/drive/1rJ3lGy-bG7kJRe_wYBWg7fjSaD9oOMDw?usp=sharing)
* Includes:
  + Installation of correct `MineRL` and other repos (takes ~20+mins)
  + Safely stowing the installation on Google Drive
    - ... enables re-installation in 2-3mins
  + Basic 'turn-360' and 'pull up inventory' action tests

#### Other Resources

* OpenAI VPT + IDM
  * [Blog Post](https://openai.com/blog/vpt/)
  * Explanation videos by [Yannic Kilcher](https://www.youtube.com/watch?v=oz5yZc9ULAc) and [Edan Meyer](https://www.youtube.com/watch?v=ODat7kfZ-5k)
  
* MineDojo
  * Datasets and MineCLIP = https://minedojo.org/
    + Except MineCLIP seems to be un-released
  
* MineRL
  * Quick explanation - [here are the docs](https://minerl.readthedocs.io/en/v1.0.0/tutorials/index.html)

* Rationale for doing this... The BASALT Challenge:
  * [BASALT Challenge website](https://minerl.io/basalt/) and [BASALT Challenge at AICrowd](https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition)
  



### Episode 2 (2022-07-06) : OpenAI VPT for YouTube Videos &rarr; [YouTube Video](https://youtu.be/qdITG9B9s3c)

_(Apologies for the 'sparkly' person-in-picture effect)_


* This episode's Colab Notebook : [DiamondJAX_02-VPT-on-YouTube](https://colab.research.google.com/drive/17FiaBr8hqaHrfac4b-NUi3giF1qB--4g?usp=sharing)
* Includes:
    + `ffmpeg` video reformatting to 20FPS, correct size
    + `MineRL`-free usage of `VPT`
    + Terminal pretty-print of `VPT` output actions

#### Notes

* Video content downloading
    
```bash
URL='https://www.youtube.com/watch?v=VqMhzc1s45A'
youtube-dl --list-formats ${URL}
# 18           mp4        640x360    360p  678k , avc1.42001E, 30fps, mp4a.40.2 (44100Hz)youtube-dl --format 18 ${URL}  # 35Mb
```

#### Other Resources

OpenAI VPT (Video Pre-Training) : 
* [Blog Post](https://openai.com/blog/vpt/) and [Code Repo](https://github.com/openai/Video-Pre-Training)
* See above for links to VPT explainer videos

BASALT Challenge - with links to Discord discussion
* [Main Competition Page](https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition)

"MineRL v1.0.0 VPT" Colab by @nev:
* [@nev's Colab Notebook](https://colab.research.google.com/drive/1OYdc4FwmW1nYTHLfCpEHv-hn83euvRdh?usp=sharing) - shared on the Discord channel

Credit to @DeadUser153 for their house building: 
* [MineCraft Basic House](https://www.youtube.com/watch?v=VqMhzc1s45A) (CC licensed)


### Episode 3 (2022-07-12) : OpenAI VPT for Android Demos &rarr; [YouTube Video](TBA)

* This episode's Colab Notebook : [DiamondJAX_03-VPT-on-Android](TBA)
* Includes (extending the previous Colab):
    + Calibration of VPT camera moves
      - Seen in previous text output of VPT camera changes: 
        - `0.00, +0.62, +1.61, +3.22, +5.81, +10.00` degrees
        - (including the negative versions &rArr; 11 steps)
      - After calibration step (using Colab+GIMP): 
        - `0.0, +4.5, +10.5, +21.5, +38.5, +66.5` pixels (+/-)
    + `ffmpeg` overlay for `VPT` output actions


#### Notes

* Android phone screen recording : [Good Blog post](https://www.fosslinux.com/46780/cast-video-android-linux.htm)
  + STEP1 : Set up Android USB connection :
```bash
dnf install android-tools
```

    + On phone : `Settings - About Phone - Lenovo version : Tap 7 times` (to become developer)
    + On phone : `Settings - Advanced Options - Developer Options (new entry!) - USB debugging : Enable`

    * Reconnect USB cable
    * Rerun `adb devices` to see the phone connected
    * May have to turn on/off USB debugging, switch to Transfer files...
        * Until 'Authorized this machine' dialog appears (say Yes) 
    * Make sure 'adb devices' is stable : 
        * Potentially change USB port on desktop machine (!) ...

  * STEP2 : Run [the scrcpy tool](https://github.com/Genymobile/scrcpy/blob/master/FAQ.md):
    * Android device needs to be at least API 21 (Android 5.0)
    * For Fedora, a [COPR](https://fedoraproject.org/wiki/Category:Copr) package is available: [`scrcpy`](https://copr.fedorainfracloud.org/coprs/zeno/scrcpy/)
    * Download [the file](https://copr.fedorainfracloud.org/coprs/zeno/scrcpy/)
        * ... to `/etc/yum.repos.d/zeno-scrcpy-fedora-34.repo`
```bash
dnf install scrcpy
# And as USER (some sample commands):
scrcpy --max-size 720 --max-fps 20
scrcpy --print-fps  # Shows that ~12FPS is max anyway
scrcpy --max-size 720 --max-fps 20 --record file00.mp4
```


#### Other Resources

OpenAI VPT (Video Pre-Training) : 
* [Blog Post](https://openai.com/blog/vpt/) and [Code Repo](https://github.com/openai/Video-Pre-Training)
* See above for links to VPT explainer videos






## License

This Repo is MIT-licensed (attribution required).

