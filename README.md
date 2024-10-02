# HIVEX: Environments

## Available Environments

| Thumbnail                                                                                                                                   | Title                        | Tag                                     | Tasks          | Difficulty Levels |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- | --------------------------------------- | -------------- | ----------------- |
| <a href="[ANONYMIZED]"><img src="[ANONYMIZED]" height="auto" width="300" style="border-radius:10px" alt="Wind Farm Control"></a>            | Wind Farm Control            | <code>WindFarmControl</code>            | <code>2</code> | <code>9</code>    |
| <a href="[ANONYMIZED]"><img src="[ANONYMIZED]" height="auto" width="300" style="border-radius:10px" alt="Wildfire Resource Management"></a> | Wildfire Resource Management | <code>WildfireResourceManagement</code> | <code>3</code> | <code>10</code>   |
| <a href="[ANONYMIZED]"><img src="[ANONYMIZED]" height="auto" width="300" style="border-radius:10px" alt="Drone-Based Reforestation"></a>    | Drone-Based Reforestation    | <code>DroneBasedReforestation</code>    | <code>7</code> | <code>10</code>   |
| <a href="[ANONYMIZED]"><img src="[ANONYMIZED]" height="auto" width="300" style="border-radius:10px" alt="Ocean Plastic Collection"></a>     | Ocean Plastic Collection     | <code>OceanPlasticCollection</code>     | <code>4</code> | <code>-</code>    |
| <a href="[ANONYMIZED]"><img src="[ANONYMIZED]" height="auto" width="300" style="border-radius:10px" alt="Aerial Wildfire Suppression"></a>  | Aerial Wildfire Suppression  | <code>AerialWildFireSuppression</code>  | <code>9</code> | <code>10</code>   |

## How to use the registry (optional):

https://unity-technologies.github.io/ml-agents/Unity-Environment-Registry/

```python
from mlagents_envs.registry import UnityEnvRegistry

registry = UnityEnvRegistry()
registry.register_from_yaml("[ANONYMIZED]")
# Available tags are:
# WindFarmControl, WildfireResourceManagement, DroneBasedReforestation, OceanPlasticCollection, AerialWildFireSuppression
env = registry["environment_tag"].make()
```
