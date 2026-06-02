# Images & GIFs

ScuffedHolograms can display still images and animated GIFs as holograms. Once an image is uploaded you add it to a hologram as an **Image** line ([Creating & Editing](creating-holograms.md)).

## Supported formats

| Format | Notes |
|--------|-------|
| **PNG** | Recommended, supports transparency |
| **JPG / JPEG** | No transparency |
| **BMP** | No transparency |
| **GIF** | Played as an animation |

## Adding an image

There are two ways to get an image into ScuffedHolograms.

### 1. Upload from a URL (in-game)

In the management GUI you can paste a direct image URL. The image downloads and becomes available right away, without restarting the server. This is the easiest method and works while players are online.

### 2. Drop folder

Place image files into:

```
mods/ScuffedHolograms/images/
```

Dropped files are imported when the server starts or reloads with no players online. Use this for bulk-adding many images at once.

## Animated GIFs

Upload a GIF the same way as any image. It plays its animation automatically in the world. Large GIFs are scaled down as needed so they display correctly.

## Choosing and adjusting the image

In an image hologram's editor you pick the image from a dropdown of everything you have uploaded. You can also rename an image and refresh the list. On the same panel you set:

- **Scale** sets how large the image appears.
- **Sharp edges** is a toggle (off by default). If you notice a faint pulsing or "heartbeat" flicker on the image, turn it **on** to remove it. You lose a small amount of edge smoothness in exchange, so if the image still looks good, leave it on.

There is also an advanced **Render Mode** toggle: **Particle** (default) looks the sharpest, while **Entity** is lighter where many players gather and avoids flicker. Switch to Entity for busy areas.

## Tips

- Images look best when their dimensions are reasonable for the in-world size you want. Very large source images are scaled to fit.
- Use the [Fixed billboard mode](display-settings.md) to mount an image flat on a wall or floor. Image holograms in Fixed mode are readable from both sides.
- To remove uploaded images you no longer use and reclaim space, run `/sch cleanimages` from the console with no players online ([Commands](commands.md)).
