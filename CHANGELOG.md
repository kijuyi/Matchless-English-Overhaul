# Changelog

All notable public changes to **The Matchless Kung Fu — English Overhaul** will be documented here.

## v1.0.1 — 2026-09-26

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
- identified a PuerTS startup-cache issue affecting the main-menu character hover under Workshop-only delivery
- validated a targeted reload of only `EquipDescItem.js` and `CharacterHorverPanel.js`, restoring the intended hover without a global cache flush or prototype patching
- preserved the exact known-good Workshop bootstrap after a simplified variant was shown to regress the hover

### Release engineering

- v1.0 remains immutable
- recovered exact Candidate 004T (`7bbb8f50...`) in multiple preserved locations
- identified the previously isolated manual PAK as Candidate 004U / SkillMasterySeparator (`48bcc43e...`), the newer live state immediately before the Workshop pivot
- selected Candidate 004U as the v1.0.1 payload after Workshop-only runtime validation
- frozen-candidate PAK SHA256: `48bcc43e15eb53ec252a2eadab9fea44c9143f48c3430eb05bcf047aa420e8a0`
- frozen Workshop bootstrap SHA256: `6f676f23597cf05698119ff3a68a6938e463f683ebc4962614563269b06e6723`
- PROBE088 passed byte-identity, mount, targeted-reload, and owner-observed UI regression gates
- final public v1.0.1 release ZIP SHA256: `f737de134b0f13d44fa02311f04e99d09e0ffb769567525ca2e7504c76acc895`
- FINAL092 confirmed the public-name ZIP is byte-identical to PACKAGE091

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

Subsequent confirmed corrections after v1.0.1 will be released as **v1.0.2+** rather than silently replacing an existing release.
