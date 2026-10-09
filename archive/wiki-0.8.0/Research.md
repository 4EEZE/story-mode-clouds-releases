# Research

Research notes lie on the layer below the memories. The game writes one for each thing found out:

- a creature first met (in sight, within 16 blocks), and later first defeated;
- a biome first come to;
- a block first dug out -- only the blocks a pack names; the built-in pack names the ores (`#c:ores`, and
  Enderscape's and Darker Depths' that it leaves out).

The built-in pack has words for the creatures and places of Caverns & Chasms, Darker Depths, Enderscape and No
Man's Land, and a few others.

Files in `assets/<namespace>/memory/research/*.json`, one entry or several under `"entries"`:

```json
{
  "entries": [
    {"block": "minecraft:amethyst_cluster"},
    {"block": "#minecraft:logs", "text": "Wood. Everything starts here."},
    {"entity": "minecraft:warden", "title": "The thing in the dark", "text": "It hears everything."},
    {"biome": "minecraft:the_void", "hidden": true}
  ]
}
```

| field | meaning |
|---|---|
| `entity`, `biome`, `block` | what the entry is about: an id, or `#tag` |
| `hidden` | `true`: never noted |
| `title` | the note's name (default: the thing's own name) |
| `text` | words put before what was found out |

Naming a `block` is what makes digging it out research. Structures cannot be noticed by a client-only mod.
