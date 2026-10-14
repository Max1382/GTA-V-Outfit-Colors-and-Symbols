# GTA V PC — Modded Outfit Name Colours, Symbols & Formatting

**A community reference collection by [Max1382](https://max1382.com)** for experimenting with colour codes, special symbols, formatting tags, and font references in **GTA V on PC**, including modded saved outfit names through a compatible mod menu or outfit-name editor.

> [!IMPORTANT]
> **This is NOT a complete list of every possible GTA V colour, code, symbol, font, or formatting option.** It contains items collected so far. **I may add more entries and update this repository at a later date.** There is no guaranteed update schedule.

The [`Outfit-colors-more.json`](Outfit-colors-more.json) file currently contains:

- **17** short colour / colour-related tags (including reset and script-variable tags)
- **235** indexed HUD colour values, **0–234**, with RGBA values captured from a running game
- **8** special symbol / icon code references
- **9** formatting tag references or patterns
- **6** additional Unicode symbols to test
- **10** font-face references to test, alongside **10** mapping records

> [!WARNING]
> **A code appearing in the JSON does not mean it works in a saved outfit name.** GTA V has different text renderers, and support can vary by game build, UI screen, font, and the mod menu or editor you use. Indexed HUD colours are documented as game colour values, **not as verified working outfit-name tags**. Fonts and many formatting examples are explicitly **to test**.

## How to use these codes in a GTA V PC mod menu

1. Launch GTA V on PC and open a compatible mod menu / outfit editor with a **saved outfit name** or **rename outfit** field.
2. Open [`Outfit-colors-more.json`](Outfit-colors-more.json) and choose a value from `color_tags`, `symbols`, or another section.
3. **Copy the code itself, not the entire JSON object.** For colours, add the colour code **before** the text or symbol you want to try.
4. Paste the result into the outfit-name field. Save or preview it if your editor supports that.
5. **Check it in the actual game UI.** Confirm whether it displays, survives saving, and persists after reopening/reloading. A name being accepted by a tool is not proof its styling renders.

### Copy-and-paste examples

```text
~g~Green Outfit
~r~Red Outfit
~b~Blue Outfit
~p~Purple Outfit
~y~Yellow Outfit
```

For a special glyph, try a colour prefix followed by the symbol:

```text
~g~¦
~y~∑
~r~Ω
```

These symbols have **reported uses**, such as Rockstar-related glyphs or a lock icon, but **their appearance is font- and UI-dependent**. In some places they may appear as normal characters or not render.

To **experiment** with an indexed HUD-colour tag:

```text
~HC_13~My Outfit
```

`~HC_13~` corresponds to HUD colour index **13**, with RGBA **254, 235, 169, 255** in the supplied data. **That does not establish that this syntax is recognised by your saved outfit name field.**

### Colour code + image tag (from a separate image-tag list)

If you also use image-source tags, the general pattern is:

```text
~g~<img src='rockstar_logo'>
```

The `~g~` prefix requests green and the `<img src='...'>` is a proposed image tag. **Image rendering or recolouring is not confirmed** for the outfit-name UI. For image candidates and size checks, see the separate [GTA V Modded Outfit Names reference](https://github.com/Max1382/GTA-V-Modded-Outfit-Names).

## Short colour / colour-related tags

The following values are copied from `color_tags`. The RGBA numbers are **reference values from the JSON**, not guarantees of how they will appear in an outfit name.

| Code | Meaning in this data | HUD index | RGBA |
| --- | --- | ---: | --- |
| `~w~` | White | 1 | 240, 240, 240, 255 |
| `~r~` | Red | 6 | 224, 50, 50, 255 |
| `~g~` | Green | 18 | 114, 204, 114, 255 |
| `~b~` | Blue | 9 | 93, 182, 229, 255 |
| `~d~` | Dark blue | 11 | 47, 92, 115, 255 |
| `~y~` | Yellow | 12 | 240, 200, 80, 255 |
| `~o~` | Orange | 15 | 255, 133, 85, 255 |
| `~p~` | Purple | 21 | 132, 102, 226, 255 |
| `~q~` | Pink | 24 | 203, 54, 148, 255 |
| `~c~` | Menu grey | 67 | 140, 140, 140, 255 |
| `~t~` | Menu grey | 67 | 140, 140, 140, 255 |
| `~m~` | Mid grey | 74 | 100, 100, 100, 255 |
| `~l~` | Black | 2 | 0, 0, 0, 255 |
| `~f~` | Friendly blue | 118 | 93, 182, 229, 255 |
| `~s~` | Reset to context default | — | Context-dependent |
| `~u~` | Script variable 2; not fixed black | — | Context-dependent |
| `~v~` | Script variable 1 | — | Context-dependent |

**Important:** `~s~` resets to the current context's default styling. `~u~` and `~v~` are **script-variable codes**, not guaranteed fixed colours. `~c~` and `~t~` both map to menu grey in the supplied list.

## Indexed HUD colours (`~HC_...~`)

The JSON includes HUD-colour records numbered **0 through 234**, for example:

| Tag | RGBA | Note |
| --- | --- | --- |
| `~HC_6~` | `224, 50, 50, 255` | Red reference value |
| `~HC_13~` | `254, 235, 169, 255` | Pale yellow reference value |
| `~HC_18~` | `114, 204, 114, 255` | Green reference value |
| `~HC_21~` | `132, 102, 226, 255` | Purple reference value |
| `~HC_208~` | `255, 0, 0, 255` | Bright red reference value |

Look under `all_hud_colors_from_running_game` to see all **235** entries. The `index` is a numeric colour identifier; `tag` is the proposed text-token representation; `rgba` gives its red, green, blue, and alpha channels (0–255). **Do not assume every `~HC_<number>~` token will be interpreted by your outfit editor.**

## Symbols and other formatting

| Code | Reported use / status |
| --- | --- |
| `¦` | Rockstar verified glyph (reported) |
| `∑` | Rockstar logo glyph (reported) |
| `‹` | Rockstar created glyph (reported) |
| `›` | Blank glyph (reported) |
| `Ω` | Lock glyph (reported) |
| `~ws~` | Wanted star (reported) |
| `~wanted_star~` | Wanted star alias (reported) |
| `~EX_R*~` | Rockstar logo in supported fonts (reported) |

Additional symbols currently marked **to test**: `←` `↑` `→` `↓` `∞` `÷`.

The `formatting_tags` section also includes `~h~`, `~bold~`, `~italic~`, `~n~`, `~nrt~`, and examples/patterns for HUD colours and blips. Entries containing literal `...`, such as `~HC_...~`, `~HUD_COLOUR_...~`, and `~BLIP_...~`, are **patterns/placeholders**, **not ready-to-paste working commands**. Replace the placeholder with an appropriate value where supported.

## Fonts

See `font_faces_to_test` and `fontmap_mappings` in the JSON. Some font names include `$GTAVLeaderboard`, `$gtaCash`, `$Font2_cond`, `$HandstyleHeist`, and `$RockstarTAG`.

**Font references are not instructions for how to load a font in every GTA interface.** Some mappings are unverified or may work only in specific UI/Scaleform contexts. Fonts aren't included as downloadable font files in this repository.

## Check length and compatibility

Outfit-name fields can have **short byte limits**, and these can depend on the editor and field used. The full pasted string counts, including colour prefixes and any additional formatting. ASCII colour codes like `~g~` take **3 UTF-8 bytes**; non-ASCII symbols may take more than one byte. If your editor states a limit, check **UTF-8 bytes**, not just visible characters.

This JSON does **not** verify which colour, symbol, or formatting strings render in saved outfit names. If a pasted code fails, try a shorter string or different game UI and report the result.

## File layout

```text
.
├── README.md                 # Instructions and reference information
├── Outfit-colors-more.json   # Colours, indexed HUD values, symbols and fonts
├── CONTRIBUTING.md           # How to submit corrections / working tests
└── LICENSE.md                # Attribution and licensing information
```

## Credit, reuse and redistribution

**This reference compilation and original documentation are maintained by [Max1382](https://max1382.com).** If you copy, repost, redistribute, or adapt the original selection, organisation, annotations, or documentation, **credit Max1382 and link to the source repository**.

**Suggested attribution:**

> GTA V PC Outfit Colours, Symbols & Formatting — compiled by **[Max1382](https://max1382.com)**. Original repository: **[https://github.com/Max1382/GTA-V-Outfit-Colors-and-Symbols](https://github.com/Max1382/GTA-V-Outfit-Colors-and-Symbols)**. Original contributions licensed under **[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)**. Changes: [describe changes or write "none"].

The licence only applies to **Max1382's original contributions** to the extent they are copyrightable. Rockstar / Take-Two intellectual property, independently existing strings, and factual game colour values are not claimed as exclusive property. See [`LICENSE.md`](LICENSE.md).

## Updates & contributions

**This collection is not exhaustive.** There may be more colour codes, variants, symbols, font mappings, or formatting controls than those currently included. **I might update it with more findings later.** New or changed values should be tested before being described as working.

If you have a correction or a confirmed working example, open a GitHub Issue or Pull Request and follow [`CONTRIBUTING.md`](CONTRIBUTING.md). Please include the exact tag, context, game version, and what was actually observed.

## Disclaimer

This is a **JSON reference**, not a mod menu, injector, or promise that a particular outfit-name effect works. Use third-party tools at your own risk; modifications to GTA Online may violate Rockstar rules and risk account action. **Unofficial fan resource; not affiliated with or endorsed by Rockstar Games or Take-Two Interactive.** Their respective trademarks and assets remain theirs.

---

**Made by [Max1382](https://max1382.com) · [Source repository](https://github.com/Max1382/GTA-V-Outfit-Colors-and-Symbols)**
