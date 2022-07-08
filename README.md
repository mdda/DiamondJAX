# DiamondJAX
`
#minecraft,#MineRL,#machinelearning,#deeplearning,#openai,#googlecolab,#jax,#pytorch
`

Repository of useful 'stuff' for the MineRL BASALT Challenge


### Minecraft and Machine Learning : First steps with MineRL
[Link to YouTube Video](https://youtu.be/8yIrWcyWGek)

* This episode's Colab Notebook : [DiamondJAX_00-Intro](https://colab.research.google.com/drive/1rJ3lGy-bG7kJRe_wYBWg7fjSaD9oOMDw?usp=sharing)
* Includes:
  + Installation of correct `MineRL` and `VPT` repos (takes ~20+mins)
  + Safely stowing the installation on Google Drive
    - ... enables re-installation in 2-3mins

#### Other Resources

* OpenAI VPT + IDM
  * [Blog Post](https://openai.com/blog/vpt/)
  * [Yannic Kilcher explanation](https://www.youtube.com/watch?v=oz5yZc9ULAc)
  * [Edan Meyer explanation](https://www.youtube.com/watch?v=ODat7kfZ-5k)
  
* MineDojo
  * Datasets and MineCLIP = https://minedojo.org/
    + Except MineCLIP seems to be un-released
  
* MineRL
  * Quick explanation - [here are the docs](https://minerl.readthedocs.io/en/v1.0.0/tutorials/index.html)

* Rationale for doing this... The BASALT Challenge:
  * [BASALT Challenge website](https://minerl.io/basalt/)
  * [BASALT Challenge at AICrowd](https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition)
  



### Minecraft and Machine Learning : Using VPT on Demo Video
[Link to YouTube Video](https://youtu.be/qdITG9B9s3c)

_(Apologies for the 'sparkly' person-in-picture effect)_


* This episode's Colab Notebook : [DiamondJAX_02-VPT-on-YouTube](https://colab.research.google.com/drive/17FiaBr8hqaHrfac4b-NUi3giF1qB--4g?usp=sharing)
* Includes:
    + `ffmpeg` video reformatting to 20FPS, correct size
    + `MineRL`-free usage of `VPT`

#### Notes

* Video content downloading
    * MineCraft Basic House (CC licensed)
        * URL='https://www.youtube.com/watch?v=VqMhzc1s45A'
    * `youtube-dl --list-formats ${URL}`

    * `# 18           mp4        640x360    360p  678k , avc1.42001E, 30fps, mp4a.40.2 (44100Hz)`
    * `youtube-dl --format 18 ${URL}  # 35Mb`

#### Other Resources

OpenAI VPT (Video Pre-Training) : 
* [Blog Post](https://openai.com/blog/vpt/)
* [Code Repo](https://github.com/openai/Video-Pre-Training)

BASALT Challenge - with links to Discord discussion
* [Main Competition Page](https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition)

"MineRL v1.0.0 VPT" Colab by @nev:
* [@nev's Colab Notebook](https://colab.research.google.com/drive/1OYdc4FwmW1nYTHLfCpEHv-hn83euvRdh?usp=sharing)

Credit to @DeadUser153 for their house building: 
* https://www.youtube.com/watch?v=VqMhzc1s45A





## License

This Repo is MIT-licensed (attribution required).

