# neoDefense playability backlog — 20 issues

1. Fix STAR_SEED initialization order so startup has no ReferenceError.
2. Map pointer coordinates to the actual canvas/world origin; remove the erroneous hard-coded HUD subtraction.
3. Center the playable field on wide laptop viewports with a shared world origin.
4. Apply the same world origin to pointer hit testing and placement.
5. Rebuild the grid after resize so cells and hit testing stay aligned.
6. Preserve tower coordinates when resizing instead of silently drifting them.
7. Ensure every tower type can acquire a valid target under its documented counter rules.
8. Ensure Cannon has a readable unpowered state and cannot appear silently broken.
9. Ensure Booster adjacency/charge updates immediately after placement, sell, and resize.
10. Ensure Laser, Missile, Boomerang, and Multi Rocket projectiles visibly render and resolve damage.
11. Remove smiley-face facial features from enemies; use glowing geometric role silhouettes.
12. Give each enemy role a distinct outline, glow, and readable combat sigil.
13. Ensure enemy and tower render layers remain inside the centered playfield.
14. Prevent HUD/action overlays from intercepting canvas placement clicks.
15. Make selected tower and selected cell state visibly unambiguous.
16. Make insufficient-gold and blocked-cell placement provide visible feedback.
17. Make the HUD sharp, information-dense, and readable without obscuring the field.
18. Keep laptop layout centered and portrait layout free of horizontal overflow.
19. Remove runtime errors/rejections during start, wave start, placement, and delayed combat.
20. Add a visible diagnostic/release marker for this playability correction and verify the full start → place → wave flow.
