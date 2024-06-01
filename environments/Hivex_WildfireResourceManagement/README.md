# HIVEX: Wildfire Resource Management Environment

## Main Environment Features

<a href="url"><img src="https://github/com/hivex-research/hivex-environments/master/docs/images/WRM_desc.jpg" width="auto" style="border-radius:10px" alt="Wildfire Resource Management Environment Features"></a>

## Process

<a href="url"><img src="https://github/com/hivex-research/hivex-environments/master/docs/images/WRM_process.jpg" width="auto" style="border-radius:10px" alt="Wildfire Resource Management Environment Process"></a>

## Environment Specifications

- Episode Length: 500
- Agent Count: 9
- Neighbour Count: 3

**Vector Observations (8)** - Stacks: 2 - Normalized: True
- Closest Fire Location (3)
- Temperature (1)
- Humidity (1)
- Overcast (1)
- Total Support (1)

**Discrete Actions (4)**
- Branch 0 - Add/Sub Resource (3):
    - 0: Do Nothing
    - 1: Add to Self
    - 2: Sub from Self
- Branch 1 - Add/Sub Resource (3):
    - 0: Do Nothing
    - 1: Add to Neighbour 1
    - 2: Sub from Neighbour 1
- Branch 2 - Add/Sub Resource (3):
    - 0: Do Nothing
    - 1: Add to Neighbour 2
    - 2: Sub from Neighbour 2
- Branch 3 - Add/Sub Resource (3):
    - 0: Do Nothing
    - 1: Add to Neighbour 3
    - 2: Sub from Neighbour 3

## Rewards

- **Watch Tower Performance** - This is a positive reward given at each time step, corresponding to the performance of the agent-controlled watch tower only. This reward is weighted by the resources distributed by self to self.
- **Neighbour Performance** This is a positive reward given at each time step, corresponding to the sum of the performance of the neighbouring agent-controlled watch towers. This reward is weighted by the resources distributed by self to neighbouring watch towers.
- **Collective Performance** - This is a positive reward given at each time step, corresponding to the sum of the performance of all agent-controlled watch towers.

## Tasks

- **Main Task: Distribute Resources** - This is the main task of the environment. Goal of the agent is to distribute a total of 1.0 resources at each time-step to self or neighbouring watch towers. If the agent is out of resource it has to remove resources from self or neighbouring watch towers before re-distribution. The resources should be distributed to the watch towers where fire is closest and incoming.
- **Subtask: Distribute All** - This is a subtask with the same goal as the main task, however distributing resources to neighbouring watch towers yields higher rewards than distributing them to self.
- **Subtask: Keep All** - This is a subtask with the same goal as the main task, however distributing resources to self yields higher rewards than distributing them to neighbouring watch towers.