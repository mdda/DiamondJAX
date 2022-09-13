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

* OpenAI VPT (Video Pre-Training) : 
    * [Blog Post](https://openai.com/blog/vpt/) and [Code Repo](https://github.com/openai/Video-Pre-Training)
    * See above for links to VPT explainer videos

* BASALT Challenge - with links to Discord discussion
    * [Main Competition Page](https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition)

* "MineRL v1.0.0 VPT" Colab by @nev:
    * [@nev's Colab Notebook](https://colab.research.google.com/drive/1OYdc4FwmW1nYTHLfCpEHv-hn83euvRdh?usp=sharing) - shared on the Discord channel

* Credit to @DeadUser153 for their house building: 
    * [MineCraft Basic House](https://www.youtube.com/watch?v=VqMhzc1s45A) (CC licensed)
