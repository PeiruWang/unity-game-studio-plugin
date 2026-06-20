---
name: unity-ui
description: Design and implement Unity 6 uGUI interfaces. Use for HUDs, menus, pause, dialogs, inventory, settings, Canvas layout, EventSystem, Input System UI input, CanvasScaler, safe area, UI binding, visual hierarchy, and playfield-readable Unity game UI.
---

# Unity UI

## Overview

Use this skill for Unity visible interface work. The target workflow defaults to uGUI, not DOM overlays and not UI Toolkit unless the project or ticket explicitly chooses it.

Game UI should support the play experience, preserve the playfield, and coordinate cleanly with gameplay input.

## Workflow

1. Inspect existing UI conventions:
   - Canvas mode, CanvasScaler, anchors, safe area handling, fonts, prefabs, EventSystem, input module, UI controllers, and scene ownership.
2. Lock UI intent:
   - Critical information, secondary information, menu surfaces, interaction states, camera/input mode, and target resolutions.
3. Define binding boundaries:
   - UI reads view models or gameplay state adapters.
   - UI sends explicit commands or actions.
   - UI does not become gameplay source of truth.
4. Gate input:
   - Disable or pause gameplay action maps while menus, dialogs, inventory, or settings own focus.
   - Enable UI action maps and selection state deliberately.
5. Verify layout:
   - Check representative aspect ratios, safe area needs, text overflow, navigation, pause/focus behavior, and console logs.

## Responsibilities

- uGUI HUDs, menus, pause screens, dialogs, inventory, settings, prompts, and overlays
- Canvas hierarchy, anchors, CanvasScaler, safe-area patterns, and prefab reuse
- EventSystem and Input System UI integration
- UI state binding to gameplay systems
- Playfield protection and readability for both 2D and 3D games

## Anti-Patterns

- Generic dashboard UI that ignores game readability
- Dense overlays that hide the playfield during normal play
- UI state directly owning gameplay rules or save truth
- Changing UI framework, input module, fonts, or global Canvas settings outside scope
- Letting gameplay input remain active under modal UI
- Hero/marketing layouts instead of usable game surfaces

## Output Expectations

- Name Canvas, prefab, scene, input, and layout risks before editing.
- Keep persistent HUD minimal enough for the camera/viewpoint.
- Include PlayMode or manual Game view checks for focus, navigation, layout, and readability.

## References

- UI details: `../../references/unity-ui.md`
- Shared architecture: `../unity-game-foundations/SKILL.md`
- Playtest checklist: `../../references/unity-playtest.md`
- Ticket safety: `../../references/unity-ticket-safety.md`
