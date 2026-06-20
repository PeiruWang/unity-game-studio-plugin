# Unity 3D Implementation Notes

Use this reference for 3D gameplay features.

## Core Boundaries

- Simulation owns rules, objectives, abilities, AI, progression, and saveable state.
- MonoBehaviours bridge Unity lifecycle, input, physics, animation, camera, and scene composition.
- MeshRenderer, Animator, Camera, materials, lights, VFX, and particles are presentation.
- Physics may be authoritative only when the project design says so; isolate that boundary.

## Controller Policy

Use existing project patterns first:

- CharacterController
- Rigidbody
- Kinematic controller
- Root motion
- Vehicle controller
- Custom simulation controller

Do not switch controller models as incidental cleanup.

## Camera Policy

Document the camera model:

- First-person
- Third-person follow
- Orbit
- Rail
- Tactical
- Fixed
- Vehicle

Gate camera input when UI owns focus.

## Physics And Colliders

- Preserve physics layers and collision matrix assumptions.
- Keep visual mesh and collider responsibilities clear.
- Use triggers, hitboxes, hurtboxes, and interaction volumes deliberately.
- Do not fix asset scale or collider mismatch through unrelated gameplay code.

## URP And Presentation

- Treat URP asset, renderer feature, shader, lighting, and Volume changes as project-level changes.
- Prefer existing material and lighting conventions.
- Measure rendering/perf issues before changing pipeline settings.

## Verification

- EditMode: pure rules, data validation, state machines.
- PlayMode: scene boot, input, camera, physics, animation, UI focus, logs, and representative Game view.
