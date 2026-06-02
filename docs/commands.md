# Commands

The base command is `/scuffedholograms`, with the alias `/sch`. All examples below use `/sch`.

Every command requires admin access (see [Permissions](permissions.md)). Players without access cannot use any `/sch` command.

| Command | Description |
|---------|-------------|
| `/sch menu` | Open the hologram management GUI |
| `/sch tool` | Give yourself the Hologram Tool |
| `/sch tptoholo <player> <hologram>` | Teleport a player to a hologram's current position |
| `/sch sendchat <player> <message>` | Send a chat message to one online player |
| `/sch cleanimages` | (Console) Delete uploaded images not used by any hologram |

---

## `/sch menu`

Opens the in-game management GUI, where you create, edit, position, and delete holograms. This is the main way to use the plugin. Must be run by a player.

If you are currently holding a hologram with the Hologram Tool's grab mode, `/sch menu` opens that hologram's edit page directly.

## `/sch tool`

Adds the **Hologram Tool** item to your inventory. The tool lets you select, grab, and move holograms in the world, and open their edit pages. See [Creating & Editing Holograms](creating-holograms.md). Must be run by a player.

## `/sch tptoholo <player> <hologram>`

Teleports `<player>` to the live position of the hologram named `<hologram>`.

- `<player>` is the target player's name.
- `<hologram>` is the hologram's key (its name). If the key contains spaces, wrap it in quotes: `"My Hologram"`.

Because the destination resolves at the moment the command runs, you can move the hologram later and the teleport still lands at its current location. This makes it useful as an interaction action, for example a "click to teleport" portal hologram (see [Interactions](interactions.md)).

This works **across worlds**: the player is taken to the hologram's world and position even if they are currently in a different world. The target player must be online.

## `/sch sendchat <player> <message>`

Sends a private chat message to a single online player.

- `<player>` is the recipient's name.
- `<message>` is the message text (the rest of the line). Quotes around the message are optional and are stripped if present.

The message supports colour codes, for example `&a` for green or `&#RRGGBB` for a hex colour. If no colour is specified, the message is sent in blue.

It is designed to be used as an interaction action so a hologram can message the player who interacted with it, for example:

```
/sch sendchat {player} "You have already completed this quest."
```

`{player}` resolves to the interacting player (see [Placeholders](placeholders.md)).

## `/sch cleanimages`

Deletes every uploaded image that is **not** referenced by any hologram, freeing space.

> **Run this from the server console with no players online.** It refuses to run while players are connected. If players are online it tells you how many and does nothing.
