---
name: unity-3d-asset-pipeline
description: Prepare Unity 6 3D assets for runtime use. Use for model import settings, scale, pivots, materials, textures, animation clips, avatar setup, prefab creation, LOD, colliders, compression, URP compatibility, and validation of 3D assets before gameplay integration.
---

# Unity 3D Asset Pipeline

## Overview

Use this skill for Unity 3D assets, not gameplay runtime code. The goal is a predictable runtime-ready Unity asset: correct import settings, scale, pivots, materials, animation clips, colliders, LOD strategy, and prefab structure.

Do not preserve the browser assumption that GLB or glTF is the runtime contract. In Unity, follow existing project import conventions and produce Unity-ready prefabs and assets.

## Default Workflow

1. Inspect existing asset conventions:
   - Source formats, import presets, material workflow, URP shaders, scale units, pivots, avatar setup, animation clip naming, LOD, colliders, prefab variants, and folder layout.
2. Identify the runtime contract:
   - Which prefab or scene consumes the asset.
   - Whether gameplay needs colliders, sockets, animation events, root motion, hitboxes, VFX anchors, or material variants.
3. Prepare import settings deliberately:
   - Scale, axes, normals/tangents, mesh compression, read/write, materials, textures, rig type, animation clips, and `.meta` stability.
4. Create or update prefab structure only when scoped:
   - Name child objects meaningfully.
   - Keep sockets, colliders, renderers, and animator references predictable.
5. Validate in Unity:
   - Inspect prefab, materials, animation clips, colliders, LODs, scene placement, console logs, and representative Game view.

## Responsibilities

- Model and texture import readiness
- URP material compatibility
- Prefab creation or prefab variant updates
- Collider, trigger, socket, and hitbox setup when scoped
- LOD and compression policy
- Animation clip setup and avatar/root-motion expectations
- Asset naming and folder convention alignment

## Anti-Patterns

- Runtime code compensating for bad scale, pivot, collider, or material setup
- Changing import settings because they look cleaner, without acceptance criteria
- Replacing project material/shader conventions casually
- Treating source DCC structure as the Unity runtime hierarchy by default
- Updating gameplay prefabs without stating why the asset requires it

## Output Expectations

- List all `.fbx`, `.obj`, `.blend`, texture, material, prefab, `.meta`, or importer changes and why they are needed.
- Preserve existing project conventions.
- Route to `unity-3d-game` when the task becomes gameplay behavior.

## References

- 3D asset details: `../../references/unity-3d-asset-pipeline.md`
- 3D gameplay: `../unity-3d-game/SKILL.md`
- Architecture rules: `../../references/unity-architecture.md`
- Ticket safety: `../../references/unity-ticket-safety.md`
