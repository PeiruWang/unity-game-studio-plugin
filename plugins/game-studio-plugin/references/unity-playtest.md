# Unity Playtest Checklist

Use this checklist for Unity gameplay QA.

## Test Runner

Prefer focused tests:

- EditMode for pure C# systems, data validation, and deterministic rules.
- PlayMode for scene boot, prefabs, input, physics, animation, camera, UI, and integration.

Unity command-line test runs usually use `-runTests`, `-testPlatform EditMode` or `-testPlatform PlayMode`, and `-testResults` when a Unity executable path is available.

## Scene Smoke Checks

- Relevant scene loads.
- No missing references.
- No console errors.
- Bootstrap order is stable.
- Main player verbs work.
- Pause/menu state works.
- Save/load boundary is not tied to scene objects.

## Input Checks

- Gameplay action maps work.
- UI action maps work.
- Gameplay input is gated under modal UI.
- Camera/look input is paused under menus or dialogs.
- Rebinding or device assumptions follow project conventions.

## 2D Visual Checks

- Sprite baseline and pivot consistency.
- Tilemap and collider alignment.
- Sorting layers and camera framing.
- Animation state readability.
- HUD does not obscure important playfield areas.

## 3D Visual Checks

- Camera framing and collision behavior.
- Mesh scale and collider match.
- Material and lighting readability.
- Animation transitions and root motion expectations.
- UI does not fight camera or movement input.

## Reporting

Lead with findings:

- What the player sees
- Reproduction steps
- Severity
- Why it matters
- Likely owner: simulation, MonoBehaviour bridge, scene/prefab, asset import, input, physics, UI, rendering, or tests
