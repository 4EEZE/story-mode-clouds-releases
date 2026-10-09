# Concepts

A concept is a way of making things: the crafting grid, the furnace, Create's crushing wheels. On the memory
screen it is a galaxy, its ideas the stars round it. A concept with a station is found when one of its stations
has been in the player's hands; until then its ideas wait. A concept without a station, or one no pack names, is
known from the start.

The mod names vanilla's, Create's (with manual item application), Farmer's Delight's, Brewin' and Chewin''s
(fermenting and pouring from the keg), No Man's Land's dipping in a cauldron and Caverns & Chasms' mime. Files in `assets/<namespace>/memory/concepts/*.json`:

```json
{
  "entries": [
    {
      "type": "farmersdelight:cooking",
      "station": "farmersdelight:cooking_pot",
      "title": "Cooking in a pot",
      "text": "A little of everything, and time."
    },
    {
      "type": "farmersdelight:cutting",
      "station": ["farmersdelight:cutting_board"],
      "title": "The cutting board"
    }
  ]
}
```

| field | meaning |
|---|---|
| `type` | the recipe type's id (below) |
| `station` | an item id, `#tag`, or a list of them: what the concept is done with |
| `title` | its name (default: made from the type's id, `Sequenced Assembly`) |
| `text` | its words |
| `parts` | ways of it that need something more (below) |

## Parts

Some ways of a concept need more than its station: Create mixes some things only over a blaze burner. A part
names those recipes by fields their files have, and what it needs. Its recipes' ideas wait until the concept is
known and one of the part's stations has been in the player's hands too; then the voice speaks of the part as of a
concept. Its stations show on the concept's card, veiled until had. The mod names Create's heated and superheated
mixing and compacting:

```json
{
  "type": "create:mixing",
  "station": "create:mechanical_mixer",
  "title": "storymodeclouds.concept.mixing",
  "parts": [
    {"when": {"heat_requirement": "heated"}, "station": "create:blaze_burner", "title": "Mixing over heat"},
    {"when": {"heat_requirement": "superheated"}, "station": "create:blaze_cake", "title": "Mixing over great heat"}
  ]
}
```

| field | meaning |
|---|---|
| `when` | fields of the recipe and their values, as its file in `data/<mod>/recipe/` has them; a recipe with all of them is of the part. A field left at its default is often not written in the file, so name the ones that are |
| `station` | an item id, `#tag`, or a list of them: what the part needs |
| `title` | what the voice calls it when it is come to (default: the concept's title) |

**Finding a recipe type's id**: open the mod's jar as a zip and look at any recipe in
`data/<mod>/recipe/` -- the `"type"` field, for example `"create:crushing"`. For most mods the recipe's type and
that field are the same.

## Families

Things of one kind made alike -- swords of every material, slabs, beds -- are a family. When two or more ideas of a
family lie in one concept, they gather under one star of their own there, named with how many it holds, in a red
of its own, which opens as a folder within the concept: the view comes nearer and its ideas come out round it. Escape, drawing back, a click on the dark or
flying far comes back to the concept. One idea alone of a family lies as itself, so a netherite sword, made at the
smithing table, is never in the crafting grid's swords.

The mod names vanilla's tools, armour, boats, signs, doors, slabs, stairs, walls, wool, beds and more; and the
furniture, seats, toolboxes, sheets, knives, flags and other kinds of the mods it was made alongside (Create,
Farmer's Delight, Another Furniture, Supplementaries, Caverns & Chasms and more), and Create's and Enderscape's
stones, each read after vanilla's (`families/palettes.json`) so its slabs stay with the slabs. Files in
`assets/<namespace>/memory/families/*.json`, one entry or several under `"entries"`:

```json
{
  "entries": [
    {"items": "#c:tools/knife", "title": "Knives"},
    {"items": "#minecraft:swords", "title": "storymodeclouds.family.swords"}
  ]
}
```

| field | meaning |
|---|---|
| `items` | an item id or `#tag`: the things of the family |
| `title` | its name, a translation key or plain words |

A thing is of the first family read that names it: name the narrower first (boats with a chest before boats).
