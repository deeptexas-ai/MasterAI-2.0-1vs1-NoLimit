# Deep Hold'em AI: HUNL Poker AI Research Source Code

> A research codebase for heads-up no-limit Texas Hold'em (HUNL), covering CFR subgame solving, ReBeL-style recursive solving, counterfactual value learning, self-play, supervised strategy learning and C++ Monte Carlo components.

[简体中文](README.md) · [繁體中文](README.zh-TW.md) · [Project site](https://deeptexas-ai.github.io/deep-holdem-ai/)

![Deep Hold'em AI table demonstration](docs/assets/screenshots/masterai-table.jpg)

## What this repository is

Deep Hold'em AI is a research project for poker AI, game theory and imperfect-information games. The public tree includes a HUNL rules engine, game-tree and CFR subgame solvers, recursive solving, value networks, self-play data generation, replay infrastructure, supervised strategy learning and a C++ Monte Carlo layer.

It is intended for research, offline training, reproducible evaluation and education. It is not a real-time online poker assistant and does not provide third-party client recognition, automated play or detection-evasion features.

## Capabilities verified against the source tree

| Area | What is implemented | Location |
| --- | --- | --- |
| HUNL engine | 52-card deck, four streets, fold/check-call/raise/all-in abstraction, terminal utilities and hand evaluation | `game/texas_holdem/` |
| CFR solving | Regret updates, average strategies, best response, exploitability, EV and reach-probability utilities | `game/subgame_solving.py` |
| Recursive solving | Public-state subgames, private-hand belief propagation and continuation solving | `game/recursive_solving.py` |
| ReBeL-style entry point | Value-network loading and root-strategy computation from state and beliefs | `robot/rebel/` |
| Self-play training | Multiprocess generation, value/policy losses, model synchronization, replay buffers and validation | `cfv/selfplay.py`, `rela/` |
| Supervised strategy | Solved-state datasets and a PyTorch `StrategyNet` | `supervised_strategy/` |
| Monte Carlo tools | C++ simulator, Python hand-ranking helpers and binding infrastructure | `csrc/mc/`, `robot/gto_mc/` |
| Experiment configs | Blinds, stacks, raise ratios, CFR iterations, tree depth, devices and training scale | `conf/` |

## Game and solving model

The engine models two-player no-limit Hold'em across preflop, flop, turn and river. A public state records board cards, committed chips, player to act, feasible actions and raise count. The default abstraction offers fold, check/call, several pot-relative raises and all-in.

The solver expands a subgame from a public state, performs CFR iterations, estimates truncated leaves with a value network when configured, and propagates private-hand beliefs after sampled actions. Self-play processes generate training examples for value and policy learning; evaluation utilities expose expected value, best response and exploitability calculations.

## Training configuration evidence

This repository-provided image shows configurable iterations, regret settings, pruning, model paths and Redis connection details. It is a training configuration/terminal view, not an online table-recognition interface.

![Deep Hold'em AI training configuration](docs/assets/screenshots/training-config.png)

## Historical table presentation

<p align="center">
  <img src="docs/assets/screenshots/poker-table.jpg" alt="Deep Hold'em AI robot table demonstration" width="48%">
  <img src="docs/assets/screenshots/masterai-table.jpg" alt="MasterAI poker table demonstration" width="48%">
</p>

These repository-provided images illustrate historical presentation material only. They do not establish integration with or automation of any third-party poker platform.

## Repository map

```text
cfv/                  counterfactual-value models and self-play
conf/                 HUNL, ReBeL and supervised experiment configs
csrc/                 C++ Monte Carlo and Python binding dependencies
game/                 states, trees, CFR and recursive subgame solving
rela/                 replay buffers, data loops and runtime context
robot/rebel/          ReBeL-style strategy-solving entry point
robot/gto_mc/         hand-ranking and Monte Carlo-related tools
supervised_strategy/  strategy datasets and supervised networks
tests/                rules and algorithm tests
```

## Good research use cases

- HUNL, CFR, recursive solving and imperfect-information game research
- Counterfactual-value and self-play training experiments
- Strategy networks, replay systems and offline bot evaluation
- Teaching game trees, expected value, best response and exploitability
- Extending mixed Python/C++ poker-computation components

## Before running

The tree contains historical components, C++ extensions, model-path assumptions and distributed-training configuration. Review `conf/`, build files and tests, then adapt the Python, PyTorch, CMake, compiler and optional Redis environment. The public repository does not substantiate a one-click executable or a 30-second installation claim.

## Responsible use

Use this project only for lawful research, education, offline training and benchmarking. Do not use it for unauthorized real-time assistance, automated online play, platform-rule evasion or any activity that undermines fair play. Users are responsible for applicable law and third-party terms.

## Contact

- Telegram: [xuzongbin001](https://t.me/xuzongbin001)
- Email: [masterai918@gmail.com](mailto:masterai918@gmail.com)
- GitHub: [deeptexas-ai/deep-holdem-ai](https://github.com/deeptexas-ai/deep-holdem-ai)

Keywords: Texas Hold'em AI source code, HUNL poker AI, CFR poker, ReBeL poker, recursive solving, self-play, counterfactual value, poker bot research, imperfect-information games.

