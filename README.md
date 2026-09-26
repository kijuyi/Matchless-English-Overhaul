# The Matchless Kung Fu — English Overhaul

A comprehensive fan-made English localization overhaul for **The Matchless Kung Fu**.

> **Current release:** v1.0.1  
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

## What's new in v1.0.1

v1.0.1 preserves the reviewed v1.0 localization baseline and adds the post-v1.0 TB032 UI/runtime fixes validated through the private Workshop pipeline.

Notable changes include:

- improved main-menu character equipment-summary wrapping for long English names
- improved Character-screen Gear name allocation and wrapping
- preserved later Character Skills readability/layout refinements
- retained Fashion/Nickname containment refinements
- validated Steam Workshop delivery for game version 1.4.0.7 using the same localization PAK plus a small runtime bootstrap

## Installation

Download the ZIP from the [Releases page](https://github.com/kijuyi/Matchless-English-Overhaul/releases).

### Windows / manual installation

1. Close the game.
2. Open the game's installation folder.
3. Go to:

   `HMS_00/Content/Paks/`

4. Copy:

   `mod/HMS_00-WindowsNoEditor_999_P.pak`

   from the downloaded archive into that folder.
5. Start the game normally.

If `HMS_00-WindowsNoEditor_999_P.pak` already exists, **do not overwrite it blindly**. It may belong to another mod.

### Linux / Steam

Close the game, extract the release archive, and run:

```bash
bash install_linux.sh
```

The installer checks common native and Flatpak Steam locations. Custom Steam libraries can be supplied through `MATCHLESS_GAME_DIR`.

## Uninstallation

Linux users can run:

```bash
bash uninstall_linux.sh
```

Manual uninstall: remove `HMS_00-WindowsNoEditor_999_P.pak` from `HMS_00/Content/Paks/` **only if it is this mod's file**.

## Compatibility

This mod replaces/overrides English localization plus a small number of UI/runtime assets.

Other mods touching the same files may conflict depending on PAK load order. For the cleanest troubleshooting, disable other English-translation mods such as BET before reporting a localization bug.

## Known limitations

v1.0 remains the frozen first public release after extensive editorial, static, and runtime QA.

The Matchless Kung Fu is a very large sandbox, so rare contextual issues can still exist—especially in unusual event combinations and less-tested advanced systems. **The Wilds** and some advanced **Sect** mechanics currently have less owner-observed runtime coverage than the main game.

Community reports are welcome. Confirmed fixes after v1.0.1 will be released as **v1.0.2+** rather than silently replacing an existing release.

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

## v1.0.1 verification

Public release ZIP SHA256:

```text
f737de134b0f13d44fa02311f04e99d09e0ffb769567525ca2e7504c76acc895
```

Installed mod PAK SHA256:

```text
48bcc43e15eb53ec252a2eadab9fea44c9143f48c3430eb05bcf047aa420e8a0
```

## Project policy after v1.0.1

v1.0 and v1.0.1 are intentionally immutable after publication.

Future changes should be tied to concrete bug reports, new runtime evidence, community feedback, or compatibility changes. They will be versioned as v1.0.2, v1.0.3, and so on.

## Disclaimer

This is an **unofficial fan project** and is not affiliated with the developers or publisher of The Matchless Kung Fu.

No repository license has been selected at this time.
