# HIVEX: Wind Farm Control Environment

## Main Environment Features

<a href="url"><img src="https://github.com/hivex-research/hivex-environments/blob/main/docs/images/WFC_desc.jpg" width="auto" style="border-radius:10px" alt="Wind Farm Control Environment Features"></a>

## Process

<a href="url"><img src="https://github.com/hivex-research/hivex-environments/blob/main/docs/images/WFC_process.jpg" width="auto" style="border-radius:10px" alt="Wind Farm Control Environment Process"></a>

## Environment Specifications

- Episode Length: 5000
- Agent Count: 8
- Neighbour Count: 0

**Vector Observations (6)** - Stacks: 1 - Normalized: True
- Turbine Location (2)
- Turbine Direction (2)
- Wind Direction (2)

**Discrete Actions (1)**
- Branch 0 - Rotate Turbine (3):
    - 0: Do Nothing
    - 1: Rotate Left
    - 2: Rotate Right

## Rewards

- **Generate Energy** - This is a positive reward given at each time-step, in the range $[0, 1]$. This reward corresponds to the performance of each wind turbine and is being calculated as described in equation. Orienting the wind turbine against the wind yields a high reward.
- **Avoid Damage** - This is a positive reward given at each time-step, in the range $[0, 1]$. We remap the angle between the wind direction and the turbine's orientation linearly from $[0, 90]$ degrees to $[0, 1]$ reward and from $[90, 180]$ degrees to $[1, 0]$ reward. Orienting the wind turbine so that the rotor blades are parallel to the wind direction yields high reward.

## Tasks

- **Main Task: Generate Energy** - This is the main task of the environment. The agent's goal is to rotate the wind turbine to be oriented against the wind direction and hence generate energy.
- **Subtask: Avoid Damage** - This is a subtask to turn the wind turbine 90 degrees away so that the wind turbine rotor blades are parallel to the wind direction, avoiding damage to the wind turbine's rotor blades.