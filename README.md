# Luminous Tide

Hallucinations of Love, by the sea. A beach at sunset that turns to night, with three poems drifting in slow golden-angle spirals over the water: **Echoes of the Void**, **Hallucinations of Love**, and a new one, **Bioluminescence**.

Open it: https://mary111331.github.io/luminous-tide/

- Drag to look around, pinch or scroll to look closer.
- Tap a line in the sky to read it; tap a poem's title to read the whole poem.
- Tap the water and it lights up.
- The button at the top turns sunset into night. Sound is off until you tap it.

## How it's made

Python builds the page (`build/build.py`):

- `poems.py` reads the two original poems from the saved notes in `build/sources/`, parses struck-through lines, system flags and stanza breaks, and checks every line shown in the sky against the original, word for word.
- `textures.py` uses numpy and Pillow to make the tileable noise for the clouds, waves and foam, the sand ripple normal map, the glow, and the butterfly.
- Everything is inlined into one `index.html`.

The browser then draws the scene live with WebGL (three.js and custom shaders): Gerstner waves, sky reflections and sun glitter, foam and surf that run up the sand, clouds, stars and the Milky Way, a lighthouse, bioluminescence at night, light motes and butterflies spiralling up toward the poems.

Rebuild: `cd build && python3 build.py`
