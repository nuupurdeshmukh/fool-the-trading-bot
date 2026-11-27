# Fool the Trading Bot

**WiDS 2026 · Winter in Data Science, Analytics Club, IIT Bombay**

Train a machine learning trading bot. Build an attacker bot that tricks it with fake market activity.
Then build a defense that catches the tricks.

> One bot reads the market, another bot lies to it, and we teach the first bot to spot the lies.

No real money and no real exchange: everything runs on `lobsim`, a small stock market simulator written
in plain Python for this project. You can read every line of it.

## Quick start

**New to Python data tools or ML?** Start with `notebooks/week0_starter_pack.ipynb`: short exercises that
check themselves, plus links to free tutorials. All the reading for every week is in [RESOURCES.md](RESOURCES.md).

**Google Colab (easiest):** open `notebooks/week1_order_books.ipynb` in Colab and run the cells from the top.
The first cell downloads this repo for you.

**On your own laptop** (Python 3.10 or newer):

```bash
git clone https://github.com/nuupurdeshmukh/fool-the-trading-bot.git
cd fool-the-trading-bot
pip install -r requirements.txt
jupyter notebook notebooks/week1_order_books.ipynb
```

Check that everything works:

```bash
pytest
```

## Your first simulated market in 3 lines

```python
from lobsim import simulate

market = simulate(steps=2000, seed=42)
market.snapshots.head()   # one row per time step: prices, spread, volume, top 5 levels of the book
```

## Repo layout

```
fool-the-trading-bot/
├── lobsim/                 the market simulator
│   ├── orderbook.py        limit order book: placing, matching and cancelling orders
│   ├── agents.py           background traders (market maker, noise, fundamental) + Agent base class
│   └── simulator.py        runs the market step by step and records data as pandas DataFrames
├── notebooks/
│   ├── week0_starter_pack.ipynb   Python, NumPy, Pandas and ML basics, with exercises
│   └── week1_order_books.ipynb
├── tests/                  checks that the simulator is correct (run with `pytest`)
├── data/                   put downloaded datasets here (not committed to git)
├── RESOURCES.md            reading list for every week
├── requirements.txt
└── pyproject.toml
```

## Weekly plan

| Week | Topic | Deliverable |
|---|---|---|
| 0 | Starter pack (before the project) | Week 0 notebook with all checks passing |
| 1 | Markets and order books | Week 1 notebook with plots and exercises |
| 2 | Trading bot: rules first, then ML | A bot that predicts mid price moves and a backtest of its profit |
| 3 | Attacker bot: spoofing | A spoofer that makes your Week 2 bot lose money, with numbers |
| 4 | Smarter attacks | Adversarial or RL-based attacker (stretch goal) |
| 5 | Defenses | A manipulation detector and a more robust bot |
| 6 | Tournament and final report | Red team vs blue team leaderboard + short report |

Notebooks for later weeks will be added each week.

## How the simulator works (short version)

* Prices are stored as whole **ticks** inside the book (1 tick = 1 cent). DataFrames show dollars.
* Each time step, a hidden "true value" of the stock moves a little at random. Then every agent gets
  one turn, in random order, to place or cancel orders. Then we record a snapshot of the book.
* Your own bots subclass `lobsim.Agent` and implement `act(market)`. Use `market.place_limit`,
  `market.place_market` and `market.cancel` so trades and profit are tracked correctly.

```python
from lobsim import Agent, BUY, simulate

class AlwaysBuy(Agent):
    def act(self, market):
        if market.t % 100 == 0:
            market.place_market(self, BUY, 5)

market = simulate(steps=1000, extra_agents=[AlwaysBuy("my_bot")])
```

## Mentors

Mentors: Nuupur Deshmukh and Samyajyoti Biswas · Questions: open a GitHub issue or ask on the WiDS group.
