# Bootstrap DQN

This repo contains our implementation of a Bootstrapped DQN with options to add a Randomized Prior, Dueling, and Double DQN in ALE games. 

[Deep Exploration via Bootstrapped DQN](https://arxiv.org/abs/1602.04621)

[Randomized Prior Functions for Deep Reinforcement Learning](https://arxiv.org/abs/1806.03335)

# Some results on Breakout

This gif depicts the orange agent from below winning the first game of Breakout and eventually winning a second game. The agent reaches a high score of 830 in this evaluation.  There are several gaps in playback due to file size. We show agent steps [1000-1500], [2400-2600], [3000-4500], and [16000-16300]. 

### Comparison:  

![alt text](figs/breakout_winning_gaps.gif?raw=true "Breakout Agent - Bootstrap, Prior")

- (blue) DQN with epsilon greed annealed between 1 and 0.01    
- (orange) Bootstrap with epsilon greedy annealed between 1 and 0.01  
- (green) Bootstrap without epsilon greedy exploration  
- (red) Bootstrap with randomized prior  

All agents were implemented as Dueling, Double DQNs. The xlabel in these plots, "steps", 
refers to the number of states the agent observed thus far in training. Multiply by 4 to account for a frame-skip of 4 to describe the total number of frames the emulator has progressed. 

Our agents are sent a terminal signal at the end of life. They face a deterministic state progression after an random number<30 of no-op steps at the beginning of each episode. 

![alt text](figs/breakout_avg_training_reward_steps.png?raw=true "Breakout Agent - Bootstrap, Prior")

# Some results on Freeway

![alt text](figs/small_ATARI_step0001508988_r0024_testcolor.gif?raw=true "Freeway Agent - Bootstrap with Prior")

![alt text](figs/freeway_9heads_prior_episode_reward.png?raw=true "Freeway Agent - Bootstrap with Prior")

# Dependencies

atari-py installed from https://github.com/kastnerkyle/atari-py  
torch='1.0.1.post2'  
cv2='4.0.0'  


# References

We referenced several execellent examples/blogposts to build this codebase: 

[Discussion and debugging w/ Kyle Kaster](https://gist.github.com/kastnerkyle/a4498fdf431a3a6d551bcc30cd9a35a0)

[Fabio M. Graetz's DQN](https://github.com/fg91/Deep-Q-Learning/blob/master/DQN.ipynb)

[hengyuan-hu's Rainbow](https://github.com/hengyuan-hu/rainbow)

[Dopamine's baseline](https://github.com/google/dopamine)
