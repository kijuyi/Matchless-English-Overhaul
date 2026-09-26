# Changelog

All notable public changes to **The Matchless Kung Fu — English Overhaul** will be documented here.

## v1.0.1 — In preparation

v1.0.1 preserves the v1.0 localization baseline and incorporates UI/runtime fixes developed and tested after the v1.0 freeze.

### Character / equipment UI

- restored the post-v1.0 character-hover layout work so long English equipment names fit their categories more cleanly
- improved Character-screen Gear allocation and English name wrapping
- improved Gear/Fashion/Nickname spacing and containment
- improved Character-screen Skills readability while preserving the original 3x2 grid/navigation semantics
- retained the later TB032 Character-panel refinements instead of falling back to the frozen TB031/v1.0 UI

### Workshop distribution

- validated a private Steam Workshop carrier for AppID `1696440`
- verified Workshop delivery byte-for-byte from the prepared carrier to Steam's Workshop cache and Matchless's live mod directory
- verified the Workshop bootstrap mounts the localization PAK at runtime with mount point `../../../` and order `100`
- confirmed `MountPak result=true` in the game log with no manual PAK required

### Release engineering

- v1.0 remains immutable
- the accepted late TB032 line is being recovered as the source for v1.0.1 rather than rebuilding changes from memory
- final v1.0.1 PAK/ZIP hashes will be recorded after the exact accepted artifact is re-verified and frozen

## v1.0 — Initial public release

### Localization

- large-scale semantic and editorial review of the English UI/localization corpus
- full reconstructed conversation-tree audit
- extensive dialogue naturalization and contextual correction
- audit of event dialogue outside reconstructed conversation trees
- review of NPC dialogue, Verbal Duel/argument text, and delegation text
- cleanup of residual MTL/Engrish, missing information, incorrect numbers, and placeholder problems
- cross-surface terminology consistency for martial arts, factions, items, mechanics, quests, and Sect systems
- preservation of character voice, humor, wuxia/Jianghu atmosphere, and culturally meaningful references where possible

### Runtime/UI work

- fixes for residual Chinese/default/fallback UI text
- TimeHUD poetry/layout restoration
- traditional double-hour labels localized using zodiac-animal names:
  - Rat Hour
  - Ox Hour
  - Tiger Hour
  - Rabbit Hour
  - Dragon Hour
  - Snake Hour
  - Horse Hour
  - Goat Hour
  - Monkey Hour
  - Rooster Hour
  - Dog Hour
  - Pig Hour
- LingWu/YaoJue/PoZhao runtime localization work
- Sect, Beast Battle, Meridian, Secret/Insight, and related system terminology cleanup

### QA

- adversarial/red-team review of late dialogue builds
- static/runtime investigation of ambiguous UI bindings
- cross-surface terminology sweeps
- owner-observed runtime testing on selected high-risk surfaces

### Release policy

v1.0 is intentionally frozen.

Subsequent confirmed corrections will be released as **v1.0.1+** rather than silently replacing the v1.0 content.
