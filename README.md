# Unity Game Studio Plugin

Unity Game Studio is a Codex plugin for planning, implementing, and verifying Unity game workflows. It adapts the workflow-routing idea from OpenAI's browser-focused Game Studio plugin into a Unity-first skill set for Unity 6, C#, scenes, prefabs, ScriptableObjects, uGUI, asset pipelines, and Unity Test Framework verification.

This project is independently maintained by PeiruWang. It is inspired by and adapted from OpenAI's Game Studio plugin, but it is not affiliated with, sponsored by, or endorsed by OpenAI.

## What It Provides

- Unity workflow routing for early game planning and implementation triage.
- Unity 2D guidance for sprites, Tilemaps, Physics2D, Animator, URP 2D, and camera work.
- Unity 3D guidance for GameObjects, prefabs, materials, cameras, colliders, Rigidbody or CharacterController workflows, Animator, and URP.
- Unity UI guidance for uGUI HUDs, menus, pause screens, dialogs, inventory, settings, Canvas layout, EventSystem, and input focus.
- Asset pipeline guidance for 3D models, textures, materials, animation clips, prefabs, LOD, import settings, and validation.
- Sprite pipeline guidance for seed frames, sprite strips, slicing, pivots, pixels per unit, SpriteAtlas, and Animator integration.
- Ticket-scoped implementation safety for Unity work driven by specs, issues, or acceptance criteria.
- Playtest guidance for EditMode tests, PlayMode tests, scene boot checks, console review, Game view QA, and input smoke tests.

## Installation

Install this repository as a local Codex plugin using the plugin directory that contains `.codex-plugin/plugin.json`.

The plugin manifest points Codex at:

- `.codex-plugin/plugin.json` for plugin metadata.
- `skills/` for the available Unity workflow skills.
- `references/` for shared Unity implementation and verification guidance.

After installation, ask Codex for Unity game planning or implementation help. The umbrella skill routes work to the most specific Unity specialist skill.

Example prompts:

```text
Plan a Unity game workflow and implementation path.
```

```text
Implement this Unity ticket using existing project conventions and include PlayMode verification.
```

```text
Review this Unity UI flow for input focus, safe area, and playfield readability.
```

## Skills

| Skill | Purpose |
| --- | --- |
| `unity-game-studio` | Umbrella router for Unity game planning across architecture, 2D, 3D, UI, assets, tickets, and playtesting. |
| `unity-game-foundations` | Architecture planning for simulation versus presentation boundaries, MonoBehaviours, ScriptableObjects, scenes, prefabs, input, save, debug, and tests. |
| `unity-2d-game` | Unity 2D implementation guidance for sprites, Tilemaps, Physics2D, SpriteRenderer, Animator, URP 2D, input, scenes, and prefabs. |
| `unity-3d-game` | Unity 3D implementation guidance for GameObjects, prefabs, MeshRenderer, materials, Animator, colliders, physics, cameras, URP, and input. |
| `unity-3d-asset-pipeline` | Runtime-readiness guidance for models, textures, materials, import settings, animation clips, prefabs, LOD, colliders, and validation. |
| `unity-ui` | Unity uGUI guidance for HUDs, menus, pause, dialogs, inventory, settings, Canvas layout, EventSystem, safe area, and input focus. |
| `unity-sprite-pipeline` | Sprite generation and import workflow guidance for frame consistency, slicing, pixels per unit, pivots, SpriteAtlas, and Animator integration. |
| `unity-ticket-implementation` | Scope-control guidance for implementing Unity tickets from specs, acceptance criteria, or bug reports. |
| `unity-playtest` | Structured Unity QA guidance for EditMode tests, PlayMode tests, scene boot, console logs, visual checks, input, camera, physics, and UI. |

## Project Layout

```text
.
├── .codex-plugin/
│   └── plugin.json
├── references/
│   └── unity-*.md
├── skills/
│   └── unity-*/SKILL.md
├── CONTRIBUTING.md
├── LICENSE
├── NOTICE.md
└── README.md
```

- `.codex-plugin/plugin.json` declares the plugin metadata, interface labels, keywords, and MIT license identifier.
- `skills/` contains Codex skill entrypoints.
- `references/` contains shared Unity-specific guidance used by the skills.
- `LICENSE` contains the MIT license for this repository.
- `NOTICE.md` records upstream inspiration and attribution.

## License And Attribution

This repository is licensed under the MIT License. See [LICENSE](LICENSE).

This project is inspired by and adapted from OpenAI's Game Studio plugin in the `openai/plugins` repository. See [NOTICE.md](NOTICE.md) for attribution details.
