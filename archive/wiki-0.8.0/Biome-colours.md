# Biome colours and clouds

## Fog, sky and haze by biome

`assets/storymodeclouds/palette/biomes.json` (one file: start from a copy of the mod's):

```json
{
  "colours": {
    "minecraft:plains": {"fog": "#C9DCF0", "sky": "#86B4F0"}
  },
  "haze": {
    "minecraft:swamp": 1.6
  }
}
```

- `colours`: each biome's fog and sky colour, `#RRGGBB`. A biome not listed keeps its own.
- `haze`: how much thicker the air is in a biome, 1 being usual.

## The clouds' shape

The clouds are drawn from vanilla's own `minecraft:textures/environment/clouds.png`: a texel is cloud where it is
not transparent. A pack that replaces that texture reshapes the clouds.
