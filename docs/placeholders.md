# Placeholders

Placeholders are tokens written in a text line that get replaced with live values. They are written as `{name}`, and some take arguments as `{name:arg}`. Unknown tokens are left untouched, so a typo shows the literal `{token}` rather than breaking the line.

Holograms containing placeholders refresh automatically on a timer. See **update interval** in [Display Settings](display-settings.md).

## Built-in placeholders

| Placeholder | Resolves to |
|-------------|-------------|
| `{player}` | The viewing player's name |
| `{online}` | Number of players currently online |
| `{time}` | Current time, `HH:mm` |
| `{date}` | Current date, `yyyy-MM-dd` |
| `{world}` | A short identifier of the viewing player's world |
| `{uuid}` | The viewing player's UUID |
| `{top:...}` | Leaderboard values (see [Leaderboards](leaderboards.md)) |

`{player}`, `{world}`, and `{uuid}` are **per-viewer**: each player sees their own value in the same hologram.

## Position placeholders (actions only)

These resolve to the interacting player's rounded coordinates and only work inside [interaction action](interactions.md) commands, **not** in display text:

| Placeholder | Resolves to |
|-------------|-------------|
| `{x}` | Player's X (rounded) |
| `{y}` | Player's Y (rounded) |
| `{z}` | Player's Z (rounded) |

In display text these are left as literal `{x}`, `{y}`, `{z}`. A typical use is an action command:

```
tp {player} {x} {y} {z}
```

## Level-plugin placeholders

Available when the matching plugin is installed (see [Integrations](integrations.md)). All are per-viewer and show `?` if the value cannot be read.

**EndlessLeveling**

| Placeholder | Resolves to |
|-------------|-------------|
| `{el_level}` | Player level |
| `{el_xp}` | Player XP |
| `{el_class}` | Primary class (`None` if unclassed) |
| `{el_prestige}` | Prestige level |

**RPGLeveling**

| Placeholder | Resolves to |
|-------------|-------------|
| `{rpg_level}` | Player level |
| `{rpg_xp}` | Player XP |
| `{rpg_class}` | Class name (`None` if unclassed) |
| `{rpg_class_tier}` | Class tier |

## PlaceholderAPI

If [PlaceholderAPI](integrations.md) is installed, you can also use its `%token%` placeholders anywhere in hologram text. They resolve per-viewer. ScuffedHolograms resolves its own `{...}` tokens first, then hands the text to PlaceholderAPI for any `%...%` tokens.

```
Welcome, {player}! Balance: %vault_eco_balance%
```
