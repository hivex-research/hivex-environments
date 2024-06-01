# HIVEX: Environments

## Available Environments

| Thumbnail | Title | Tag | Tasks | Difficulty Levels |
| --- | --- | --- | --- | --- |
| <a href="https://github.com/hivex-research/hivex-environments/master/environments/Hivex_WindFarmControl/"><img src="https://github.com/hivex-research/hivex/master/docs/images/WindFarmControl_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Wind Farm Control"></a> | Wind Farm Control | <code>WindFarmControl</code> | 2 | 9 |
| <a href="https://github.com/hivex-research/hivex-environments/master/environments/Hivex_WilfireResourceManagement/"><img src="https://github.com/hivex-research/hivex/master/docs/images/WildfireResourceManagement_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Wildfire Resource Management"></a> | Wildfire Resource Management | <code>WildfireResourceManagement</code> | 3 | 10 |
| <a href="https://github.com/hivex-research/hivex-environments/master/environments/Hivex_DroneBasedReforestation/"><img src="https://github.com/hivex-research/hivex/master/docs/images/DroneBasedReforestation_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Drone-Based Reforestation"></a> | Drone-Based Reforestation |<code>DroneBasedReforestation</code> | 7 | 10 |
| <a href="https://github.com/hivex-research/hivex-environments/master/environments/Hivex_OceanPlasticCollection/"><img src="https://github.com/hivex-research/hivex/master/docs/images/OceanPlasticCollection_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Ocean Plastic Collection"></a> | Ocean Plastic Collection | <code>OceanPlasticCollection</code> | 4 | - |
| <a href="https://github.com/hivex-research/hivex-environments/master/environments/Hivex_AerialWildfireSuppression/"><img src="https://github.com/hivex-research/hivex/master/docs/images/AerialWildfireSuppression_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Aerial Wildfire Suppression"></a> | Aerial Wildfire Suppression | <code>AerialWildFireSuppression</code> | 9 | 10 |

## How to use the registry (optional):

https://unity-technologies.github.io/ml-agents/Unity-Environment-Registry/

```python
from mlagents_envs.registry import UnityEnvRegistry

registry = UnityEnvRegistry()
registry.register_from_yaml("https://raw.githubusercontent.com/hivex-research/hivex-environments/master/hivex_environment_registry.yaml")
# Available tags are:
# WindFarmControl, WildfireResourceManagement, DroneBasedReforestation, OceanPlasticCollection, AerialWildFireSuppression
env = registry["environment_tag"].make()
```