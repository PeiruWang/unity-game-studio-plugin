# Contributing

Thank you for improving Unity Game Studio. Keep contributions focused on Unity-first game workflows and preserve the clear boundary between planning guidance, implementation guidance, and verification guidance.

## Contribution Guidelines

- Keep the plugin Unity-first. Do not add Phaser, Three.js, React, Vite, DOM, browser canvas, or Playwright assumptions unless they are explicitly framed as things this Unity plugin replaces.
- Prefer project-specific Unity conventions over broad new abstractions.
- Keep skills scoped and route work through the umbrella `unity-game-studio` skill when a request spans multiple Unity subsystems.
- Document why any new skill or reference file exists and which Unity workflow it supports.
- Update `README.md` when adding, removing, or renaming skills.
- Update `NOTICE.md` if attribution or upstream inspiration changes.
- Keep license references consistent with the MIT license declared in `.codex-plugin/plugin.json` and `LICENSE`.

## Documentation Style

- Use concise English.
- Prefer Unity terms over browser-game terms.
- Avoid wording that implies this project is affiliated with, sponsored by, or endorsed by OpenAI.
- Keep examples practical and tied to Codex plugin usage.
