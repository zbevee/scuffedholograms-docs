# Leaderboards

A leaderboard hologram is a text hologram that uses `{top:...}` placeholders. Each token shows one entry of a ranked list, so you build a leaderboard by stacking lines.

> **Quick start:** the **New Leaderboard** button in `/sch menu` drops in a ready-made top-10 board (ranked by prestige and level) that you can edit. To rank by something else, change the stat name in its `{top}` placeholders as described below.

## The `{top}` placeholder

```
{top:<stat>:<rank>}
{top:<stat>:<rank>:<field>}
```

- `<stat>` is which ranking to read (see [Tracked stats](#tracked-stats)).
- `<rank>` is the position, starting at `1` for first place.
- `<field>` is optional, and sets what to show for that entry:
  - *(omitted)*: the player's **name**
  - `value`: the player's **stat value**
  - `level`: that player's level
  - `prestige`: that player's prestige

If nobody occupies that rank yet, name fields show `---` and numeric fields show `0`.

## Example

A top-3 play time board:

```
&6&lTop Playtime
&e1. {top:playtime:1} - {top:playtime:1:value} min
&f2. {top:playtime:2} - {top:playtime:2:value} min
&f3. {top:playtime:3} - {top:playtime:3:value} min
```

## Tracked stats

These stats are tracked out of the box:

| Stat | Meaning |
|------|---------|
| `playtime` | Total minutes played |
| `joins` | Number of times the player has joined |

With **EndlessLeveling** installed (synced periodically):

| Stat | Meaning |
|------|---------|
| `el_level` | Player level |
| `el_xp` | Player XP |
| `el_prestige` | Prestige level |
| `el_rank` | Combined ranking: prestige first, then level as tiebreaker |

With **RPGLeveling** installed:

| Stat | Meaning |
|------|---------|
| `rpg_level` | Player level |
| `rpg_xp` | Player XP |

> **Tip:** for a prestige ladder, rank by `el_rank` and pull out the real numbers with the field qualifiers. For example, `{top:el_rank:1}` for the name, and `{top:el_rank:1:prestige}` and `{top:el_rank:1:level}` for their prestige and level.

## Refreshing

Leaderboard holograms update on their **update interval** like any placeholder hologram. The default interval is intentionally slow (about two minutes) to keep things light. Lower it on the hologram's [Display Settings](display-settings.md) if you want the board to refresh more often. The minimum interval is about 4 seconds.
