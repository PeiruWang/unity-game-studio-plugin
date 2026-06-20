---
name: unity-sprite-pipeline
description: Prepare Unity 6 sprites and 2D animation assets. Use for seed-frame consistency, full animation strips, slicing, pivots, pixels per unit, filter/compression settings, SpriteAtlas, Animator clips, prefab integration, URP 2D readiness, and sprite visual verification.
---

# Unity Sprite Pipeline

## Overview

Use this skill for Unity sprite generation, normalization, import, and animation readiness. This preserves the original sprite-pipeline idea of seed-frame consistency while ending in Unity-native import settings, pivots, PPU, SpriteAtlas, Animator clips, and prefab updates.

Do not generate frame-by-frame variants unless the user explicitly accepts drift.

## Core Workflow

1. Start from an approved in-game seed frame or existing shipped sprite.
2. Define Unity import expectations before generation or slicing:
   - Frame count, frame size, PPU, pivot, facing direction, palette, transparency, filter mode, compression, SpriteAtlas, and target prefab/Animator.
3. Generate or normalize the full strip as one coherent asset when image generation is needed.
4. Slice consistently:
   - Use one frame size and one pivot policy across the strip.
   - Preserve `.meta` stability when updating existing sprites.
5. Integrate only when scoped:
   - Animator clips, AnimationController changes, prefab SpriteRenderer references, sorting layers, materials, and SpriteAtlas membership must map to ticket acceptance.
6. Verify at game scale:
   - Check baseline, silhouette, pivot, animation timing, transparency, lighting/material compatibility, and scene readability.

## Responsibilities

- Sprite and strip consistency
- Unity sprite import guidance
- PPU, pivot, slicing, filter, compression, and SpriteAtlas expectations
- Animator clip and prefab integration when scoped
- URP 2D material/lighting compatibility when relevant

## Anti-Patterns

- Frame-by-frame generation causing character drift
- Casual PPU or pivot changes that break colliders, animation, or scene placement
- Updating prefab/Animator references without explaining why
- Treating sprite visual state as gameplay truth
- Replacing existing import conventions with a new pipeline during a narrow ticket

## Output Expectations

- Record import assumptions and any `.meta`, prefab, Animator, or SpriteAtlas changes.
- Require visual verification before declaring the asset ready.
- Route to `unity-2d-game` when gameplay behavior is required.

## References

- Sprite details: `../../references/unity-sprite-pipeline.md`
- 2D gameplay: `../unity-2d-game/SKILL.md`
- UI surfaces: `../unity-ui/SKILL.md`
- Ticket safety: `../../references/unity-ticket-safety.md`
