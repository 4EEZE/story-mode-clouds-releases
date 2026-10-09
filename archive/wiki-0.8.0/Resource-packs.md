# Resource packs

A pack for this mod is an ordinary Minecraft 1.21.1 resource pack:

```
my-pack/
  pack.mcmeta
  assets/
    storymodeclouds/          the mod's own files: voice lines, biome colours
      lang/en_us.json         your translation keys, if you use any
    mypack/                   your own namespace, for memory data
      memory/
        kinds/*.json
        ideas/*.json
        research/*.json
        concepts/*.json
      lang/en_us.json
```

`pack.mcmeta`:

```json
{
  "pack": {
    "pack_format": 34,
    "description": "My memories"
  }
}
```

Put the folder (or a zip of it) in `resourcepacks/`, turn it on in Options -> Resource Packs, and press F3+T after
each change.

## Which pack wins

- **A file at the same path** in two packs: the higher pack's file is used whole. The mod's voice lines and biome
  colours are one file each, so a pack that changes them starts from a copy of the mod's file (open the mod's
  jar as a zip; they are under `assets/storymodeclouds/`).
- **Memory data** (`memory/kinds`, `ideas`, `research`, `concepts`) is read from every file in every pack, so
  adding is just adding a file. For the same thing named twice, the first one read is used.
- The mod's own memory data comes in a built-in pack, **Elsewhen: memory**, always on and at the bottom:
  any pack you add is above it.

## Words

Wherever a file has a `title`, `text`, `name` or `known`, it can be a translation key (`mypack.idea.lead`, with
the words in `assets/mypack/lang/<language>.json`) or plain words. Plain words are the same in every language.
