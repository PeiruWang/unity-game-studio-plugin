# Unity 2D Implementation Notes

Use this reference for sprite, Tilemap, 2D physics, and 2D camera work.

## Core Boundaries

- Gameplay systems own rules and saveable state.
- MonoBehaviours bridge input, physics, animation, sprites, camera, and scene references.
- SpriteRenderer, Animator, Tilemap, ParticleSystem, and uGUI mirror state.

## Sprite And Tilemap Checks

Before changing sprites or Tilemaps, inspect:

- Pixels per unit
- Pivot policy
- Slicing policy
- Filter mode and compression
- Sorting layers and order
- SpriteAtlas use
- Sprite material and URP 2D lighting
- Collider shape and generation
- Tilemap grid size and origin

## Physics2D

- Use existing Rigidbody2D, Collider2D, trigger, layer, and controller conventions first.
- Decide whether movement is physics-authoritative, kinematic, or simulation-authoritative.
- Do not derive gameplay truth from visual overlap alone.

## Animation

- Animator state should derive from gameplay state or adapter state.
- Animation events may notify gameplay only when that pattern already exists or the ticket requires it.
- Do not hide rules inside animation transitions.

## Camera

Choose fixed, follow, room-based, tactical pan, side-view, or top-down camera behavior explicitly.

## Verification

- EditMode: pure rules, data validation, state transitions.
- PlayMode: scene boot, input, physics, Tilemap collision, animation state, camera, HUD overlap.
