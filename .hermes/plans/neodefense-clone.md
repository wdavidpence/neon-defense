# neoDefense Clone — Implementation Plan

## Target Game: neoDefense by duetBlock (SON GIL)
- Premium iOS tower defense ($1.99), geometric/vector graphics, particle effects
- 99 missions across sectors (Alpha, Beta, Gamma, Delta, Epsilon, Zeta, Eta) — 15 missions/sector + bonus
- 2500+ waves of creeps, boss at end of each sector group
- Speed control 0.1x–16x, tower direction locking (Laser), auto-upgrade

## Current State
- Single-file Phaser 3 game (~2600 lines) with 8 tower types, 8 enemy types
- Has: HUD overlay, tower panel, power-ups, wave system, particle effects
- Missing: neoDefense's sector structure, correct tower types, vector aesthetic, speed control range

## Tower Types (neoDefense originals)
1. **Cannon** — AOE damage, slow fire rate, upgrades to bigger explosions
2. **Vulcan** — Rapid-fire single target, high DPS at max level
3. **Laser** — Continuous beam, can lock direction when upgraded, chains to nearby enemies
4. **Missile** — Homing projectile, AOE on impact, tracks targets
5. **Boomerang** — Throws a boomerang that returns through all enemies on path
6. **Multi Rockets** (later unlock) — Fires 3 rockets in spread pattern

Each tower upgradeable to level 5 with branching upgrade paths.

## Enemy Types (neoDefense)
1. **Creep (Normal)** — Basic enemy, follows path to core
2. **Fast Creep** — Small, quick, low HP
3. **Armored Creep** — High HP, slow movement
4. **Flying Creep** — Can fly over some obstacles (if map has them)
5. **Bouncer** — Bounces back when killed, damages nearby towers
6. **Boss** — Appears at end of each sector group (every 15 missions), very high HP

## Visual Style
- Dark background (#0a0a1a or similar)
- Geometric shapes for towers and enemies (circles, squares, triangles)
- Neon-colored outlines on all elements
- Particle explosions when enemies die (fireworks effect — key visual signature)
- Glowing path with subtle animation
- Clean, minimal UI

## Mission Structure
- **Alpha Sector** (Missions 1–15): Basic enemies, introduce all towers
- **Beta Sector** (Missions 16–30): Fast enemies introduced, harder combos
- **Gamma Sector** (Missions 31–45): Armored enemies, Bouncers introduced
- **Delta Sector** (Missions 46–60): Flying enemies, complex paths
- **Epsilon Sector** (Missions 61–75): All enemy types, harder bosses
- **Zeta Sector** (Missions 76–90): Extreme difficulty, bonus missions
- **Eta Sector** (Missions 91–99): Final challenge

Each sector has:
- 15 main missions with unique map layouts and enemy compositions
- 3 bonus missions (unlockable)
- Boss mission at the end of each sector

## Map/Path System
- Grid-based placement (12x16 or responsive)
- Multiple unique paths per mission (not just one static path)
- Path cells clearly marked with neon glow
- Spawn point and core/exit clearly visible

## Core Mechanics to Preserve & Enhance
1. **Tower placement** — Click tower type, then click empty cell
2. **Double-tap to upgrade** — Level 1–5 with stat increases
3. **Sell towers** — 60% refund, single and bulk sell
4. **Wave system** — Start wave button, enemy spawn queue
5. **Gold economy** — Earn gold from kills, spend on towers/upgrades
6. **Lives system** — Enemies reaching core cost lives (20 total)
7. **Speed control** — 0.1x, 0.25x, 0.5x, 1x (default), 2x, 4x, 8x, 16x
8. **Tower direction lock** — Laser tower can be locked to fixed direction at level 3+
9. **Cannon Booster** — Adjacent cannons get fire rate boost (synergy mechanic)
10. **Auto-upgrade** — Toggle to auto-upgrade towers when affordable

## Audio
- Web Audio API procedural sounds (already implemented)
- Different sounds per tower type
- Explosion noise for enemy deaths
- Wave start chime, wave clear melody
- Power-up collection sound

## Implementation Approach
Since this is a single-file Phaser 3 game, we rewrite `index.html` with:

1. **CSS** — Keep the overlay UI structure, update tower panel icons/names to match neoDefense
2. **Tower definitions** — Replace with Cannon, Vulcan, Laser, Missile, Boomerang, Multi Rockets
3. **Enemy definitions** — Replace with Creep types matching neoDefense (add Bouncer)
4. **Wave/mission system** — Implement sector-based structure with 99 missions
5. **Map generation** — Create multiple unique paths (at least 10 different layouts)
6. **Laser direction lock** — Add toggle for locked/unlocked laser targeting
7. **Cannon Booster synergy** — Detect adjacent cannons, apply fire rate bonus
8. **Speed control** — Expand to 0.1x–16x range (currently only has basic toggle)
9. **Auto-upgrade** — Add toggle that auto-purchases upgrades when affordable
10. **Particle effects** — Enhance death explosions to match neoDefense's "fireworks" look
11. **Boss system** — Boss at end of each sector (missions 15, 30, 45, 60, 75, 90)
12. **Mission select screen** — Sector-based mission browser with progress tracking

## File Structure
- Single `index.html` file (Phaser 3 via CDN) — no build step, mobile-friendly

## Key Differences from Current Game
| Feature | Current | Target (neoDefense) |
|---------|---------|---------------------|
| Tower types | Archer, Cannon, Ice, Tesla, Sniper, Laser, Rocket | Cannon, Vulcan, Laser, Missile, Boomerang, Multi Rockets |
| Enemy types | Normal, Fast, Tank, Healer, Boss, Phase, Swarmer, Nimbus | Creep, Fast, Armored, Flying, Bouncer, Boss |
| Mission structure | 40 waves (30 + boss rush) | 99 missions across 7 sectors |
| Speed control | Basic toggle (1x/2x) | 0.1x to 16x range |
| Laser mechanic | Standard beam | Direction lock at level 3+ |
| Synergy | Generic adjacent bonuses | Cannon Booster specific mechanic |
| Auto-upgrade | Not present | Toggle feature |
| Visual style | Emoji-based icons | Pure geometric/vector shapes |
| Particle effects | Basic burst | Fireworks-style explosions |

## Execution Order
1. Rewrite tower definitions (6 neoDefense towers)
2. Rewrite enemy definitions (5 types + boss)
3. Implement sector/mission structure with 99 missions
4. Create multiple map paths (10+ unique layouts)
5. Add Laser direction lock mechanic
6. Add Cannon Booster synergy
7. Expand speed control to 0.1x–16x
8. Add auto-upgrade toggle
9. Enhance particle effects for fireworks look
10. Update UI (tower panel, mission select, HUD)
11. Add boss system at sector boundaries
12. Polish: sounds, animations, mobile touch
