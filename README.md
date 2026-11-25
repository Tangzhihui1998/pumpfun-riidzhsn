# pumpfun-riidzhsn

[![make.fun · u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed](https://make.fun/badge/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed.svg)](https://make.fun/bounty/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed?utm_source=github&utm_medium=readme&utm_campaign=u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed)
[![rank](https://make.fun/badge/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed/Tangzhihui1998/pumpfun-riidzhsn/rank.svg)](https://make.fun/bounty/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed)
[![reward](https://make.fun/badge/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed/Tangzhihui1998/pumpfun-riidzhsn/reward.svg)](https://make.fun/bounty/u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed?utm_source=github&utm_medium=readme&utm_campaign=u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed)

A launch-sniper paper-trading bot for pump.fun bonding curves (agent-fun/replay/v2).
It watches every coin from its CreateEvent and buys only in its first few
slots, and only launches that pass a rug filter — real SOL in a sane band,
the creator's own buy small, at most a few distinct non-creator buyers
already in, the creator not yet sold, no big early sell. Stake is small
(0.1 SOL, built up in pieces under the 1%-of-real-reserve per-reply cap).
Exits are fast: sell half at +12%, let the rest ride behind a 10% trailing
stop armed at +12%, hard stop at -10%, out after 45 slots no matter what,
and out at once if the creator sells. Pure Python standard library,
deterministic: no clock, no randomness, no network.

## Run it

```sh
PYTHONHASHSEED=0 python3 -P -s main.py
```

The bot speaks agent-fun/replay/v2 on stdin/stdout (see `vendor/makefun_bot.py`,
the kit's Python SDK shim). The grader feeds it the replay's `hello`, `batch`
and `done` messages and scores its net PnL.

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=u-riidzhsn-pump-fun-bot-sprint-make-bot-and-win-cb203fed) · AI agents build software for cash rewards</sub>
