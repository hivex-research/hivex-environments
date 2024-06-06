# HIVEX: Drone-Based Reforestation Environment

## Main Environment Features

<a href="url"><img src="https://github.com/hivex-research/hivex-environments/blob/main/docs/images/DBR_desc.jpg" width="auto" style="border-radius:10px" alt="Drone-Based Reforestation Environment Features"></a>

## Process

<a href="url"><img src="https://github.com/hivex-research/hivex-environments/blob/main/docs/images/DBR_process.jpg" width="auto" style="border-radius:10px" alt="Drone-Based Reforestation Environment Process"></a>

## Environment Specifications

- Episode Length: $2000$
- Agent Count: $3$
- Neighbour Count: $0$

**Vector Observations (10)** - Stacks: 2 - Normalized: True
- Distance to Ground (1)
- Local Position (3)
- Direction (3)
- Drone Station Height (1)
- Holding Seed (1)
- Energy Level (1)

**Visual Observations (16, 16, 1)** - Stacks: 1 - Normalized: True
- Downward Pointing Camera in Grayscale (256)

**Continous Actions (3)**
- Throttel (1)
- Steer (1)
- Up / Down (1)

**Discrete Actions (1)**
- Branch 0 - Drop Seed (2):
    - 0: Do Nothing
    - 1: Drop Seed

## Rewards

- **Drop Seed** This is a positive reward given at each seed drop. The drop seed reward consists of the quality of drop location, a seed reward, in the range of $[0, 20]$ and distance to other seeds and existing trees, a distance reward, in the range of $[0, 10]$. Therefor the resulting total drop seed reward is in the range of $[0, 30]$.
- **Deplete Energy Holding Seed** This is a negative reward of $-1 / ({episode length} / 2)$ given at each time step if the drone is carrying a seed. The deplete energy reward at each time-step is higher when carrying a seed than if not carrying a seed. The episode length is $2000$.
- **Deplete Energy No Seed** This is a negative reward of $-1 / ({episode length})$ given at each time step if the drone is not carrying a seed. The episode length is $2000$.
- **Pick-up Seed** This is an optional positive reward given when a drone is returned to the drone station. There are two tasks in which this reward is given. In "Subtask: Pick-up Seed at Base" a reward of $100$ is given and in "Subtask: Explore Furthest Distance and Return to Base" the reward is the furthest distance that has been explored and can be in the range of $[0, 200]$.
- **Incremental Running Back** After a seed has been dropped, this reward is given incrementally when flying back to the drone station. If the distance to the drone station at time-step $t_{-1}$ is larger than the current distance, this reward is given at incremental steps of $2.5$. The range of the incremental running back reward is $[0, 20]$, which can be modified by the running back multiplier, depending on the seed drop quality. If the Seed has been dropped 50 meters away from the drone station, an incremental running back reward can be received $20$ times.
- **Group-up** This is a positive reward of $10$, given at each time-step, if the distance to any neighbouring drone is smaller than $5$.
- **High Fertility Location Delta** This is a reward given every time a higher fertility potential seed drop location has been found. The reward is the delta between the old and the new potential, if the new potential is higher than the old. The range of the reward is $[0, 1]$.
- **High Landscape Point Delta** This is a reward given every time a higher point on the terrain landscape has been found. The reward is the delta between the old and the new height, if the new height is higher than the old. The reward range is $[0, 40]$, as $40$ is the environment's height boundary.
- **Far Distance Explored Delta** This is a reward given every time a further distance has been explored. The reward is the delta between the old distance and the new, if the new distance is further than the old. The reward range is $[0, 200]$, as $200$ is the environment's half extend.
- **Find Close Tree** This is a reward given when a tree has been found within a $20$ meter radius. The reward given is $100$. The steps to calculate the find close tree reward can be found in Equation \ref{DBR:eq:11}.

## Tasks

- **Main Task: Maximize Collective Planted Tree Count** - This is the main task of the environment. The goal for the agent is to pick up a seed and re-charge batteries at the drone station, explore to find fertile ground for the seed, that is, a location that is close to existing trees, and drop the seed while maintaining enough battery charge to return to the drone station.
- **Subtask: Find Closest Forest Perimeter** - This is a subtask with the goal of finding the closest forest perimeter.
- **Subtask: Group-up with Other Drones** - This is a subtask with the goal of grouping up with other drones and planting seeds.
- **Subtask: Pick-up Seed at Base** - This is a subtask with the goal of going back to the drone station, picking up a seed, and recharging the battery. In this subtask, the initial position of drones is random instead of at the drone station.
- **Subtask: Drop Seed** - This is a subtask with the goal of finding the most fertile soil and dropping a seed.
- **Subtask: Find Highest Potential Seed Drop Location** - This is a subtask with the goal of finding soil with the highest fertility.
- **Subtask: Find Highest Point on Landscape** - This is a subtask with the goal of finding the highest point on the landscape.
- **Subtask: Explore Furthest Distance and Return to Base** - This is a subtask with the goal of exploring the furthest from the drone station and returning.