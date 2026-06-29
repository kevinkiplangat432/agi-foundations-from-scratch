# agi-foundations-from-scratch

A step-by-step reimplementation of the algorithms behind AlphaGo, AlphaFold, and AlphaStar, the systems Google DeepMind built on the path toward general artificial intelligence.

Built from research papers, from scratch, by a 20-year-old software engineering and datascience student in Nairobi, Kenya.

---

## What this is

DeepMind published the research papers behind their most celebrated systems. The algorithms are public. The ideas belong to science. This repo is an attempt to truly understand those ideas by building them, not importing a library, not following a tutorial, but reading the papers and writing the code.

The progression moves from the simplest possible game (Tic-tac-toe) to increasingly complex environments, each one introducing exactly one new layer of difficulty. The goal is not to reproduce DeepMind's compute scale. The goal is to reproduce the *learning dynamic* — an agent that genuinely improves through self-play.

---

## The core algorithm

Every game in this repo is powered by the same engine, based on the **AlphaZero** paper (Silver et al., 2018):

- **Monte Carlo Tree Search (MCTS)** — a search algorithm that explores possible futures
- **Deep neural network** — a policy head (what move to make) + value head (who is winning)
- **Self-play** — the agent plays against itself, generating training data
- **No human knowledge** — the agent learns entirely from scratch

---

## Project structure

```
agi-foundations-from-scratch/
├── core/               # The engine: MCTS, neural net base, self-play loop
├── games/              # One folder per game, each implementing the same interface
├── experiments/        # Saved models and training logs per game
├── papers/             # Notes and summaries of the source research papers
├── ROADMAP.md          # Full progression from Tic-tac-toe to novel domains
└── requirements.txt
```

---

## Progression

| Stage | Game | New concept introduced |
|-------|------|----------------------|
| 1 | Tic-tac-toe | Core MCTS + self-play loop |
| 2 | Connect Four | Larger action space |
| 3 | Othello | Dynamic valid moves |
| 4 | 9x9 Go | Spatial reasoning, longer horizon |
| 5 | Checkers | Piece types, forced moves |
| 6 | Chess | Full AlphaZero benchmark |
| 7 | Atari (Pong) | Raw pixel input |
| 8 | Custom domain | Original research territory |

---

## Papers

- Silver et al. (2016) — *Mastering the game of Go with deep neural networks and tree search*
- Silver et al. (2017) — *Mastering the game of Go without human knowledge* (AlphaGo Zero)
- Silver et al. (2018) — *A general reinforcement learning algorithm that masters chess, shogi, and Go* (AlphaZero)
- Vinyals et al. (2019) — *Grandmaster level in StarCraft II using multi-agent reinforcement learning* (AlphaStar)
- Jumper et al. (2021) — *Highly accurate protein structure prediction with AlphaFold*

---

## Stack

- Python 3.10+
- PyTorch
- NumPy

---

## Author

Kevin — software engineering and data science student, Nairobi, Kenya.
Building ARVIS (AI infrastructure monitoring for African enterprises) in parallel.
Long-term: Google DeepMind. Even longer term: an AI research institution focused on African problems.
