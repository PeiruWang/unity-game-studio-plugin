# Unity 3D Asset Pipeline

Use this reference when preparing 3D assets for Unity runtime use.

## Inspect First

Before changing imports, inspect:

- Existing source formats
- Import presets
- Units and scale
- Pivot/origin conventions
- Material and shader workflow
- Texture compression
- Rig type and avatar setup
- Animation clip naming
- LOD conventions
- Collider and socket conventions
- Prefab variant conventions

## Runtime-Ready Asset Requirements

A Unity 3D asset is runtime-ready when:

- Scale and pivot match gameplay use.
- Materials use project-appropriate shaders.
- Textures fit memory and visual needs.
- Animation clips are named and configured predictably.
- Colliders, triggers, sockets, hitboxes, and attach points are explicit when needed.
- LODs or mesh compression are considered for repeated or large assets.
- The prefab hierarchy is meaningful and stable.
- The asset has been checked in a representative scene or prefab context.

## Import Settings

Change import settings only for a scoped reason:

- Scale factor
- Normals and tangents
- Read/write
- Mesh compression
- Materials
- Rig and avatar
- Animation clip ranges
- Texture type, size, compression, color space, alpha, and mipmaps

`.meta` changes are implementation-significant and must be explained.

## Common Failure Modes

- Runtime code compensates for bad scale or pivot.
- Colliders do not match visible geometry.
- Materials import with wrong shader or color space.
- Animation clips are unnamed or have wrong loop/root motion settings.
- Prefab child names are unstable or DCC-driven.
- LOD and texture budgets are ignored until performance fails.
