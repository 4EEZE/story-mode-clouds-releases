# Kinds of note

Every note on the memory screen is of a kind: memory, experiment, idea, concept, research. A kind is one file,
`assets/<namespace>/memory/kinds/<id>.json`; its id is `<namespace>:<id>`.

```json
{
  "name": "mypack.memory.kind.dream",
  "plural": "mypack.memory.kind.dream.plural",
  "colour": "#9FB8FF",
  "player": true,
  "order": 5,
  "layer": 0
}
```

| field | meaning |
|---|---|
| `name`, `plural` | translation keys (or words) for one note and several |
| `colour` | `#RRGGBB`: the note's star and its threads |
| `player` | `true`: the player writes notes of this kind (right click the dark). `false`: only the game does, and such notes fade by themselves when long unlooked-at |
| `order` | where it comes in lists, smaller first |
| `layer` | which layer of the screen it lies on: 0 is the top (memories, notes, concepts); 1 is below it (research). Default: 0 for player kinds, 1 for the others |

**Recolour or move a built-in kind**: a file at the same path in your pack, under the mod's namespace, wins:
`assets/storymodeclouds/memory/kinds/research.json`. The built-in ids are `memory`, `experiment`, `idea`,
`concept`, `research`.
