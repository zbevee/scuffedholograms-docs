# Creating & Editing Holograms

Everything is done in-game. There are no config files to edit. You manage holograms two ways:

- **The management GUI** with `/sch menu`
- **The Hologram Tool** with `/sch tool`

Both require admin access ([Permissions](permissions.md)).

## The management menu

`/sch menu` opens a menu with three sections.

### Holograms

The main section. Here you can:

- **Search** your holograms by name.
- **Create** a new hologram with the create buttons: **New Text**, **New Image**, **New Model**, **New Particle**, or **New Leaderboard**. The new hologram appears at your location and its editor opens. **New Leaderboard** inserts a ready-made [leaderboard](leaderboards.md) you can edit; the others give you an empty hologram of that type.
- **Edit**, **Copy** (duplicate), or **Delete** any hologram in the list. The list is paginated, so use Prev and Next.
- **Organise** holograms into **folders**. Make a New Folder, select holograms with their checkbox, and move them in or out. Folders only keep a large list tidy.

### Combat Text

Customises the game's damage numbers server-wide. See [Combat Text](combat-text.md).

### Settings

- **Language** sets the GUI language.
- **Debug Logging** toggles extra logging for troubleshooting.
- **Import All** imports holograms from other plugins ([Importing](importing.md)).
- **Give me one** gives you the Hologram Tool.
- **Reload** reloads holograms and assets.

## Editing each type

Each hologram is one of four kinds, set by the create button you used. The edit page shows the controls for that kind.

### Text holograms

A text hologram is a stack of **lines** that you add, edit, reorder, duplicate, and remove. A line is either a line of text or a **spacer** (an empty gap of adjustable height used to separate text). For each text line you can:

- Type the text, with [placeholders](placeholders.md) such as `{player}` and `{online}`.
- Pick a **font**.
- Colour it with the **Colour Segments** tool (see [Styling Text](text-formatting.md)).
- Choose an **animation** (None, Scroll, Typewriter, or Rainbow).
- Set up **variants**.

The text panel also sets the hologram's overall **text scale** and **line spacing**.

#### Text variants

A text line can **rotate** between several different texts. Turn variants on, add two or more entries, and set a rotation interval in seconds. The line cycles through them on that interval, and every player sees the same variant at the same time.

#### Advanced: rendering options

A text hologram has two advanced toggles you can usually leave alone:

- **Mode**: **Glyph** (default) draws fully styled, coloured text. **Nameplate** draws plain text with no styling, the lightest option.
- **Renderer**: **Particle** (default) looks the sharpest. **Entity** is lighter where many players gather in one spot, so switch to it for busy hubs and crowded areas.

### Image holograms

An image hologram shows a single uploaded image or GIF. Pick the image and set its scale and sharp-edges option. See [Images & GIFs](images-and-gifs.md).

### Model holograms

A model hologram shows a single 3D model. Type the model's asset ID and set its scale. There is a **Mannequin** preset for a quick humanoid model. Use the in-game asset editor to find model IDs.

### Particle holograms

A particle hologram shows a single particle effect. See [Particle Effects](particle-effects.md).

## Positioning with the Hologram Tool

`/sch tool` (or **Give me one** in the menu) gives you the **Hologram Tool**. Hold it and its controls appear on screen. Aim at a hologram within about 25 blocks and use these controls:

| Control | Action |
|---------|--------|
| **Primary action** | **Grab and release.** Pick the hologram up and it follows your aim, snapping to a **0.5-block grid**. Use it again to drop the hologram in place. |
| **Secondary action** | **Delete** the held hologram. Press once to arm, then again within 2 seconds to confirm. |
| **Ability 1 / Ability 2** | **Rotate** left and right (yaw, in 15-degree steps) |
| **Ability 3 / Interact** | **Tilt** up and down (pitch) |
| **Pick Block** | **Toggle billboard mode** |

The on-screen legend shows your actual key bindings for each of these. To open a held hologram's edit page, run `/sch menu` while grabbing it.

## Fine positioning in the GUI

The edit page also lets you nudge a hologram along X, Y, and Z in small 0.1-block steps, or teleport it to your current position. This is best for precise adjustments after rough-placing with the tool.

---

> The management GUI is translated into many languages and automatically follows each admin's client language.
