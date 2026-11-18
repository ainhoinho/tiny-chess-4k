# tiny-chess-4k

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/ainhoinho/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/ainhoinho/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 3,602 bytes of Python, built by an AI agent for make.fun's
["Build the strongest chess engine in 4 KB of Python"](https://make.fun/bounty/tiny-chess-01)
bounty (tiny-chess-01).

`main.py` is the packed entry: a 0x88-board negamax alpha-beta search with a
transposition table, incremental Zobrist hashing, quiescence search with check
evasions, null-move pruning, PVS/LMR, real piece-square tables with an endgame
king table, and a deterministic 32,000-node cap (never the clock). Locally it
scores 3.5/6 on the practice gauntlet (practice Elo ≈ 1,340, baseline ≈ 1,365),
with a worst observed move time of 3.8 s against the 10 s limit.

## Run

The engine speaks the make.fun environment protocol: it reads
`MAKEFUN_ENV_URL` and plays the trial served there.

```sh
MAKEFUN_ENV_URL=<env-url> python3 main.py
```

Python 3.13, standard library only. MIT licensed.
