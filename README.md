# The Matchless Kung Fu — English Overhaul

A comprehensive fan-made English localization overhaul for **The Matchless Kung Fu**.

> **Current release:** v1.0.2<br>
> **Tested game version:** 1.4.0.7  
> **Standalone:** BET is **not** required.

[Download the latest release](https://github.com/kijuyi/Matchless-English-Overhaul/releases/latest)

## Why this project exists

The Matchless Kung Fu is an unusually rich sandbox, but the official English localization can be difficult to follow. Existing translation mods improved parts of the game, yet a large amount of awkward, machine-translated, inconsistent, or contextually incorrect English remained.

This project grew from a simple translation cleanup into a much deeper localization effort. The goal is not to rewrite the game for stylistic preference, but to preserve the original Chinese meaning, gameplay information, character voice, humor, and wuxia/Jianghu atmosphere while making the English natural and readable.

## What was reviewed

The project includes modern review and QA across the known English localization surfaces used by the tested build, including:

- **9,408** UI/localization IDs
- **675** reconstructed conversation trees
- **1,527** event-dialogue keys outside those trees
- **558** strings across NPC dialogue, Verbal Duel/argument text, and delegation text
- terminology consistency across martial arts, factions, items, quests, sect systems, mechanics, and UI
- runtime/static UI text outside the ordinary CSV corpus
- TimeHUD double-hour localization, LingWu/YaoJue/PoZhao, and several fallback/static UI surfaces
- late-stage adversarial/red-team review of dialogue and high-risk strings

Correct or natural English was intentionally retained. **A reviewed line is not necessarily a rewritten line.**

## A small example of the difference

Some of the original English was grammatically understandable but had lost the personality, humor, or cultural setup of the Chinese.

One reviewed event, for example, originally flattened two overdramatic martial artists into repeated phrases about a generic “noble endeavor.” The revised version restores their theatrical storybook language, the Peach Garden sworn-brotherhood joke, and the final punchline that they are mostly happy to have found somewhere to eat.

That kind of contextual recovery—not just grammar correction—is the main purpose of this overhaul.

## AI-assisted localization

This project made extensive use of **AI tools** for translation analysis, Chinese-source comparison, contextual research, consistency checking, runtime/code investigation, adversarial review, and QA.

AI output was **not treated as authoritative or accepted as raw machine translation**. Changes were iteratively checked against the original Chinese, neighboring dialogue, gameplay context, established terminology, and—where necessary—runtime behavior and game code.

Multiple AI systems were used at different stages of the project, alongside manual playtesting, screenshots, static analysis, and editorial adjudication.

The goal was to use AI as a research and review tool to reduce the problems normally associated with machine-translated localization, not to ship another unreviewed MTL pass.

## What's new in v1.0.2

- Reviewed dialogue/context corrections and clearer sect guidance after joining.
- `Roamer` for the generic identity; narrative refugees remain distinct.
- Corrected mechanical mastery terminology, including `Adept` in affected contexts.
- Conditional head-item descriptions without empty identity delimiters.
- Preserved approved UI/runtime fixes and the narrower event-created-actor name repair.

[Release notes and known limitations](docs/V1.0.2_RELEASE_NOTES.md) · [Changelog](CHANGELOG.md). Split Name&Surname 2.0 is **not included**. Steam Workshop rollout is separate from this GitHub release.

## What's new in v1.0.1

v1.0.1 preserves the reviewed v1.0 localization baseline and adds the post-v1.0 TB032 UI/runtime fixes validated through the private Workshop pipeline.

Notable changes include:

- improved main-menu character equipment-summary wrapping for long English names
- improved Character-screen Gear name allocation and wrapping
- preserved later Character Skills readability/layout refinements
- retained Fashion/Nickname containment refinements
- validated Steam Workshop delivery for game version 1.4.0.7 using the same localization PAK plus a small runtime bootstrap

## Installation — v1.0.2 (Steam, Windows or Linux/Proton)

Download [Matchless_English_Overhaul_v1.0.2.zip](https://github.com/kijuyi/Matchless-English-Overhaul/releases/download/v1.0.2/Matchless_English_Overhaul_v1.0.2.zip) and verify its [SHA256](#v102-verification).

**v1.0.2 is a full runtime mod package. Do not use the old v1.0.1 PAK-only instructions.** This ZIP contains no `install_linux.sh` or `uninstall_linux.sh`. Its layout is:

```text
Matchless_EnglishOverhaul_v1.0.2/
  INSTALL.txt
  COMPONENTS.json
  CHANGELOG.md
  mod/
    WorkItem.json
    Src/Main.js
    Content/Pak/HMS_00-WindowsNoEditor_999_P.pak
```

All three files under `mod/` must be installed together. The PAK alone omits required runtime integration.

### Workshop versus this GitHub release

This GitHub publication **does not update Steam Workshop**. The existing [Workshop item 3808208955](https://steamcommunity.com/sharedfiles/filedetails/?id=3808208955) remains a separate delivery channel. Subscribing alone does not guarantee that this GitHub version has reached Steam.

The manual update below uses that existing subscribed item as the game's loader carrier. Keep it subscribed. Steam may replace manually updated cache files when it downloads or verifies Workshop content; check the version/hashes again if this happens. Do not mix this update with another copy of the overhaul or another English-translation mod while troubleshooting.

### Windows — manual update of the subscribed carrier

1. Subscribe to the existing Workshop item above, let Steam finish downloading it, then close the game completely.
2. Extract the ZIP. Open `Matchless_EnglishOverhaul_v1.0.2/mod/`.
3. Locate the **existing** Workshop cache folder for that item, in its Steam library:

   `<SteamLibrary>\steamapps\workshop\content\1696440\3808208955\`

   It must already contain `WorkItem.json`, `Src` and `Content`. Back up the whole item folder somewhere outside Steam before changing it. Do not create a guessed folder in a different library.
4. Copy the **contents of `mod/`** into that item folder, merging the `Src` and `Content` directories and replacing the three matching files. Do not create an extra nested `mod` directory.
5. Start the game and ensure **Matchless English Overhaul** is enabled in Manage Mods. The game synchronizes this subscribed carrier to `HMS_00/Content/JavaScript/Mods/3808208955/` itself. Editing only that game-managed copy is insufficient: it is rebuilt during startup.

### Linux / Steam Deck / Proton — same carrier layout

Use the existing item folder under the library that actually stores its Workshop download:

`<SteamLibrary>/steamapps/workshop/content/1696440/3808208955/`

This applies to native and Flatpak Steam libraries; their library roots differ. Close the game **and Proton** first. Back up that item folder outside Steam, then copy the same three files from the extracted `mod/` directory into it. Preserve the exact case of `Src/Main.js`, `Content/Pak` and `WorkItem.json`. Do not copy into the Proton prefix or into `HMS_00/Content/Paks/`.

Linux example, **after making the backup**, from inside the extracted `Matchless_EnglishOverhaul_v1.0.2` directory (replace the library path):

```bash
MODROOT="/path/to/SteamLibrary/steamapps/workshop/content/1696440/3808208955"
test -f "$MODROOT/WorkItem.json" || { echo "Existing subscribed carrier not found"; exit 1; }
cp mod/WorkItem.json "$MODROOT/WorkItem.json"
cp mod/Src/Main.js "$MODROOT/Src/Main.js"
cp mod/Content/Pak/HMS_00-WindowsNoEditor_999_P.pak "$MODROOT/Content/Pak/HMS_00-WindowsNoEditor_999_P.pak"
```

Restart and enable the overhaul in Manage Mods. Native release QA was performed on Linux/Proton; the Windows instructions use the same source-verified Steam carrier contract, not a separate Windows playtest. Non-Steam loader installation is not covered here.

### Upgrading from a legacy PAK-only installation

If you previously installed this overhaul directly into `HMS_00/Content/Paks/`, back up and remove **only the old standalone copy positively identified as this mod** before using the carrier installation. Do not remove original game PAKs or unrelated mods. A stale standalone PAK can override the new carrier's files. The v1.0.1 archive and its installers remain available on its immutable release page, but they are not v1.0.2 installers.

## Rollback / uninstallation

Close the game and Proton, restore the three exact files from your pre-update carrier backup, then restart. Verify their hashes if recorded. Do not restore or modify saves to roll back mod files; mod rollback does not undo world progress.

To remove the overhaul entirely, unsubscribe from its Workshop item and remove only any identified legacy standalone overhaul PAK you installed separately. Leave original game files and other mods untouched. There is no v1.0.2 uninstall script in this ZIP.

## Compatibility

This mod replaces/overrides English localization plus a small number of UI/runtime assets.

Other mods touching the same files may conflict depending on PAK load order. For the cleanest troubleshooting, disable other English-translation mods such as BET before reporting a localization bug.

## Known limitations

v1.0 remains the frozen first public release after extensive editorial, static, and runtime QA.

The Matchless Kung Fu is a very large sandbox, so rare contextual issues can still exist—especially in unusual event combinations and less-tested advanced systems. **The Wilds** and some advanced **Sect** mechanics currently have less owner-observed runtime coverage than the main game.

Community reports are welcome. Further fixes will receive a new version rather than silently replacing an existing release. [Issue #2](https://github.com/kijuyi/Matchless-English-Overhaul/issues/2) tracks minor concatenated headings such as `AdvanceAdept`; this is deferred and does not invalidate the corrected `Adept` caption.

## Reporting a problem

The easiest option is to [open a GitHub Issue](https://github.com/kijuyi/Matchless-English-Overhaul/issues/new/choose).

The most useful report includes:

- a screenshot
- the exact English text, if readable
- what you were doing
- the quest/event/panel/system involved
- what option you selected immediately before the problem, if relevant

Especially useful reports include:

- MTL/Engrish or nonsensical dialogue
- wrong speaker, pronoun, subject, or object
- numbers/effects that do not match gameplay
- untranslated Chinese
- clipping or overflow
- literal placeholders such as `{0}`
- inconsistent names for the same martial art, faction, item, or mechanic
- choices whose results do not match their text

See [REPORTING-BUGS.md](REPORTING-BUGS.md) for details.

## v1.0.2 verification

ZIP SHA256:

```text
e276d617e4a41a69d1944e86b5324b49df9c4472c7c2e417da93d7b8a157f298
```

Windows PowerShell: `Get-FileHash .\Matchless_English_Overhaul_v1.0.2.zip -Algorithm SHA256`

Linux: `sha256sum Matchless_English_Overhaul_v1.0.2.zip`

The three individual payload hashes are in `COMPONENTS.json` and the [release notes](docs/V1.0.2_RELEASE_NOTES.md#package-identity).

## v1.0.1 verification (historical)

Public release ZIP SHA256:

```text
f737de134b0f13d44fa02311f04e99d09e0ffb769567525ca2e7504c76acc895
```

Installed mod PAK SHA256:

```text
48bcc43e15eb53ec252a2eadab9fea44c9143f48c3430eb05bcf047aa420e8a0
```

## Project policy

v1.0 and v1.0.1 remain intact. Published release assets are immutable.

Future changes should be tied to concrete bug reports, new runtime evidence, community feedback, or compatibility changes. They will receive a new version, beginning with v1.0.3.

## Disclaimer

This is an **unofficial fan project** and is not affiliated with the developers or publisher of The Matchless Kung Fu.

No repository license has been selected at this time.
