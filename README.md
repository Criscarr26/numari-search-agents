# Numari — Search agents (DFS, BFS and A*)

Implementation of the **Numari** puzzle, playable in the console, together with
three search agents that solve it automatically. *Introduction to Artificial
Intelligence* project (ITLA).

## The game

In Numari you start on a numbered cell and must walk exactly that many empty
cells to reach the next number, repeating the process until you visit **all** the
cells on the board. It includes 16 levels (from easy 3x3 to very hard 10x10) and
supports custom levels from `.txt` files.

## The agents

| Agent | Structure | Detail |
|---|---|---|
| **DFS** | Explicit stack | UDLR expansion reversed on push |
| **BFS** | Queue (deque) | Guarantees the shortest path |
| **A\*** | Priority queue | `f(n) = g(n) + h(n)` with 5 normalized heuristics |

The A\* heuristics (remaining cells, pending steps, remaining numbers, isolation
and Manhattan distance) are combined with **8 weight configurations** to compare
their effect on the search.

Each run reports standard metrics: path to the goal, cost, expanded nodes,
search depth, time and peak RAM usage.

## Files

- [`Numari_Agentes_Final.ipynb`](Numari_Agentes_Final.ipynb) — full version with the three agents and the menu
- [`Numari_final.ipynb`](Numari_final.ipynb) — playable game version
- [`Numari_Benchmark.xlsx`](Numari_Benchmark.xlsx) — comparative agent results

## How to run it

Designed for **Google Colab** (it uses `google.colab.output` to clear the menu
screen). Open the notebook, run the cells in order and the last cell starts the
interactive menu: choose a level, play manually or let an agent solve it.
