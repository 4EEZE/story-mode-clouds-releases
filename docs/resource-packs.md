# Resource packs for Elsewhen

Use an ordinary Minecraft 1.21.1 resource pack (`pack_format: 34`). Enable it in Options → Resource Packs;
F3+T reloads it. The mod id and resource namespace remain `storymodeclouds`.

## Recipe discovery stations

Files under `assets/<namespace>/memory/concepts/*.json` specify stations required for recipe discovery.
The legacy path remains supported even though the memory screen is shelved. A file contains one rule or an
`entries` array. For an identical resource path the higher pack replaces the whole file; the first loaded
rule for a recipe type wins. Override a built-in rule at its original `assets/storymodeclouds/` path.
The built-in **Elsewhen: recipe discovery** pack stays at the bottom of the pack list.

```json
{
  "entries": [
    {
      "type": "create:mixing",
      "station": "create:mechanical_mixer",
      "parts": [
        {"when": {"heat_requirement": "heated"}, "station": "create:blaze_burner"},
        {"when": {"heat_requirement": "superheated"}, "station": "create:blaze_cake"}
      ]
    }
  ]
}
```

- `type`: the recipe type's registered ID.
- `station`: an item ID, `#item_tag`, or a list of alternatives. Any seen or known alternative satisfies it.
  No station requirement, or no rule for the type, means no station gate.
- `parts`: additional requirements for a subset of recipes. `when` matches every listed top-level primitive
  field of the recipe's serialized form. The recipe needs both its main station and the matching part's
  station. If multiple parts match, the first wins.

Titles and note descriptions are ignored. `memory/kinds`, `memory/ideas`, `memory/research` and
`memory/families` are shelved and are not loaded. Stations gate discovery from ingredients; actually
crafting an item always teaches its recipes. JEI/EMI discovery can be disabled in settings (K), under
**Nostalgia → Recipe discovery**. Existing progress is retained.

## Mod panels, slots and buttons

Enable **Interface → Mods' Screens in the Pack's Look**. It is off by default; exclude individual mods
with its exclusion list. Elsewhen reads the active pack's standard container and button textures,
including button scaling metadata. Panel grain repeats at its native size, large slot interiors repeat
within their fixed edges, and ordinary mod buttons and Create's button backgrounds use pack sprites.
Standard furnace-shaped progress arrows also use the active pack's furnace background and
`container/furnace/burn_progress` sprite, with cropped progress preserved. Slightly different slot shades
and rounded tank contours are recognised, while enclosed icons and tiny decorative marks retain their art.
Coloured artwork and separately drawn icons retain their own textures. Custom renderers that do not use
these supported drawing paths may keep their original appearance.

Vintage is a separate resource pack and is not included in Elsewhen. Any compatible active pack can
supply the textures.

## Inner voice and biome colours

- [Inner voice](inner-voice.md): replace or add `assets/storymodeclouds/voice/<language>.json`.
- [Biome colours](biome-colours.md): replace `assets/storymodeclouds/palette/biomes.json`.

Whole-file replacements start from the corresponding file in the mod JAR. The prototype wiki is archived;
its memory formats are not an active API in this version.
