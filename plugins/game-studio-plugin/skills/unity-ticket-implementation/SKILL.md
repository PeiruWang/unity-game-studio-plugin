---
name: unity-ticket-implementation
description: Implement scoped Unity 6 game tickets safely. Use when the user provides a ticket, implementation spec, acceptance criteria, bug report, or narrowly scoped feature involving C#, scenes, prefabs, ScriptableObjects, Input System, uGUI, URP, sprites, 3D assets, or PlayMode/EditMode tests.
---

# Unity Ticket Implementation

## Overview

Use this skill whenever actual Unity work is driven by a ticket or implementation spec. The ticket controls scope; prototype specs provide intent and mood only.

Do not silently broaden the ticket into architecture cleanup, design invention, balance tuning, package changes, Project Settings edits, or unrelated prefab/scene rewrites.

## Ticket Workflow

1. Read the ticket and current project state.
2. Extract acceptance criteria:
   - User-visible behavior
   - Data/state changes
   - Scenes, prefabs, assets, ScriptableObjects, input assets, UI, or settings that may need changes
   - Required tests or manual verification
3. Separate known facts from design gaps.
   - Ask when missing design choices would materially change gameplay.
   - Use narrow defaults only when they are implementation mechanics, not game design.
4. Route to specialist skills:
   - `unity-2d-game`, `unity-3d-game`, `unity-ui`, `unity-sprite-pipeline`, `unity-3d-asset-pipeline`, and `unity-playtest`.
5. Implement only the scoped changes.
6. Verify with focused tests and PlayMode/manual checks.
7. Report changed assets and remaining risks.

## Scope Rules

- Follow existing project conventions before introducing new patterns.
- Avoid broad refactors unless needed to satisfy the ticket.
- Do not alter Project Settings, packages, URP assets, input assets, scenes, prefabs, import settings, or `.meta` files without a clear ticket reason.
- Do not tune gameplay values outside the ticket.
- Do not treat prototype docs as source of truth over implementation specs or existing assets.

## Design Gap Rules

Ask or mark an explicit assumption when the ticket lacks:

- Win/loss or failure behavior
- Player verbs or ability outcomes
- Camera feel or control mode
- Enemy behavior
- Level layout or spawn rules
- Economy, stats, damage, cooldowns, or tuning values
- UI priority, wording, or flow
- Asset identity, scale, or style

## Output Expectations

- State the implementation scope before editing.
- Name scene/prefab/settings/import risks.
- Keep verification tied to acceptance criteria.
- Report tests run, tests not run, and why.

## References

- Ticket safety details: `../../references/unity-ticket-safety.md`
- Shared architecture: `../unity-game-foundations/SKILL.md`
- Playtest checklist: `../unity-playtest/SKILL.md`
