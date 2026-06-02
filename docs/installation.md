# Installation

## Requirements

A Hytale server running version **0.5.0 or newer**.

## Steps

1. Place the ScuffedHolograms `.jar` into your server's `mods/` folder.
2. Start (or restart) the server.
3. On first start the plugin creates its data folders automatically (see [Data & Files](data-and-files.md)). No configuration file editing is required.
4. Join the server as an admin and run `/sch menu` to open the management GUI, or `/sch tool` to get the Hologram Tool. See [Commands](commands.md).

That is everything needed to start placing holograms.

## Optional plugins

ScuffedHolograms works fully on its own. If any of the following are installed, extra features turn on automatically (see [Integrations](integrations.md)):

- **LuckPerms** gives permission-node management for hologram access.
- **PlaceholderAPI** lets you use `%...%` placeholders in hologram text.
- **EndlessLeveling** and **RPGLeveling** add level, XP, class, and prestige placeholders and leaderboards.
- **A supported quest plugin** enables quest-gated interaction chains.

None of these are required. The plugin runs normally without any of them installed.

## Important: file watcher

Image and GIF holograms need the server's asset file watcher to be running. Do not start the server with `--disable-file-watcher`. If you do, image holograms will not appear for players. Text, model, and particle holograms are not affected. The `/sch menu` GUI warns you if the server was started with this flag.
