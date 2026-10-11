# AGENTS.md

This repository is designed for continuous development across multiple ChatGPT/Codex conversations.

## Mandatory startup sequence

Before editing code or documentation:

1. Read `PROJECT_STATE.md`.
2. Read `docs/ARCHITECTURE.md`.
3. Read `docs/DECISIONS.md`.
4. Read `docs/RESEARCH_EXISTING_PROJECTS.md` when work touches prior art, haptics, pulse modeling, or platform choices.
5. Inspect the relevant implementation files before changing them.

Do not rely on chat history as the primary project state.

## Mandatory finish sequence

After a meaningful development batch:

1. Update `PROJECT_STATE.md` with:
   - what changed
   - current phase
   - what was validated
   - unresolved questions/risks
   - exact next step
2. Add or update an entry in `docs/DECISIONS.md` when an architectural or product decision changes.
3. Keep platform-independent pulse data separate from platform-specific haptic rendering.
4. Avoid claiming phone haptics reproduce real clinical pulse palpation.

## Engineering principles

- iPhone-first for V1.
- Native Swift/SwiftUI/Core Haptics for the haptic-critical path.
- Data-driven pulse definitions, not hard-coded per-screen behavior.
- One source model should drive both visual waveform and haptic rendering where practical.
- Build the learning loop before adding diagnosis/health claims.
- Prefer small testable milestones over broad feature implementation.
- Real-device haptic validation is required before declaring a pulse model acceptable.

## Working definition of done

A feature is not considered fully validated when it only works in a simulator if its value depends on haptics. Haptic features require iPhone testing and feedback to be marked validated.
