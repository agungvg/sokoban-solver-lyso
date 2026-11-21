# Sokoban Solver

[![make.fun bounty](https://img.shields.io/badge/make.fun-bounty-blue)](https://make.fun/bounty/sokoban-solver-01-run-20261121)

Push-optimal Sokoban solver for make.fun's **Build the best Sokoban solver, 21 November 2026** bounty. One run (`node main.ts`, Node 22, stdlib only) answers all 5 instances of a set, writing `/output/<id>/solution.txt` for each.

Method: per-room breadth-first search over pushes — a state is the sorted box squares plus the player's reachable region — with dead-square and frozen-2x2 pruning (both sound, so the first solved state is push-optimal). Rooms are found by cutting the hallway row's dead squares out of the floor; boxes never leave their room, so the rooms' optima sum to the level's. Deterministic: fixed direction order, sorted boxes, a work-based state cap, no clock.

Practice set: **1,000,000** (5/5 at P*, ~1s). Also 1,000,000 on 6 held-out sets drawn with the kit's published generator (30 fresh instances).

License: MIT (see `LICENSE`).
