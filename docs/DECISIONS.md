# Decisions

## D-001 — iPhone-first V1

**Status:** Accepted

V1 targets iPhone rather than Android.

Reasoning:

- Core Haptics provides a strong native API for complex tactile patterns.
- Apple hardware is more uniform, which matters when users are learning subtle tactile differences.
- Android remains a planned later target once the pulse-domain model is stable.

## D-002 — Native SwiftUI + Core Haptics

**Status:** Accepted

The haptic-critical path will use native Swift/SwiftUI/Core Haptics rather than Flutter or React Native for V1.

Reasoning:

- direct access to Core Haptics
- easier capability/error handling
- less abstraction between model and tactile output
- easier real-time parameter control

## D-003 — Data-driven pulse models

**Status:** Accepted

Pulse qualities must be represented as platform-independent data rather than hard-coded UI behavior.

The model should be versionable because tactile mappings will change during calibration.

## D-004 — Do not claim full reproduction of real pulse palpation

**Status:** Accepted

The product is a tactile learning abstraction. It cannot reproduce all clinically relevant factors such as tissue depth, arterial compliance, spatial motion, vessel wall tension under finger pressure, or true three-finger palpation mechanics.

Product copy and documentation must preserve this limitation.

## D-005 — Validate primitives before encoding all 28 pulses

**Status:** Accepted

The first real-device prototype will test basic tactile dimensions before assigning traditional pulse names. This prevents false confidence from encoding 28 labels before the haptic renderer itself is calibrated.

## D-006 — Repository is the canonical project memory

**Status:** Accepted

`PROJECT_STATE.md` is the canonical status handoff across ChatGPT/Codex conversations. Chat history is secondary.
