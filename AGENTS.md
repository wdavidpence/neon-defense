# neon-defense agent context

This is a Phaser/browser tower-defense game inspired by Neo Defense for iPhone.

Start by running `git status --short`, then inspect `README.md`, `index.html`, and any existing checks. Serve the repository over HTTP for browser testing; do not use `file://`.

Make one player-visible improvement per pass. Before changing code, establish the current baseline. After changing code, run the repository's real checks, `git diff --check`, and a Playwright probe covering page load, start flow, console errors, delayed runtime errors, and an iPhone portrait viewport when relevant.

Static source checks are not proof of playability. Do not push, deploy, or publish unless the user explicitly asks.

## Per-pass checklist

- Goal / non-goals / first slice:
- Baseline check and browser condition:
- Changed behavior and files:
- Automated evidence:
- Browser/mobile evidence:
- Remaining uncertainty:
