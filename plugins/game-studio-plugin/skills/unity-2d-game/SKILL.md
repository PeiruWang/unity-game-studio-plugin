---
name: unity-2d-game
description: Implement ticket-scoped Unity 6 2D gameplay with C#, sprites, Tilemaps, SpriteRenderer, Animator, Physics2D, URP 2D, Input System actions, scenes, prefabs, ScriptableObjects, and PlayMode or EditMode verification. Use for top-down, side-view, grid, tactics, and sprite-based Unity game work.
---

# Unity 2D Game

## Overview

Use this skill for Unity 2D implementation. This replaces the browser Phaser path with Unity-native sprites, Tilemaps, prefabs, C# gameplay systems, 2D physics, URP 2D, Input System, and PlayMode/EditMode verification.

Keep gameplay truth outside renderer objects. `SpriteRenderer`, `Animator`, `Tilemap`, particles, camera, and uGUI should mirror state, not own core rules.

## Workflow

1. Inspect the existing project conventions before editing:
   - Unity version, assemblies, packages, render pipeline, input setup, relevant scenes, prefabs, ScriptableObjects, and tests.
2. Confirm ticket scope:
   - Player verb, gameplay state change, acceptance criteria, scene/prefab touch points, and expected verification.
3. Choose the implementation boundary:
   - Plain C# system for rules, scoring, inventory, turns, cooldowns, ability outcomes, or deterministic logic.
   - MonoBehaviour adapter for lifecycle, serialized references, input, physics, view updates, and scene wiring.
4. Keep assets explicit:
   - Sprites need PPU, pivot, slicing, compression, filter mode, SpriteAtlas, and Animator ownership considered before import changes.
   - Tilemaps need grid/cell sizing, collision, sorting layers, and level ownership documented.
5. Verify with focused tests:
   - EditMode for pure rules and data validation.
   - PlayMode for scene, prefab, input, physics, animation, and UI integration.

## 2D Responsibilities

- Sprite-based gameplay and presentation bridges
- Top-down, side-view, grid, tactics, platformer, and lightweight combat loops
- Tilemap and level composition changes when scoped
- 2D camera behavior and readability
- Animator state derived from gameplay state
- Physics2D integration through a clear authority boundary
- URP 2D lighting only when already in scope or project conventions require it

## Anti-Patterns

- Gameplay rules living in `Update` because it is convenient
- `SpriteRenderer`, `Animator`, or Tilemap state as save truth
- Changing pivots, PPU, sorting layers, physics layers, or import settings without stating why
- Hardcoded keyboard/controller reads instead of action maps
- Broad prefab or scene rewrites during a narrow ticket
- Tweaking balance values outside acceptance criteria

## Output Expectations

- Keep changes tied to the ticket or implementation spec.
- Name any scene, prefab, sprite import, `.meta`, input asset, or Project Settings changes before making them.
- Include test coverage or a concrete reason why only manual PlayMode verification is feasible.

## References

- Shared architecture: `../unity-game-foundations/SKILL.md`
- 2D implementation notes: `../../references/unity-2d.md`
- Sprite pipeline: `../unity-sprite-pipeline/SKILL.md`
- UI surfaces: `../unity-ui/SKILL.md`
- Ticket safety: `../../references/unity-ticket-safety.md`
