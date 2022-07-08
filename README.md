# DiamondJAX
Repository of useful 'stuff' for the MineRL BASALT Challenge


### Minecraft and Machine Learning : First steps with MineRL
`
#minecraft,#MineRL,#machinelearning,#deeplearning,#openai,#googlecolab,#jax,#pytorch
`

[Link to YouTube Video](https://youtu.be/8yIrWcyWGek)

* OpenAI VPT + IDM
  * https://openai.com/blog/vpt/
  * Yannic explanation = https://www.youtube.com/watch?v=oz5yZc9ULAc
  * Edan Meyer = https://www.youtube.com/watch?v=ODat7kfZ-5k
  
* MineDojo
  * Datasets and MineCLIP = https://minedojo.org/
  
* MineRL
  * Quick explanation
  * https://minerl.readthedocs.io/en/v1.0.0/tutorials/index.html
  
* Look at the Colab
  https://colab.research.google.com/drive/1rJ3lGy-bG7kJRe_wYBWg7fjSaD9oOMDw?usp=sharing

* Coming up next... BASALT Challenge
  * https://minerl.io/basalt/
  * https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition
  
  


### Minecraft and Machine Learning : Using VPT on Demo Video
`
#minecraft,#MineRL,#machinelearning,#deeplearning,#openai,#googlecolab,#jax,#pytorch
`
[Link to YouTube Video](https://youtu.be/qdITG9B9s3c)


* Colab Notebook : DiamondJAX_02-VPT-on-YouTube
  * https://colab.research.google.com/drive/17FiaBr8hqaHrfac4b-NUi3giF1qB--4g?usp=sharing
	* MineCraft Basic House (CC licensed)
		* URL='https://www.youtube.com/watch?v=VqMhzc1s45A'
    * `youtube-dl --list-formats ${URL}`

    * `# 18           mp4        640x360    360p  678k , avc1.42001E, 30fps, mp4a.40.2 (44100Hz)`
    * `youtube-dl --format 18 ${URL}  # 35Mb`

OpenAI VPT (Video Pre-Training)
* https://openai.com/blog/vpt/
* https://github.com/openai/Video-Pre-Training

BASALT Challenge - with links to Discord discussion
* https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition

"MineRL v1.0.0 VPT" Colab by @nev:
* https://colab.research.google.com/drive/1OYdc4FwmW1nYTHLfCpEHv-hn83euvRdh?usp=sharing

DiamondJAX_00-SetUp
* Colab set-up : see previous video
* But we won't be needing the full MineRL installation here...

Credit to @DeadUser153 for their house building: 
* https://www.youtube.com/watch?v=VqMhzc1s45A

New Notebook : VPT for YouTube videos
* https://colab.research.google.com/drive/17FiaBr8hqaHrfac4b-NUi3giF1qB--4g?usp=sharing

(Apologies for the 'sparkly' person-in-picture effect)




## License

This Repo is MIT-licensed (attribution required).

