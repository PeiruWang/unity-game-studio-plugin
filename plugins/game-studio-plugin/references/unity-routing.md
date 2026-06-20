# Unity Routing And Browser Replacement Map

Use this reference when adapting browser-game guidance into Unity 6 workflows.

## Browser Assumptions To Remove

- Phaser as the default 2D runtime.
- Three.js, React Three Fiber, raw WebGL, Babylon.js, and PlayCanvas as runtime choices.
- TypeScript, Vite, React state, npm, DOM, CSS, canvas, and browser app shell assumptions.
- DOM HUD layered over a canvas or WebGL playfield.
- Playwright, browser screenshots, DOM assertions, WebGL context-loss handling, SpectorJS, and browser performance tooling as default QA.
- Rapier JS, GLTFLoader, DRACOLoader, KTX2Loader, and browser GLB/glTF runtime-loader assumptions.

## Unity Equivalents

| Original concept | Browser meaning | Unity equivalent | Risk |
|---|---|---|---|
| Game Studio umbrella | Route browser stack | `unity-game-studio` | Route by subsystem and ticket type |
| 2D default: Phaser | Sprite/tile browser runtime | `unity-2d-game` | Do not carry Phaser scene assumptions |
| 3D plain TS/Vite | Three.js imperative runtime | `unity-3d-game` | Use Unity camera, physics, prefabs, URP |
| 3D React | R3F with shared React state | Unity scene plus UI/state bridges | No React state assumptions |
| 3D asset pipeline | GLB/glTF optimization | `unity-3d-asset-pipeline` | Follow Unity import conventions |
| Raw WebGL/shaders | Custom renderer | URP Shader Graph, HLSL, renderer features | Project-level changes need scope |
| DOM HUD | Browser overlay | uGUI Canvas and EventSystem | UI Toolkit only if chosen |
| Phaser Scene | Browser scene lifecycle | Unity Scene plus bootstrap MonoBehaviours | Scene edits are high-risk |
| Three scene graph | WebGL object graph | GameObject hierarchy and prefabs | Hierarchy is not save truth |
| Rapier JS | Browser physics | Unity Physics, Physics2D, CharacterController | Do not swap physics model casually |
| Pointer lock | Browser camera capture | Input System action-map gating | Gameplay and UI maps must not fight |
| Playwright QA | Browser automation | Unity Test Framework plus Game view QA | Visual checks may remain manual |
| SpectorJS | WebGL frame capture | Unity Profiler and Frame Debugger | Measure before tuning |
| Asset manifest keys | TS indirection | Serialized refs, ScriptableObject catalogs, Addressables if existing | Do not invent asset architecture |
| Sprite strip output | Browser sprite asset | Unity import settings, pivots, PPU, Animator clips | `.meta` changes matter |
| Save state | Serializable JS | Serializable C# DTOs | Never save renderer/scene objects as truth |

## Routing Defaults

- Route architecture questions to `unity-game-foundations`.
- Route sprite, Tilemap, 2D physics, and 2D camera work to `unity-2d-game`.
- Route 3D movement, camera, physics, materials, prefabs, and world features to `unity-3d-game`.
- Route model/import/prefab-readiness tasks to `unity-3d-asset-pipeline`.
- Route HUD, menus, pause, dialogs, inventory, settings, and input focus to `unity-ui`.
- Route seed-frame, sprite-strip, slicing, PPU, pivot, SpriteAtlas, and Animator asset tasks to `unity-sprite-pipeline`.
- Route verification to `unity-playtest`.
- Route ticket-driven implementation to `unity-ticket-implementation`.

## Default Questions

Ask only when the answer affects implementation:

- What is the intended player verb or state change?
- Which scene or prefab owns this feature?
- Is this a 2D or 3D camera/control problem?
- What is authoritative: simulation, physics, animation event, input action, or UI command?
- Which acceptance criteria prove this ticket is done?
