# Particle Effects

A **particle-effect hologram** anchors a particle effect at a location in the world, such as a portal swirl, a fire, sparkles, or a magic aura. It has no text or image lines. The effect itself is the hologram.

## Creating one

In the management GUI, create a particle-effect hologram and choose an effect. A **search box** filters the list, which holds **every particle effect registered on your server**: all of Hytale's built-in effects, plus any added by other installed plugins or data packs. Type part of a name (for example Fire, Portal, or Magic) and pick from the dropdown.

## Options

| Setting | Effect |
|---------|--------|
| **Effect** | Which particle system to display |
| **Size** | Scale of the effect |
| **Colour tint** | Tints the effect a colour. The result depends on the effect, since the tint blends with the effect's own colours. |
| **Respawn interval** | How often the effect restarts, in seconds. Leave it at the default (auto) to match the effect's natural duration, or set a value to force a specific loop. The minimum is 0.5 seconds. |

Because the effect list is read from your server's installed assets, the exact effects available depend on your Hytale version and which other plugins you run. Open the dropdown in-game to see your full list.

## Positioning and other settings

Particle-effect holograms are positioned with the [Hologram Tool](creating-holograms.md) and the GUI nudges like any other hologram. They can also use [interaction actions](interactions.md), for example a clickable glowing portal that teleports the player.
