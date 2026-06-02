# Styling Text

Text holograms are coloured with a visual tool in the line editor, so there are no codes to memorise. You type your text, then colour parts of it, pick a font, and optionally add an animation.

## Colour Segments

In a text line's editor, the **Colour Segments** tool colours spans of the line:

1. Add a segment and set the range of characters it covers.
2. Choose a colour mode:
   - **Solid** uses one colour for the whole span.
   - **Gradient** fades smoothly between two colours.
   - **Rainbow** cycles through the colour spectrum across the span.
3. Pick the colour with the colour picker (two colours for a gradient).

Add as many segments as you like to colour different parts of one line.

## Fonts

Each text line can use its own font. Drop `.ttf` files into `ScuffedHolograms/fonts/` to add your own, then choose them in the line editor.

## Animations

Each text line can have one animation:

| Animation | Effect |
|-----------|--------|
| **None** | Static text (default) |
| **Scroll** | Text scrolls horizontally |
| **Typewriter** | Text types out character by character, then repeats |
| **Rainbow** | Colours cycle through the spectrum over time |

The Rainbow animation moves over time. The Rainbow colour segment above is a fixed rainbow that does not move.
