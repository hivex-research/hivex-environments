# HIVEX: Ocean Plastic Collection Environment

## Main Environment Features

<a href="url"><img src="https://github.com/hivex-research/hivex-environments/blob/main/docs/images/OPC_desc.jpg" width="auto" style="border-radius:10px" alt="Ocean Plastic Collection Environment Features"></a>

## Process

<a href="url"><img src="https://github.com/hivex-research/hivex-environments/blob/main/docs/images/OPC_process.jpg" width="auto" style="border-radius:10px" alt="Ocean Plastic Collection Environment Process"></a>

## Environment Specifications

- Episode Length: 5000
- Agent Count: 3
- Neighbour Count: 1

**Vector Observations (6)** - Stacks: 2 - Normalized: True
- Local Position (2)
- Direction (2)
- Closest Neighbouring Vessel (2)

**Visual Observations (25, 25, 1)** - Stacks: 2 - Normalized: True
- Trash (625)

**Discrete Actions (2)**
- Branch 0 - Throttel (2):
    - 0: Do Nothing
    - 1: Accelerate
- Branch 1 - Steer (3):
    - 0: Do Nothing
    - 1: Turn Right
    - 2: Turn Left

## Rewards

- **Collect Trash** - This is a positive reward of $1$ given for each floating plastic pebble collected.
- **Lowest Collected Trash Count** - This is a positive reward given at each time step for the lowest collected trash count amongst all agents. The lowest trash count is scaled by $0.01$.
- **Crossed Border** - This is a negative reward of $-100$ given when the border is crossed.
- **Collided with Other Vessel** - This is a negative reward of $-100$ given when colliding with other vessel.
- **Close to Other Vessel** - This is a positive reward of $1$ given at each time-step when the distance to the other vessel is smaller than or equal to $10$.
- **Nearby Trash Count Delta** - This is a positive reward given when the nearby trash field population is higher than it has been until this time step. The reward given is the delta between the previous nearby trash field population count and the current. A nearby trash field population count is calculated by finding all floating plastic pebbles around a vessel with a radius smaller than or equal to $25$.
- **Collide with Trash** - This is a negative reward of $-1$ given when the agent-controlled vessel is colliding with a floating plastic pebble.

## Tasks

- **Main Task: Plastic Collection** - This is the main task of the environment. Goal for the agent is to accerlate and steer the plastic collection vessel to collect as many floating plastic pebbles as possible, while avoiding to crash into other vessels and crossing the environment border.
- **Subtask: Find Highest Polluted Area** - This is a subtask with the goal to find the highest trash population area in a given scenario.
- **Subtask: Group Up** - This is a subtask with the goal find other vessels and stay close to other vessels, while collecting as many floating plastic pebbles as possible.
- **Subtask: Avoid Plastic** - This is a subtask with the goal to avoid floating plastic pebbles.
