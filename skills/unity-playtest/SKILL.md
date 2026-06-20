---
name: unity-playtest
description: Verify Unity 6 gameplay with structured QA. Use for EditMode tests, PlayMode tests, Unity Test Framework runs, scene boot checks, console log review, input smoke tests, prefab and UI validation, Game view visual review, camera readability, physics checks, and issue reporting.
---

# Unity Playtest

## Overview

Use this skill to test Unity games the way players experience them: scene boot, input, camera, UI focus, animation, physics, HUD readability, logs, and representative Game view states.

Prefer Unity Test Framework for repeatable checks. Use structured manual PlayMode review when deterministic automation is not practical.

## Preferred Workflow

1. Inspect available verification:
   - Test assemblies, EditMode tests, PlayMode tests, CI commands, Unity version, target platform, and existing QA scripts.
2. Run focused tests when feasible:
   - EditMode for pure systems and data validation.
   - PlayMode for scene, prefab, input, physics, animation, camera, and UI integration.
3. Boot the relevant scene and exercise the main verbs.
4. Review Unity console logs and missing-reference symptoms.
5. Check visual states:
   - HUD readability, camera framing, animation state, collider behavior, material/lighting regressions, and text/layout overflow.
6. Report findings by severity with reproduction steps and likely subsystem owner.

## Tooling Guidance

- Use Unity Test Framework commands when a Unity executable path is available.
- If command-line Unity is unavailable, state that and perform static or manual-review guidance from available project artifacts.
- Use Unity Profiler, Frame Debugger, Rendering Debugger, and Stats for performance or rendering issues rather than guessing.
- Do not use browser-only tools such as Playwright, SpectorJS, or DOM assertions unless the target is explicitly Unity WebGL and the ticket asks for browser QA.

## Common Checks

- Scene loads without console errors or missing references
- Main player verbs work from Input System actions
- Gameplay and UI action maps do not fight each other
- Camera framing matches the intended view
- Animations and VFX mirror gameplay state
- Colliders/triggers match visible objects
- HUD/menu/dialog layout is readable at target aspects
- Save/load uses serializable data, not scene objects
- Performance issues are measured before tuning

## Reporting Standard

Lead with findings:

- What the player sees
- How to reproduce it
- Why it matters
- Likely owner: simulation, MonoBehaviour bridge, scene/prefab, UI, asset import, rendering, input, physics, or tests

## References

- Full checklist: `../../references/unity-playtest.md`
- Architecture rules: `../../references/unity-architecture.md`
- UI cues: `../unity-ui/SKILL.md`
- Ticket safety: `../../references/unity-ticket-safety.md`
