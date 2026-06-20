# Unity Architecture Rules

Use these rules before implementing Unity gameplay.

## Simulation Versus Presentation

Simulation owns:

- Rules, outcomes, turns, timers, progression, scoring, objectives, inventory, quests, abilities, AI decisions, saveable state, and deterministic gameplay outcomes.

Presentation owns:

- GameObject hierarchy, SpriteRenderer, MeshRenderer, Animator, Camera, Canvas, ParticleSystem, VFX, audio, materials, lighting, and visual feedback.

Presentation can mirror state and emit explicit commands. It must not become the source of gameplay truth.

## MonoBehaviour Boundaries

Use MonoBehaviours for:

- Unity lifecycle
- Serialized references
- Scene bootstrap
- Input bridges
- Physics bridges
- Animation and visual adapters
- UI adapters
- Camera adapters

Prefer plain C# systems for:

- Rules
- Data transformations
- Save models
- Ability and combat outcomes
- Turn or objective logic
- Validation that can run in EditMode tests

## ScriptableObject Usage

Use ScriptableObjects for authored data and shared immutable runtime references:

- Abilities
- Items
- Enemy definitions
- Level or encounter config
- Tuning tables
- Catalogs
- Spawn definitions

Avoid mutating ScriptableObject assets as runtime state. If the runtime needs mutable data, copy authored data into a runtime model.

## Scene And Prefab Ownership

- Scenes compose levels, menus, entry points, and integration surfaces.
- Prefabs define reusable GameObject hierarchies and serialized wiring.
- Prefab variants are valid when the project already uses them or the variation is a stable product concept.
- State why any `.unity`, `.prefab`, `.asset`, `.meta`, Project Settings, package, input asset, or URP asset change is required.

## Input Mapping

- Prefer the Input System when the project uses it or the target workflow requires it.
- Keep gameplay and UI action maps separate.
- Gate gameplay actions while pause, inventory, dialogs, menus, or settings own focus.
- Avoid hardcoded input reads scattered across gameplay scripts.

## Camera

Choose and document one camera model early:

- Fixed
- Follow
- Room-based
- Tactical pan
- Orbit
- Third-person
- First-person
- Rail

Camera transforms are presentation. They are not the source of gameplay truth.

## Save, Debug, And Performance

- Save serializable runtime data, not UnityEngine object references.
- Keep debug overlays and diagnostic toggles scoped and easy to disable.
- Use Unity Profiler, Frame Debugger, Rendering Debugger, Stats, logs, and target builds for performance or rendering claims.
- Measure before tuning.

## Verification

- Use EditMode tests for pure systems and data validation.
- Use PlayMode tests for scene, prefab, input, physics, animation, camera, and UI integration.
- If tests are impractical, perform a structured manual PlayMode pass and report the gap.
