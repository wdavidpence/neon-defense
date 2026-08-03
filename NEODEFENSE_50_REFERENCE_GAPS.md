# 50 neoDefense iPhone reference gaps for neon-defense

Research date: 2026-08-03

Scope: comparison of the current local `/Users/davidpence/neon-defense` build against the iPhone neoDefense reference. This is a prioritized research/backlog file, not a claim that every item should be implemented immediately.

Evidence labels:
- **A — App Store listing:** explicitly advertised or shown in the official Apple listing.
- **B — App Store review:** player-observed behavior/requests on the official listing; useful corroboration, but not a product specification.
- **C — reference screenshot/domain notes:** visible in the official iPhone screenshots or existing neoDefense reference notes.
- **D — local gap check:** absent or materially different in the current `index.html` source/runtime.

The current build already has real strengths—99 mission slots, seven tower definitions, deterministic authored missions 1–42, Booster/Cannon power, bosses, touch-oriented UI, synthesized SFX, mission persistence, and a neon canvas presentation. The list below deliberately identifies what the reference has or presents that this build does not yet match.

## Campaign, mission structure, and modes

1. **2,500+ total waves as real playable content** — neoDefense advertises more than 2,500 waves; the current build has only three authored sub-waves for missions 1–42 and fallback/random content afterward. **A/D · P0**
2. **99 genuinely authored, individually designed missions** — the reference describes each mission as mind-challenging; the current build exposes 99 slots but only authors 1–42 and falls back beyond that. **A/D · P0**
3. **Distinct mission identity rather than reusable fallback generation** — current missions 43–99 use legacy/random behavior instead of authored rosters and topology. **A/D · P0**
4. **Group/sector-specific campaign pacing** — the reference has mission groups with boss endpoints and soundtrack changes; current sectors are mostly metadata around a shared system. **A/C/D · P0**
5. **Boss at the end of every mission group** — the listing explicitly advertises this; current `isBossMission()` omits mission 99 and the authored set only reaches boss mission 15. **A/D · P0**
6. **Bonus missions** — the App Store “What’s New” explicitly mentions three bonus Eta missions; current UI has no separate bonus-mission classification or bonus campaign. **A/D · P1**
7. **Gamma-sector expansion/content gating** — the listing says in-app purchases unlock more Gamma missions; current build labels Gamma but has no expansion/access model. **A/D · P2**
8. **Sandbox mode** — a player review specifically describes Sandbox as a desired old-game mode; the current build has no sandbox/free-build mode. Treat this as a reference/legacy feature gap to validate, not a listing guarantee. **B/D · P2**
9. **Endless mode** — a player review specifically requests Endless; current build has no endless escalation mode. Treat this as a requested reference-era gap, not an App Store feature claim. **B/D · P2**
10. **Mission replay with a clear regular/bonus/mode distinction** — current mission selector only presents the authored/fallback mission grid; it does not distinguish campaign, bonus, sandbox, or endless entries. **B/D · P1**
11. **Per-mission difficulty authored as a deliberate challenge curve** — reference copy emphasizes mission-specific hardness; current fallback scaling is formulaic and random after the authored boundary. **A/D · P0**
12. **Pre-wave planning state with a true pause/build phase** — a review says the game would be more strategic if players could pause and build/start upgrades; current build has no pause control and waves run in real time once active. **B/D · P1**
13. **Clear pause/resume semantics** — current speed control is not a pause mode and has no paused overlay or explicit resume state. **B/D · P1**
14. **Mission result: flawless/no-leak outcome** — a review asks for visibility into whether a level was completed flawlessly or with leaks; current results show towers/kills/lives, not leak count or flawless status. **B/D · P1**
15. **High-score comparison/leaderboard presentation** — a review asks for high-score comparison; current local high score is stored but never surfaced as a leaderboard or comparison view. **B/D · P2**

## Core gameplay and tower strategy

