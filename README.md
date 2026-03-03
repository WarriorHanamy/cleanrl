# CleanRL (Clean Implementation of RL Algorithms)

CleanRL is a Deep Reinforcement Learning library that provides high-quality single-file implementation with research-friendly features. The implementation is clean and simple, yet we can scale it to run thousands of experiments using AWS Batch. The highlight features of CleanRL are:

Notable CleanRL-related projects:

* [corl-team/CORL](https://github.com/corl-team/CORL): Offline RL algorithm implemented in CleanRL style
* [pytorch-labs/LeanRL](https://github.com/pytorch-labs/LeanRL): Fast optimized PyTorch implementation of CleanRL RL algorithms using CUDAGraphs.


> ⚠️ **NOTE**: CleanRL is *not* a modular library and therefore it is not meant to be imported. At the cost of duplicate code, we make all implementation details of a DRL algorithm variant easy to understand, so CleanRL comes with its own pros and cons. You should consider using CleanRL if you want to 1) understand all implementation details of an algorithm's variant or 2) prototype advanced features that other modular DRL libraries do not support (CleanRL has minimal lines of code so it gives you great debugging experience and you don't have do a lot of subclassing like sometimes in modular DRL libraries).

## Get started

Prerequisites:
* Python >=3.7.1,<3.11
* [uv 0.7.9+](https://docs.astral.sh/uv/)

To run experiments locally, give the following a try:

```bash
uv run python cleanrl/ppo.py \
    --seed 1 \
    --env-id CartPole-v0 \
    --total-timesteps 50000

# open another terminal and enter `cd cleanrl/cleanrl`
tensorboard --logdir runs
```

To use experiment tracking with wandb, run
```bash
wandb login # only required for the first time
uv run python cleanrl/ppo.py \
    --seed 1 \
    --env-id CartPole-v0 \
    --total-timesteps 50000 \
    --track \
    --wandb-project-name cleanrltest
```
