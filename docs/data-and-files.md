# Data & Files

ScuffedHolograms stores everything under one folder in your `mods/` directory. You normally never need to touch these files, since everything is managed in-game, but knowing the layout helps with backups and server migrations.

## Folder layout

```
mods/
├── ScuffedHolograms/          all your data
│   ├── holograms/             one .json file per hologram
│   ├── images/                uploaded images and GIFs
│   ├── leaderboards/          leaderboard stat data
│   ├── fonts/                 custom fonts
│   └── lang/                  language files
└── ScuffedHologramsData/      generated asset pack (textures and similar)
```

Both `ScuffedHolograms/` and `ScuffedHologramsData/` are created automatically on first start.

## Holograms

Each hologram is saved as its own `.json` file in `holograms/`, named after the hologram. Saves are written safely, so a crash mid-save cannot corrupt an existing hologram.

## Leaderboards

Each tracked [leaderboard](leaderboards.md) stat is stored as a `.json` file in `leaderboards/`, alongside a cached list of player names so offline players still show up by name.

## Backing up

To back up or move your holograms to another server, copy the whole **`mods/ScuffedHolograms/`** folder. That preserves your holograms, uploaded images, and leaderboard data together.

> If you move to a new server, copy `mods/ScuffedHolograms/` **before** the first launch there, so your holograms load on startup.

## Reloading

After manually editing files or dropping in new images, restart the server (or reload the plugin) with no players online so the changes are picked up cleanly. Adding images and editing holograms through the in-game GUI never needs a manual reload.