16. **The reference’s compact five-weapon roster presentation** — neoDefense advertises five upgradable weapons; the current build presents seven choices, including Boomerang and Multi Rkt, so its roster does not match the reference’s recognizable five-weapon identity. **A/C/D · P1**
17. **All reference weapons available in the intended campaign progression** — the current build exposes every tower immediately in the tray; the reference presents a progression/expansion relationship that should be modeled rather than showing everything from mission 1. **A/B/D · P1**
18. **Weapon availability tied to sector/expansion progression** — review feedback notes weapons should become available across levels after expansion packs; current tower availability is global. **B/D · P1**
19. **Five weapon upgrade trees with reference-specific upgrade behavior** — current levels are generic stat scaling; the reference’s “five upgradable weapons” should become distinct upgrade identities, not just shared level math. **A/D · P1**
20. **Explicit Cannon/Booster adjacency rule** — reference notes state Booster works only with adjacent Cannons; current code uses power-range logic, not a strict adjacency-only rule. **C/D · P0**
21. **Booster explosion-energy collection mechanic** — reference notes describe collecting energy from explosions in its area; current Booster charge is incremented by nearby kills, not modeled as explosion-area energy pickup. **C/D · P0**
22. **Booster upgrade increases storage capacity and collection radius** — current Booster has capacity but no separate upgrade path that visibly increases both reference properties. **C/D · P1**
23. **Cannon dependency communicated as a core tactical rule** — the reference makes Cannon power management central; current UI shows “NO BOOST” but does not teach adjacency, energy pickup, or the placement puzzle before play. **C/D · P0**
24. **Exit-zone damage multiplier** — a player review reports that towers in the exit wavy circle receive double damage; current code has no exit-zone damage modifier. Validate against the actual app before implementing because this is review evidence, not official documentation. **B/D · P1**
25. **Build-anywhere fortress planning with reference map affordances** — the listing emphasizes building a fortress “any way you wish”; current maps use a rectangular grid with a single generated path and local no-build exceptions, not the reference’s distinctive compact map composition. **A/C/D · P1**
26. **Reference-style tower placement density/layout** — official screenshots show a dense field of small towers and creeps; current portrait layout leaves large UI chrome and uses larger geometric tower cells, reducing tactical density. **C/D · P1**
27. **Readable weapon power-up feedback** — screenshots advertise “Full of powers!” and show visually intense powered-up play; current Booster state is a small charge bar/text indicator without a comparable power surge presentation. **C/D · P1**
28. **Sweep/clear feedback as a named combat moment** — the listing markets “Build, Upgrade and Sweep!”; current wave clear has a chime but no named sweep moment, screen treatment, or clear-summary beat. **A/D · P1**
29. **Reference enemy catalog breadth** — reference notes call out 13+ enemy types; current build defines six enemy types. **C/D · P0**
30. **Enemy-specific visual/mechanical silhouettes for the larger catalog** — current roles are creep, fast, armored, flying, bouncer, boss; it lacks the reference’s broader enemy variety and corresponding counters. **C/D · P0**
31. **Reference boss presentation and escalation** — current boss is a scaled red enemy; the reference presents bosses as mission-group milestones and “too hard to beat,” requiring a stronger entrance, distinct mechanics, and reward beat. **A/C/D · P1**
32. **High-density fireworks combat presentation** — official screenshots visibly show a screen-filling burst of projectiles/effects; current effects are deliberately restrained and do not reach the reference’s “fireworks show” intensity. **C/D · P1**
33. **Upgrade/build cadence matched to fast reference combat** — a review reports waves can pass in 2–3 seconds and describes rapid drop/upgrade play; current game has upgrade actions but no reference-calibrated build/start cadence or pause-to-plan alternative. **B/D · P1**
34. **Challenge modes or difficulty setting** — a review requests an easy setting after finding later Gamma levels punishing; current build has no difficulty selector. **B/D · P2**
35. **Resource economy tuned around the reference’s three-life pressure** — reference notes describe a three-lives system; current build starts authored missions with 15–20 lives and displays a large lives budget, so the failure economy is materially different. Validate target version before adopting. **C/D · P1**

## Audio, music, and audiovisual polish

