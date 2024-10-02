# HIVEX: Aerial Wildfire Suppression Environment

## Main Environment Features

<a href="url"><img src="[ANONYMIZED]" width="auto" style="border-radius:10px" alt="Aerial Wildfire Suppression Environment Features"></a>

## Process

<a href="url"><img src="[ANONYMIZED]" width="auto" style="border-radius:10px" alt="Aerial Wildfire Suppression Environment Process"></a>

## Environment Specifications

- Episode Length: 3000
- Agent Count: 3
- Neighbour Count: 0

**Vector Observations (8)** - Stacks: 1 - Normalized: True

- Local Position (2)
- Direction (2)
- Holding Water (1)
- Closest Tree Location (2)
- Closest Tree Burning (1)

**Visual Observations (42, 42, 3)** - Stacks: 1 - Normalized: True

- Downward Pointing Camera in RGB (1764)

**Continous Actions (1)**:

- Steer Left / Right (1)

**Discrete Actions (1)**:

- Branch 0 - Drop Water (2):
  - 0: Do Nothing
  - 1: Drop Water

## Rewards

- **Crossed Border** - This is a negative reward of $-100$ given when the border of the environment is crossed. The border is a square around the island in the size of $1500$ by $1500$. The island is $1200$ by $1200$.
- **Pick-up Water** - This is a positive reward of $100$ given when the agent steers the airplane towards water. The island is $1200$ by $1200$ and there is a girdle of water around the island with a width of $300$. There is a small negative reward for each time-step of $-1 / MaxStep$.
- **Fire Out** - This is a positive reward of $10$ given when the fire on the whole island dies out, with or without the active assistance of the agent.
- **Too Close to Village** - This is a negative reward of $-50$ given when the fire is closer than $150$ to the centre of the village.
- **Time Step Burning** - This is a negative reward of $-0.01$ given at each time-step, while the fire is burning.
- **Find Fire** - This is a positive reward of $100$ given when a burning tree has been found.
- **Find Village** - This is a positive reward of $100$ given when the village has been found and the distance between the current local airplane position and the village is less than $150$.
- **Extinguishing Tree** - This is a positive reward in the range of $[0, 5]$ given for each tree that has been in the state burning in time-step $t_{-1}$ and is now extinguished by dropping water at its location.
- **Preparing Tree** - This is a positive reward in the range of $[0, 1]$ given for each tree that has been in the state not burning in time-step $t_{-1}$ and is now wet by dropping water at its location.

## Tasks

- **Main Task: Minimize Time Fire Burning and Prevent Fire From Moving Towards Village** - This is the main task of the environment. Goal for the agent is to pick up water, and extinguish as many burning trees as possible, or prepare forest that is not yet burning. A secondary goal is to protect the village from approaching fire by extinguishing burning trees before it gets too close to the village or redirect the fire by preparing trees.
- **Subtask: Maximize Extinguished Burning Trees** - This is a subtask with the goal to extinguish as many burning trees as possible.
- **Subtask: Maximize Preparing Non-Burning Trees** - This is a subtask with the goal to prepare as many non-bruning trees as possible.
- **Subtask: Minimize Time Fire Burning** - This is a subtask with the goal to minimize the time of trees burning.
- **Subtask: Protect Village** - This is a subtask with the goal to protect the village from approaching fire.
- **Subtask: Pick Up water** - This is a subtask with the goal to pick up water.
- **Subtask: Drop Water** - This is a subtask with the goal to drop water anywhere.
- **Subtask: Find Fire** - This is a subtask with the goal to find a burning tree.
- **Subtask: Find Village** - This is a subtask with the goal to find the village.
