# MasterAI-2.0-1vs1-NoLimit  出售德州AI源码和训练模型；联系Telegram：@xuzongbin001或E-mail：masterai918@gmail.com

## Introduction

MasterAI v2.0 is an iterative algorithm derived from MasterAI v1.0 
It utilizes profound Reinforcement Learning + Search in imperfect-information games and achieves superhuman performance in heads-up no-limit Texas Hold’em. Furthermore, it is a major step toward developing technologies for multiagent interactions in real world.

![](https://raw.githubusercontent.com/deeptexas-ai/MasterAI-2.0-1vs1-NoLimit/main/proto/masterai.jpg) 

## Technology

1.MaterAI v2.0 algorithm generalizes the paradigm of self-play reinforcement learning and deep learning and search through gargantuan imperfect-information. It makes decisions by factoring in the probability distribution of different beliefs each player might have about the current state of the game and uses counterfactual Regret minimization (CFR) algorithm to search efficiently.


2.Our experiments confirmed that MasterAI does indeed converge to an approximate Nash equilibrium in two-player zero-zum game

## Technical bottlenecks

Some technical bottlenecks are encountered when training the algorithm model with CFR framework. For instance, the large state space is leading to too much computation:

1.Algorithm training has a large amount of calculation (2560000 * 1750 in the paper)

2.Deployment speculation and search time is too much: 3 ~ 5 seconds

3.The number of nodes in Abstract CFR (400BB) Betting Tree is too large, more than 400 million

## Contact us

Telegram：@xuzongbin001