36. **Sector-specific soundtrack groups** — the listing explicitly advertises an amazing soundtrack in each group of missions; current code has no music tracks or soundtrack system. **A/D · P0**
37. **Title/attract music** — current start screen is silent until SFX interaction; no looping title theme or attract bed exists. **C/D · P1**
38. **Gameplay music loop** — current Audio API only synthesizes one-shot tones/noise; there is no gameplay music loop. **A/D · P0**
39. **Boss music/stinger** — current boss waves reuse ordinary wave audio; no boss-specific music or stinger is present. **A/D · P1**
40. **Sector transition music** — current sector changes update text only; there is no musical transition or sector-specific audio identity. **A/D · P1**
41. **Reference-style audio mix with music/SFX channels** — current `SFX` has a single volume/mute path and no independent music volume, SFX volume, or ducking controls. **A/D · P1**
42. **Distinct enemy movement/arrival sounds** — current code has shoot, death, wave, clear, power-up, and explosion sounds, but no enemy spawn, leak, or core-impact cue. **C/D · P1**
43. **Leak/core-damage sound** — current lives change visually, but there is no dedicated core-hit/leak sound event. **C/D · P1**
44. **Tower placement/upgrade/sell sounds** — current audio definitions do not include dedicated placement, upgrade, sell, or invalid-placement cues. **C/D · P1**
45. **Weapon-specific impact/explosion layering** — current shoot tones are per tower, but impact and explosion audio are generic noise/tones rather than distinct cannon, missile, laser, and powered-cannon layers. **C/D · P1**
46. **Mute state persistence and separate music mute** — current mute is an in-memory toggle only; reloading loses the setting and music cannot be muted independently because music does not exist. **D · P1**
47. **Music/SFX unlock on first iPhone touch without autoplay failure** — current AudioContext is initialized by start/click paths but has no music-start lifecycle, resume handling, or audio readiness indicator. **D · P1**

## iPhone UI, presentation, and finish

48. **Reference iPhone portrait composition** — App Store screenshots show a tightly framed portrait playfield, compact bottom controls, and gameplay content filling the phone; current portrait CSS retains a large top HUD/action stack and a much larger desktop-like grid footprint. **C/D · P1**
49. **Reference vector icon/logo/brand treatment** — the official listing uses a distinctive neoDefense logo and title treatment; current start screen uses a text/diamond substitute and does not reproduce the brand mark. **C/D · P2**
50. **Reference-quality animated vector finish** — the listing promises “stunning vector graphics,” “thrilling sound effects & animations,” and “astounding visual heaven”; current build has polished neon geometry but still lacks the reference’s dense micro-animation, music, power fireworks, broader content, and iPhone-native presentation as one coherent finish pass. **A/C/D · P0**

## Suggested order

1. Audio foundation: 36–47, starting with sector music, gameplay loop, boss stinger, and separate music/SFX controls.
2. Reference mechanics: 20–24, 29–35, especially strict Booster adjacency, explosion-energy collection, enemy catalog, boss milestones, and tuned lives/economy.
3. Content depth: 1–15, with authored missions and bonus/endless/sandbox decisions separated from the core campaign.
4. iPhone presentation: 25–28 and 48–50, after mechanics/audio are stable.

## Sources consulted

- Official App Store listing: https://apps.apple.com/us/app/neodefense-tower-defense/id1240750175
- Official developer site linked by the listing: https://www.duetblock.com/
- Local reference notes: `NEODEFENSE_RESEARCH.md`
- Local domain notes: `~/.hermes/skills/game-development/single-file-game-debugging/references/neodefense-domain.md`
- Current local implementation reviewed: `index.html` at commit `9de0a52`, plus a live HTTP probe at `http://127.0.0.1:4173/`

## Evidence limits

The App Store listing is authoritative for its marketing claims, screenshots, metadata, and displayed reviews—not for undocumented mechanics. Items marked B or C should be validated against a playable/reference build before being treated as exact specifications. The local gap claims were checked against current source terms and live UI; they are not a claim that the local build is otherwise unplayable.
