# Unity Sprite Pipeline

Use this reference for sprite generation, import, slicing, and animation readiness.

## Seed-Frame Rule

Start from an approved in-game frame whenever possible. Preserve:

- Silhouette
- Palette
- Facing direction
- Costume and proportions
- Readable key features
- Transparent background
- Game-scale readability

Generate whole strips in one pass when image generation is needed. Frame-by-frame generation drifts easily.

## Unity Import Decisions

Define these before import or slicing:

- Frame count
- Frame size
- Pixels per unit
- Pivot policy
- Filter mode
- Compression
- Alpha handling
- SpriteAtlas membership
- Material or URP 2D lighting expectations
- Sorting layer/order
- Target Animator clips
- Target prefab references

## Slicing And Animation

- Use one frame size across a strip.
- Use one shared pivot policy across the strip.
- Keep frame timing readable at game scale.
- Keep Animator state derived from gameplay or adapter state.
- Do not update Animator controllers or prefabs unless scoped.

## Verification

- Baseline consistency
- Pivot consistency
- No frame-to-frame size drift
- Transparency preserved
- Action readable at game scale
- Collider or hitbox alignment still valid
- Prefab and Animator references intact
