---
name: unity-game-foundations
description: Set Unity 6 game architecture before implementation. Use when the user needs simulation versus presentation boundaries, MonoBehaviour policy, ScriptableObject usage, scene or prefab ownership, Input System action maps, camera model, save/debug/perf strategy, or PlayMode/EditMode test strategy.
---

# Unity Game Foundations

## Overview

Use this skill to establish Unity architecture before implementation starts. Unity projects become hard to maintain when gameplay rules, renderer objects, UI state, input plumbing, scenes, prefabs, and save data all become one mutable surface.

Default rule: simulation owns gameplay truth; Unity objects adapt that truth into scene, prefab, physics, animation, audio, camera, and UI presentation.

## Architecture Rules

1. Separate simulation from presentation.
   - Simulation owns rules, progression, scoring, AI decisions, inventory, quest state, saveable state, and deterministic outcomes.
   - Presentation owns GameObjects, Renderers, Animators, Cameras, Canvases, particles, VFX, audio, and visual feedback.
2. Keep MonoBehaviour boundaries narrow.
   - Use MonoBehaviours for Unity lifecycle, serialized references, input bridges, physics bridges, view binding, and scene orchestration.
   - Keep complex rules in plain C# systems or small components that can be tested without a live scene when practical.
3. Use ScriptableObjects for authored data.
   - Good uses: abilities, item definitions, enemy stats, level config, tuning tables, catalogs, and shared immutable references.
   - Do not treat ScriptableObject assets as mutable runtime state unless the ticket explicitly concerns editor tooling.
4. Treat scenes and prefabs as owned assets.
   - Scenes compose levels and entry points.
   - Prefabs define reusable GameObject hierarchies.
   - State why any scene, prefab, `.asset`, `.meta`, Project Settings, input asset, or URP asset change is needed.
5. Keep input mapping explicit.
   - Prefer Input System action maps for gameplay and UI.
   - Gate gameplay input while menus, dialogs, inventory, or pause UI own focus.
6. Define save/debug/perf boundaries up front.
   - Save serializable runtime data, not UnityEngine object references.
   - Keep debug overlays and perf probes toggleable.
   - Use Unity Profiler, Frame Debugger, Rendering Debugger, logs, and target builds before tuning.

## Implementation Checklist

Define these before core code:

- Player fantasy and primary verbs
- 2D or 3D route
- Camera model
- Input action map and UI focus policy
- Simulation state owner
- MonoBehaviour adapter boundary
- Scene and prefab ownership
- ScriptableObject data shape
- UI surfaces
- Save data boundary
- EditMode and PlayMode verification

## Anti-Patterns

- Game rules hidden inside renderer, camera, animator, or UI callbacks
- Scene hierarchy as gameplay source of truth
- Global manager sprawl without ownership
- Mutating ScriptableObject assets as runtime save state
- Hardcoded input reads scattered across gameplay scripts
- Reworking folder layout, packages, Project Settings, or prefabs during a narrow feature ticket

## Output Expectations

- Produce a concise architecture plan with boundaries, likely touched assets, risks, and test strategy.
- Name design gaps instead of filling them silently.
- Route to the specific implementation skill once architecture is stable.

## References

- Unity architecture details: `../../references/unity-architecture.md`
- Ticket safety: `../../references/unity-ticket-safety.md`
- 2D patterns: `../../references/unity-2d.md`
- 3D patterns: `../../references/unity-3d.md`
- Playtest checklist: `../../references/unity-playtest.md`
