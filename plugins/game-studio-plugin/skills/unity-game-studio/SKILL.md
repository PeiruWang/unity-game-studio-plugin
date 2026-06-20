---
name: unity-game-studio
description: Route early Unity 6 game work. Use when the user needs workflow planning across C#, 2D or 3D gameplay, scenes, prefabs, ScriptableObjects, URP, Input System, uGUI, assets, ticket scope, and PlayMode or EditMode verification before moving to a specialist Unity skill.
---

# Unity Game Studio

## Overview

Use this skill as the umbrella entrypoint for Unity game work. Do not route to browser stacks such as Phaser, Three.js, React Three Fiber, Vite, DOM overlays, Playwright, Rapier JS, or raw WebGL.

Unity 2D and Unity 3D are both first-class paths. The job here is to classify the request, preserve the player's intended fantasy and verbs, identify design gaps, and hand off to the most specific Unity specialist skill.

## Routing Rules

Classify before designing or coding:

- `Unity foundations`: architecture, simulation versus presentation, MonoBehaviour boundaries, scene/prefab ownership, input model, save/debug/perf.
- `Unity 2D`: sprites, Tilemaps, 2D physics, SpriteRenderer, Animator clips, URP 2D lighting, 2D camera.
- `Unity 3D`: GameObjects, prefabs, MeshRenderer, materials, colliders, Rigidbody or CharacterController, Animator, 3D camera, URP lighting.
- `Unity 3D assets`: model import settings, scale, pivots, materials, animation clips, LOD, colliders, prefab readiness.
- `Unity UI`: uGUI HUD, menus, pause, dialogs, inventory, settings, EventSystem, CanvasScaler, input focus.
- `Unity sprite pipeline`: seed frames, strips, slicing, PPU, pivots, SpriteAtlas, Animator integration.
- `Unity playtest`: EditMode tests, PlayMode tests, scene boot, console logs, visual QA, input smoke tests.
- `Unity ticket implementation`: scoped implementation from tickets or implementation specs.

Route immediately after classification:

- Shared architecture: `../unity-game-foundations/SKILL.md`
- 2D implementation: `../unity-2d-game/SKILL.md`
- 3D implementation: `../unity-3d-game/SKILL.md`
- 3D asset preparation: `../unity-3d-asset-pipeline/SKILL.md`
- UI surfaces: `../unity-ui/SKILL.md`
- Sprite asset work: `../unity-sprite-pipeline/SKILL.md`
- Verification: `../unity-playtest/SKILL.md`
- Ticket-scoped work: `../unity-ticket-implementation/SKILL.md`

Keep one coherent plan across routed skills. Do not let design intent, implementation ticket scope, asset pipeline, UI, and verification drift apart.

## Default Workflow

1. Inspect the Unity project before making claims:
   - Read `ProjectSettings/ProjectVersion.txt` when available.
   - Check packages, input setup, render pipeline, existing tests, and relevant scenes/prefabs/assets.
2. Lock the game fantasy, player verbs, camera model, core loop, failure states, progression, and intended play session length.
3. Treat prototype specs as intent. Treat implementation specs, tickets, acceptance criteria, and current project state as implementation truth.
4. Choose the Unity path:
   - Use `unity-2d-game` for sprites, Tilemaps, 2D physics, side-view, top-down, grid, tactics, or 2D action.
   - Use `unity-3d-game` for 3D movement, camera, materials, lighting, colliders, 3D physics, or prefab composition.
   - Use `unity-3d-asset-pipeline` when the main task is import/runtime readiness rather than gameplay code.
5. Define UI early through `unity-ui` when the feature has HUD, menus, dialogs, pause, inventory, settings, or input focus concerns.
6. Close with `unity-playtest` before calling work production-ready.

## Safety Rules

- Do not silently invent game design decisions such as win/loss rules, abilities, stats, level layouts, economy values, camera feel, enemy behavior, or tuning values.
- Keep implementation ticket-scoped. Avoid broad refactors, package swaps, Project Settings edits, render pipeline edits, or scene/prefab rewrites unless the ticket requires them.
- State why any `.unity`, `.prefab`, `.asset`, `.meta`, `ProjectSettings`, input asset, or URP asset change is necessary.
- Do not use renderer or presentation objects as gameplay source of truth. `SpriteRenderer`, `MeshRenderer`, `Animator`, `Camera`, `Canvas`, `ParticleSystem`, and VFX mirror state.

## Output Expectations

- For planning requests, return a Unity-specific plan with player intent, subsystem route, asset/UI implications, test approach, and explicit unknown design decisions.
- For implementation requests, route to `unity-ticket-implementation` when a ticket or implementation spec exists.
- For mixed requests, keep the Unity version and project conventions visible, and name any scene, prefab, settings, or asset import risks before changing them.

## References

- Routing and browser replacement map: `../../references/unity-routing.md`
- Architecture rules: `../../references/unity-architecture.md`
- Ticket safety: `../../references/unity-ticket-safety.md`
- Playtest checklist: `../../references/unity-playtest.md`
