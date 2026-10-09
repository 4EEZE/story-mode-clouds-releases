# Ideas

An idea is a thing the player could make. It comes once about half of a recipe's ingredients have been in the
player's hands, and becomes understood when all of them have been (half, for recipes of four or more), or when
the thing is made. Every recipe the game knows can become an idea; nothing has to be written for that.

Files in `assets/<namespace>/memory/ideas/*.json` change single things. One entry per file, or several:

```json
{
  "entries": [
    {"item": "minecraft:debug_stick", "hidden": true},
    {"item": "#c:music_discs", "hidden": true},
    {
      "item": "minecraft:lead",
      "title": "Something to keep animals close",
      "text": "A knot and something sticky...",
      "known": "Now I can lead them anywhere."
    }
  ]
}
```

| field | meaning |
|---|---|
| `item` | an item id, or `#tag` for every item in a tag |
| `hidden` | `true`: never an idea (its recipes still work) |
| `title` | the idea's name while it is not understood (default: "Something with ...") |
| `text` | its words while not understood |
| `known` | its words once understood |

Settings that shape all ideas (how much must be seen, how many come at once) are in the mod's config,
Nostalgia section.
