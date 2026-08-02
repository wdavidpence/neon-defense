# neoDefense Depth Research and Backlog

Research date: 2026-08-02

## Reference evidence

- Official site: https://www.duetblock.com/
- Full App Store listing: https://itunes.apple.com/us/app/neodefense/id1240750175?mt=8
- Lite App Store listing: https://itunes.apple.com/us/app/neodefense-lite/id1276408212?mt=8
- Public search results and Reddit strategy discussions were used only for mechanics cross-checks.

The official full-version listing reports:

- More than 2,500 waves across 99 missions.
- Five upgradable weapons.
- A boss at the end of each mission group.
- Distinct soundtrack groups by sector.
- Missions intended to be individually mind-challenging rather than interchangeable random waves.
- Build-anywhere fortress planning, upgrades, and resource decisions.

The official site identifies sector releases (for example, Zeta) as mission-content expansions. Public strategy discussion specifically calls out the Booster as a battery-like power source for Cannons, confirming that adjacency/power management is a core tactical relationship.

## Current neon-defense gap

The project displays 99 missions, but the implementation currently uses ten repeated path templates and random enemy selection. That creates a campaign label without authored mission identity, predictable budgets, or reliable strategy learning.

## Prioritized backlog

1. Deterministic authored mission data: map layout, starting budget, life budget, wave budget, enemy roster, boss flag, and mission rewards.
2. First campaign slice: hand-tuned missions 1-15 with distinct maps and deterministic wave compositions.
3. Economy pass: make starting cash, kill rewards, wave bonuses, and upgrade costs mission-specific and readable before starting.
4. Enemy roster pass: define explicit roles (runner, tank, flyer, splitter/bouncer, boss) and introduce them by sector with counters.
5. Tower identity pass: keep five core weapons distinct; make Booster/Cannon power a deliberate placement puzzle.
6. Campaign UI: show mission difficulty, map preview, starting budget, enemy preview, and best result before launch.
7. Sector progression: 7 sectors with distinct visual/audio themes and boss missions, while keeping 99 mission slots data-driven.
8. Map variety: authored path topology, multiple entrances/exits, choke points, long/short lanes, and tower-placement tradeoffs.
9. Playtest gates: deterministic start, one-tower placement, one wave completion, mission restart, portrait touch input, and online Pages verification.

## First implementation slice

Implement missions 1-15 as deterministic data while preserving the existing UI and controls. Use distinct layouts and explicit enemy wave rosters/budgets. Keep the 99-mission campaign path as the fallback for later authored content, but stop using random enemy composition for the first campaign slice.
