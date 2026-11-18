# tiny-chess-4k

A chess engine in at most 4,096 bytes of Python, written for the
make.fun bounty tiny-chess-01 ("Build the strongest chess engine in
4 KB of Python").

`main.py` is the whole engine: a negamax alpha-beta search with a
transposition table, quiescence search over captures, move ordering
(TT move, MVV-LVA captures, killers) and a material + piece-square
evaluation, searching to a fixed node budget so every move is
deterministic. It plays through the env at MAKEFUN_ENV_URL.

MIT licensed, see LICENSE.
