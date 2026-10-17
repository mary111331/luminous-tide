# Luminous Tide

Hallucinations of Love, by the sea. A beach at sunset that turns to night, and you can walk all of it: a campfire to sit by, a cave in the cliff with two stone beds, glowing crystals and glow-worms, a little waterfall with a pool, and dunes with grass moving in the wind. Over the sea, three poems circle on rings of lines that keep drifting across each other: **Echoes of the Void**, **Hallucinations of Love**, and **Bioluminescence**.

Open it: https://mary111331.github.io/luminous-tide/

- Phone: left thumb on the left side walks (up goes forward, sideways turns, all the way out runs). Drag on the right side to look, pinch to look closer.
- Laptop: W A S D or the arrow keys, Shift to run, drag to look, scroll to zoom, E to use the button that appears near things.
- Near the fire, the beds, the crystals, the waterfall or the surf, a button appears: sit by the fire and put a log on, lie down on a stone bed and watch the glow-worms, touch the glowing stones.
- Places jumps to the campfire, the shore, the waterfall, the cave or the dunes, or turns you toward a poem.
- Tap a line in the sky to read it; tap a poem's title to read the whole poem. Tap the water and it lights up; wade into the surf and your steps light it.
- The Night button turns sunset into night. Sound (surf, fire, waterfall) is off until you tap it.

## How it's made

Python builds the page (`build/build.py`):

- `poems.py` reads the two original poems from the saved notes in `build/sources/`, parses struck-through lines, system flags and stanza breaks, and checks every line shown in the sky against the original, word for word.
- `textures.py` uses numpy and Pillow to make the tileable noise for the clouds, waves, foam, flames and waterfall, the sand ripple normal map, the glow, and the butterfly.
- Everything is inlined into one `index.html`.

The browser then draws the scene live with WebGL (three.js and custom shaders): Gerstner waves, sky reflections and sun glitter, foam and surf that run up the sand, clouds, stars and the Milky Way, a lighthouse, bioluminescence at night, light motes and butterflies. The cliff, cave, rocks and driftwood share one lit shader with the sun, the moon, the flickering campfire light and the cave glow; the flames, sparks, waterfall, pool and grass are animated in their own shaders. The source of the scene is `build/app.js`.

Rebuild: `cd build && python3 build.py`
