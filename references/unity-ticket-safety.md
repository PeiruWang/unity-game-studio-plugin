# Unity Ticket Safety

Use this reference whenever implementation is driven by a ticket, implementation spec, acceptance criteria, or bug report.

## Source Of Truth

- Prototype specs describe intent, mood, and possible direction.
- Implementation specs, tickets, acceptance criteria, and current project state control actual work.
- Existing project conventions beat new abstractions unless the ticket requires a change.

## Do Not Invent Design

Ask or state an explicit assumption when missing information would change player-facing behavior:

- Win/loss or failure state
- Ability effect or player verb
- Enemy behavior
- Level layout or spawn rule
- Camera feel
- Stats, economy, damage, cooldown, cost, duration, or balance values
- UI flow, priority, wording, or confirmation behavior
- Asset identity, scale, style, or animation meaning

## Scope Controls

Do not make these changes unless tied to acceptance criteria:

- Broad refactors
- Package changes
- Project Settings changes
- URP asset or renderer feature changes
- Input asset rewrites
- Scene rewrites
- Prefab rewrites
- Import setting or `.meta` churn
- Folder reorganizations
- Balance tuning
- Naming sweeps

## High-Risk Unity Files

Call out why any of these are touched:

- `ProjectSettings/`
- `Packages/manifest.json`
- `.unity`
- `.prefab`
- `.asset`
- `.inputactions`
- `.controller`
- `.anim`
- `.mat`
- `.meta`
- URP renderer or pipeline assets

## Implementation Report

When finishing a ticket, report:

- What acceptance criteria are satisfied
- Which assets and systems changed
- Which tests or PlayMode checks ran
- Which checks could not run and why
- Any remaining design assumptions
