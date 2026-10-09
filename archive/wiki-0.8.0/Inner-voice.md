# Inner voice

What the inner voice says is in `assets/storymodeclouds/voice/<language>.json` (`en_us.json`, `ru_ru.json`, ...).
A pack's file replaces the mod's for that language, so start from a copy of the mod's file. A language the mod
has no file for can simply be added; English is used for anything it does not have.

```json
{
  "rain": {
    "soft": {
      "good": ["Rain.| Everything smells of earth now."],
      "neutral": ["Here comes the rain."],
      "bad": ["Rain as well.| Of course."]
    },
    "rough": {
      "neutral": ["Wet again."]
    }
  }
}
```

- The top keys are the moments (`rain`, `sunrise`, `hunger`, `ideacome`, `research`, ...): the list is the
  mod's own file.
- `soft` and `rough` are the two voices a player can choose; `good`, `neutral` and `bad` the moods. A mood
  without lines falls back to `neutral`.
- `|` splits a line into two beats, with a short pause between them.
- `{name}` is the place, player, thing or idea the moment is about, where it has one.

How often each moment is said is in the mod's config, Voice section.
