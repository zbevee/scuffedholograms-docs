# Display Settings

Every hologram has a **Settings** tab in the edit GUI that controls how it looks and behaves. This page is a reference for those options. Defaults are listed so you know what you get without changing anything.

## Orientation

| Setting | Options / default | Effect |
|---------|-------------------|--------|
| **Billboard** | Center *(default)*, Fixed, Horizontal | How the hologram rotates relative to the viewer |
| **Yaw** | degrees, default 0 | Facing direction, used in **Fixed** mode |
| **Pitch** | degrees, default 0 | Tilt, used in **Fixed** mode |

Billboard modes:

- **Center** always turns to face each viewer's camera. Best for text and signs that should be readable from anywhere.
- **Fixed** does not rotate. It stays at the Yaw and Pitch you set. Best for images and decorations placed flat on a wall or floor. Image holograms in Fixed mode are readable from both front and back.
- **Horizontal** turns to face the viewer but only around the vertical axis, so it always stays upright.

Size and spacing are not on this tab. They are set in each hologram's content editor (text scale and line spacing for text holograms, scale for image, model, and particle holograms). See [Creating & Editing](creating-holograms.md).

## Visibility

| Setting | Default | Effect |
|---------|---------|--------|
| **View distance** | 80 | Maximum distance in blocks at which the hologram is visible |
| **Update interval** | 600 ticks | How often dynamic content refreshes (see below) |
| **Schedule** | off | Show the hologram only during a time-of-day window |

### Update interval

Controls how often a hologram re-renders its dynamic content: [placeholders](placeholders.md), [leaderboards](leaderboards.md), and text animations. It is entered in **ticks**, and the hologram updates **5 times per second** (1 tick = 0.2 seconds).

- Default: **600 ticks**, which is **120 seconds** (2 minutes).
- Range: **20 to 6000 ticks** (4 seconds to 20 minutes).

Lower it for clocks and leaderboards that should update often, and raise it for static text to save resources. A hologram with no placeholders ignores this setting.

### Schedule

When enabled, set a **start hour** and **end hour** from 0 to 24. The hologram is only visible while the world's time is inside that window. Wrap-around is supported: for example, start `22` and end `4` makes it visible from 22:00 to 03:59. The full `0` to `24` window means "always visible".

## Ambient light

A hologram can emit real light into the world, set at the bottom of the Settings tab:

| Setting | Default | Effect |
|---------|---------|--------|
| **Light colour** | off | A hex colour the hologram casts into its surroundings |
| **Light radius** | 5 (range 0 to 15) | How far the light reaches |

Set a light colour to turn a hologram into a coloured light source, which is useful for signs in dark areas. Use **Clear** to turn it back off.

## World map marker

A hologram can place a marker on the in-game world map:

| Setting | Default | Effect |
|---------|---------|--------|
| **Map marker** | off | Show this hologram on the world map |
| **Marker icon** | a default pin | Which marker icon to use |
| **Marker label** | hologram's name | Text shown next to the marker |

Use this to put points of interest such as spawn, shops, and dungeons on the map.

## Interaction sound

A hologram can play a sound when interacted with. This is set on the **Triggers + Permissions** tab. See [Interactions & Actions](interactions.md).

---

> The edit GUI is available in many languages and follows the client's language automatically.
