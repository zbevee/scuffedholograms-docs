# Integrations

ScuffedHolograms works fully on its own. When any of the plugins below are installed, extra features turn on **automatically**, with nothing to enable. If a plugin is not installed, its features are unavailable and everything else keeps working.

## LuckPerms

Use [LuckPerms](permissions.md) to manage who can administer holograms and to drive per-hologram access gates.

- Grant `scuffedholograms.admin` to let staff manage holograms without full operator powers.
- Per-hologram permission gates and per-permission trigger overrides resolve through LuckPerms.

## PlaceholderAPI

With PlaceholderAPI installed, you can use its `%token%` [placeholders](placeholders.md) anywhere in hologram text, in addition to ScuffedHolograms' own `{...}` tokens. They resolve per-viewer.

```
Balance: %vault_eco_balance%
```

## EndlessLeveling

Adds per-player level placeholders and level leaderboards:

- Placeholders: `{el_level}`, `{el_xp}`, `{el_class}`, `{el_prestige}`
- Leaderboard stats: `el_level`, `el_xp`, `el_prestige`, `el_rank`

See [Placeholders](placeholders.md) and [Leaderboards](leaderboards.md).

## RPGLeveling

Adds per-player level placeholders and leaderboards for RPGLeveling:

- Placeholders: `{rpg_level}`, `{rpg_xp}`, `{rpg_class}`, `{rpg_class_tier}`
- Leaderboard stats: `rpg_level`, `rpg_xp`

## Quest plugins

The **Quest Chain** [action mode](interactions.md) turns a hologram into a quest-giver NPC, and works with a supported quest plugin installed. ScuffedHolograms supports **TaleQuests** and **EndlessQuests**. Enter a quest's ID on each action, and the hologram advances through the chain as the player completes those quests.

Without a quest plugin, Quest Chain mode has nothing to gate against, so use one of the other action modes instead.
