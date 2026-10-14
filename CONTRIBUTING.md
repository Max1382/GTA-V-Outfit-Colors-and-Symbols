# Contributing — GTA V PC Outfit Colours, Symbols & Formatting

This is an **incomplete, evolving research/reference collection** maintained by **[Max1382](https://max1382.com)**. More codes may be added later, and some entries are untested in saved outfit names.

Original project: <https://github.com/Max1382/GTA-V-Outfit-Colors-and-Symbols>

## Report a code or correction

Open an Issue and include:

1. **Exact string tested** (for example `~g~Green Outfit` or `~HC_13~My Outfit`).
2. **Category**: short colour, indexed HUD colour, special symbol, formatting, or font.
3. **GTA V PC edition/build** and **mod menu or outfit editor/version**, if known.
4. **Location tested**: saved outfit name, another UI field, Scaleform interface, etc.
5. **Outcome**: displayed colour/icon, literal text, missing glyph, saved, persisted after reload, or failed.
6. **Evidence**: screenshots if useful (remove account details and other personal information).

**Please do not equate a recorded HUD RGBA value with confirmed saved-outfit-name formatting support.** A tag working in one UI may not work in another.

## Pull requests

- Keep [`Outfit-colors-more.json`](Outfit-colors-more.json) valid JSON and retain the existing seven top-level categories unless a change is explained.
- Use the current data shapes: `{"code":"~g~", "meaning":"green", "hud_color_index":18, "rgba":[114,204,114,255]}` for colour entries; `{"index":18, "tag":"~HC_18~", "rgba":[114,204,114,255]}` for indexed HUD colours.
- Don't label untested codes as working. Explicitly identify **reported**, **tested**, **verified**, and **experimental** observations.
- Add context and provenance for new information; explain what changed and why.
- Avoid duplicate entries; if an existing tag has more than one meaning depending on UI context, document the difference.
- Don't upload proprietary GTA textures, font files, or other third-party assets without rights to distribute them.
- Keep creator acknowledgement to **Max1382**, with links to **https://max1382.com** and the [original repository](https://github.com/Max1382/GTA-V-Outfit-Colors-and-Symbols), per the licence terms for original contributions.

## Version and completeness

This is **not** an exhaustive list of GTA V symbols, HUD colours, or formatting tokens across all versions and interfaces. It may be revised or expanded later. No updates are guaranteed.

Thanks for helping improve the reference!
