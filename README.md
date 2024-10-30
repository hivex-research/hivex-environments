# HIVEX: Environments

## Available Environments

| Thumbnail | Title | Tag | Tasks | Difficulty Levels |
| --- | --- | --- | --- | --- |
| <a href="https://github.com/hivex-research/hivex-environments/blob/main/environments/Hivex_WindFarmControl/"><img src="https://github.com/hivex-research/hivex/blob/main/docs/images/WFC_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Wind Farm Control"></a> | Wind Farm Control | <code>WindFarmControl</code> | <code>2</code> | <code>9</code> |
| <a href="https://github.com/hivex-research/hivex-environments/blob/main/environments/Hivex_WilfireResourceManagement/"><img src="https://github.com/hivex-research/hivex/blob/main/docs/images/WRM_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Wildfire Resource Management"></a> | Wildfire Resource Management | <code>WildfireResourceManagement</code> | <code>3</code> | <code>10</code> |
| <a href="https://github.com/hivex-research/hivex-environments/blob/main/environments/Hivex_DroneBasedReforestation/"><img src="https://github.com/hivex-research/hivex/blob/main/docs/images/DBR_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Drone-Based Reforestation"></a> | Drone-Based Reforestation |<code>DroneBasedReforestation</code> | <code>7</code> | <code>10</code> |
| <a href="https://github.com/hivex-research/hivex-environments/blob/main/environments/Hivex_OceanPlasticCollection/"><img src="https://github.com/hivex-research/hivex/blob/main/docs/images/OPC_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Ocean Plastic Collection"></a> | Ocean Plastic Collection | <code>OceanPlasticCollection</code> | <code>4</code> | <code>-</code> |
| <a href="https://github.com/hivex-research/hivex-environments/blob/main/environments/Hivex_AerialWildfireSuppression/"><img src="https://github.com/hivex-research/hivex/blob/main/docs/images/AWS_thumb.jpg" height="auto" width="300" style="border-radius:10px" alt="Aerial Wildfire Suppression"></a> | Aerial Wildfire Suppression | <code>AerialWildFireSuppression</code> | <code>9</code> | <code>10</code> |

## How to use the registry (optional):

https://unity-technologies.github.io/ml-agents/Unity-Environment-Registry/

```python
from mlagents_envs.registry import UnityEnvRegistry

registry = UnityEnvRegistry()
registry.register_from_yaml("https://raw.githubusercontent.com/hivex-research/hivex-environments/main/hivex_environment_registry.yaml")
# Available tags are:
# WindFarmControl, WildfireResourceManagement, DroneBasedReforestation, OceanPlasticCollection, AerialWildFireSuppression
env = registry["environment_tag"].make()
```
