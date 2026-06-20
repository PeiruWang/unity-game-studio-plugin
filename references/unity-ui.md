# Unity UI Notes

Use this reference for Unity uGUI work.

## Default Stack

Default to uGUI for this skill family:

- Canvas
- RectTransform
- CanvasScaler
- GraphicRaycaster
- EventSystem
- InputSystemUIInputModule when using Input System

Use UI Toolkit only when the existing project or ticket explicitly chooses it.

## Layout Rules

- Protect the playfield first.
- Keep critical information visible and secondary surfaces collapsible.
- Avoid dense always-on panels during normal movement.
- Use anchors, layout groups, and CanvasScaler intentionally.
- Check representative aspect ratios and safe area needs.
- Prevent text overflow in buttons, labels, panels, and prompts.

## State Binding

- UI reads gameplay state through a view model, adapter, presenter, or existing project pattern.
- UI sends commands or actions back to gameplay.
- UI must not own gameplay truth or save data.

## Input Focus

- Disable or gate gameplay action maps while modal UI owns focus.
- Enable UI action maps and selection state deliberately.
- Pause camera/look input under menus, inventory, dialogs, and settings.
- Restore previous gameplay input state when UI closes.

## Verification

- Game view aspect checks
- Navigation/focus checks
- Pause/menu input checks
- Text overflow checks
- Console log review
- Playfield obstruction review
