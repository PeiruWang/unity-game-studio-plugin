---
name: unity-3d-game
description: Implement ticket-scoped Unity 6 3D gameplay with C#, GameObjects, prefabs, MeshRenderer, materials, Animator, colliders, Rigidbody or CharacterController, cameras, URP, Input System actions, ScriptableObjects, scenes, and PlayMode or EditMode verification. Use for first-person, third-person, traversal, exploration, combat, vehicle, and 3D world features.
---

# Unity 3D Game

## Overview

Use this skill for Unity 3D implementation. This replaces the browser Three.js and React Three Fiber paths with Unity-native scenes, prefabs, GameObjects, cameras, URP, materials, Animator, colliders, physics, C# systems, and Unity verification.

3D support is first-class. Do not downgrade 3D requests into 2D defaults, and do not keep browser renderer assumptions such as WebGL scene graphs, DOM HUDs, GLTF runtime loaders, Rapier JS, or SpectorJS.

## Workflow

1. Inspect project conventions:
   - Unity version, URP setup, packages, assemblies, input assets, relevant scenes, prefabs, materials, physics layers, and tests.
2. Lock design facts before coding:
   - Camera model, movement model, interaction verbs, physics authority, collision expectations, animation meaning, UI focus behavior, and acceptance criteria.
3. Define ownership:
   - Simulation or gameplay systems own rules and saveable state.
   - MonoBehaviours own Unity lifecycle, serialized references, input/physics/view bridges, and scene composition.
   - Meshes, materials, renderers, animation clips, cameras, lights, VFX, and particles are presentation unless the ticket explicitly makes physics authoritative.
4. Choose controller boundaries deliberately:
   - Use existing project controller patterns first.
   - Do not switch between CharacterController, Rigidbody, root motion, or custom kinematic control as incidental cleanup.
5. Verify in PlayMode when scene integration matters:
   - Check scene boot, input, camera, colliders, animation transitions, UI focus, logs, and target frame cost where relevant.

## 3D Responsibilities

- First-person, third-person, orbit, rail, vehicle, traversal, exploration, and 3D combat features
- Camera model and camera/readability boundaries
- Collider and physics integration through existing project conventions
- Prefab composition and serialized reference wiring
- Animator and visual state derived from gameplay state
- URP materials, lights, volumes, and renderer features only when scoped
- Input System action maps and UI/gameplay focus transitions

## Anti-Patterns

- Mesh hierarchy, material state, Animator state, or camera transform as gameplay truth
- Changing model scale, colliders, materials, lighting, URP assets, controller physics, or camera feel without ticket scope
- Runtime code compensating for import mistakes that belong in asset setup
- Shipping large scene/prefab rewrites during a narrow feature ticket
- Guessing camera feel, combat values, or enemy behavior when the design is unspecified

## Output Expectations

- Produce implementation tied to the ticket, with explicit scene/prefab/material/input risks.
- Prefer project conventions over new architecture.
- Include EditMode tests for pure rules and PlayMode checks for scene, camera, input, physics, animation, and UI integration where feasible.

## References

- Shared architecture: `../unity-game-foundations/SKILL.md`
- 3D implementation notes: `../../references/unity-3d.md`
- 3D asset pipeline: `../unity-3d-asset-pipeline/SKILL.md`
- UI surfaces: `../unity-ui/SKILL.md`
- Playtest checklist: `../../references/unity-playtest.md`
