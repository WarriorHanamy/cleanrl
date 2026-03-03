# CleanRL (Clean Implementation of RL Algorithms)

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

To use experiment tracking with swanlab, run
```bash
swanlab login # only required for the first time
uv run python cleanrl/ppo.py \
    --seed 1 \
    --env-id CartPole-v0 \
    --total-timesteps 50000 \
    --track \
    --swanlab-project-name cleanrltest
```
