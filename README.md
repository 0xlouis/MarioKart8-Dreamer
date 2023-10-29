# MarioKart8-Dreamer
A MarioKart8 RL agent which is model based. Trained with DreamerV3 :
```
@article{hafner2023dreamerv3,
  title={Mastering Diverse Domains through World Models},
  author={Hafner, Danijar and Pasukonis, Jurgis and Ba, Jimmy and Lillicrap, Timothy},
  journal={arXiv preprint arXiv:2301.04104},
  year={2023}
}
```

# Coming soon
This project was completed on 03/2023 as a personal project first. I managed to train an agent that beat the hardest CPU in a few hundred hours of play (ingame time).

Now, I'll try to publish an easy-to-read and reproducible version of this project with the aim of serving as an example of "HowTo" use Switch games for RL applications.

The RL agent is a world model that takes the game's RGB image as input and produces an XBox controller command (with analog joystick) as output. Which is really an human like IO.

The agent was trained on one track: the Rainbow Road, which is the longest track in the game.
The game was configured in 150cc (with or without mirror) Hard CPU with franetic items.
After a few hundred hours, the bot was able to:
* Manage the kart to get a serval microboost by jumping or drifting.
* Find all the shortcuts on the map (at least all the shortcuts taken by the speedrunners).
* The bot has about 70% chance of winning the race in first place and >90% in the top 3.
* Interestingly, the bot found a way to use its environment to defeat the incoming red shells (approaching the wall at a good angle to destroy the shell on the wall).
  
The bot is struggling (or has not been sufficiently trained):
* The bot doesn't seem to use objects optimally (for example, the agent doesn't use objects to protect himself from attacks, which is an obvious mistake from my point of view).
* Similarly, it's rare to see the bot defeat the blue shell with an horn.

The training and inference script will be published with the trained network parameters.

This project depend on `MarioKart8-Gym-Env`.
