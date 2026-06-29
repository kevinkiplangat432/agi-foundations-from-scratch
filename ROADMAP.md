# Roadmap — From Tic-tac-toe to AGI Foundations

This document maps the full learning progression of this project.
Each stage builds on the last. The rule for moving forward: the agent must demonstrably improve through self-play before advancing.

---

## Tier 1 — Learn the core loop
*Goal: get MCTS + neural net + self-play working end to end*

### Stage 1: Tic-tac-toe
- 3x3 board, 2 players, 9 possible actions
- Concepts: MCTS, policy head, value head, self-play data generation, training loop
- Success criteria: agent never loses to a random player
- Status: [ ] Not started

### Stage 2: Connect Four
- 6x7 board, larger action space (7 columns)
- Concepts: slightly deeper search, handling draws
- Success criteria: agent plays winning lines consistently
- Status: [ ] Not started

### Stage 3: Othello (Reversi)
- 8x8 board, dynamic valid moves that change every turn
- Concepts: masking invalid actions in the policy head
- Success criteria: agent beats a greedy (most-captures) baseline
- Status: [ ] Not started

---

## Tier 2 — Real search depth
*Goal: stress-test the architecture with longer games and larger boards*

### Stage 4: 9x9 Go
- First serious test of spatial reasoning
- Concepts: territory, ko rule, passing, scoring
- Concepts (implementation): board history as input channels, Tromp-Taylor scoring
- Success criteria: agent plays legal, sensible Go — avoids obvious blunders
- Status: [ ] Not started

### Stage 5: Checkers
- Piece types, forced captures, king promotion
- Concepts: asymmetric piece representation in the neural net input
- Success criteria: agent beats a random player consistently
- Status: [ ] Not started

### Stage 6: Chess
- The full AlphaZero benchmark
- Concepts: 8x8x73 action space encoding, castling, en passant, threefold repetition
- External library: python-chess for move generation
- Success criteria: agent reaches a recognizable playing style, avoids hanging pieces
- Status: [ ] Not started

---

## Tier 3 — Leave board games
*Goal: adapt the algorithm to new input types*

### Stage 7: Atari — Pong
- Raw pixel input (210x160 RGB frames)
- Concepts: convolutional front-end, frame stacking, reward shaping
- This is where AlphaZero meets the Atari/DQN lineage
- Success criteria: agent learns to rally and score
- Status: [ ] Not started

### Stage 8: Custom environment
- Define a problem no one has cleanly solved with this framework
- Candidate: resource allocation, anomaly detection as a sequential decision game
- This is where the paper lives
- Status: [ ] Not started

---

## Tier 4 — Research territory
*Goal: original contribution*

### Stage 9: Novel domain application
- Apply AlphaZero-style self-play to a domain relevant to African infrastructure
- Candidate domains: network anomaly detection, energy grid optimization, fraud detection as a game
- Write the paper. LaTeX on Overleaf. NeurIPS/ICML format.
- Status: [ ] Not started

---

## Key papers (read in this order)

1. Silver et al. (2016) — AlphaGo [start here, understand the motivation]
2. Silver et al. (2017) — AlphaGo Zero [the clean version, no human data]
3. Silver et al. (2018) — AlphaZero [the generalized algorithm, what this repo implements]
4. Vinyals et al. (2019) — AlphaStar [multi-agent, imperfect information]
5. Jumper et al. (2021) — AlphaFold 2 [different domain, same DeepMind DNA]

---

## Compute strategy

Local machine (16GB RAM, 512GB storage):
- Tier 1 and early Tier 2 fully runnable locally
- Reduce residual blocks to 6-10 (original AlphaZero uses 40)
- Limit self-play iterations — learning signal matters, not scale

Google Colab / Kaggle (free GPU):
- Heavier Tier 2 runs (Go, Chess)
- All Tier 3 experiments

---

*Last updated: June 2026*
