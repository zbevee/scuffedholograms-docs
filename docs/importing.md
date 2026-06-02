# Importing

If you are moving to ScuffedHolograms from another hologram plugin, you can import your existing holograms instead of rebuilding them. Importing is done from the management GUI (`/sch menu`).

## Supported plugins

| Plugin | Imported from |
|--------|---------------|
| **FancyHolograms** | `mods/FancyHolograms/` |
| **HydroHologram** | `mods/HydroHologram/` |

The importer reads each plugin's saved holograms and brings across their text and images.

## How to import

1. Make sure the other plugin's data is still present in your `mods/` folder. You do not need the plugin enabled, only its files.
2. Open `/sch menu`, go to the **Settings** section, and click **Import All**.
3. ScuffedHolograms scans for FancyHolograms and HydroHologram data and imports any holograms it finds, copying their images in as well.

## After importing

- Imported holograms are normal ScuffedHolograms holograms. Edit them in the GUI like any other.
- Review positioning and [billboard mode](display-settings.md). Other plugins describe orientation differently, so a few holograms may need a small adjustment.
- Once you have confirmed everything imported correctly, you can remove the old plugin.
