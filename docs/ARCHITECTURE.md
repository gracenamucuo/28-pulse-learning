# Architecture

## Design objective

Represent a pulse quality as data, then render that same conceptual model into:

1. haptic output on iPhone
2. synchronized visual waveform
3. learning/training metadata

## High-level flow

```text
PulseModel
   |
   +--> HapticRenderer (Core Haptics)
   |
   +--> WaveformRenderer (SwiftUI/Canvas)
   |
   +--> LearningMetadata
   |
   +--> TrainingEngine
```

## Core modules

### PulseDomain

Platform-independent definitions:

- pulse identity
- rate/tempo
- rhythm/regularity
- amplitude/strength envelope
- sharpness envelope
- pulse width / duration
- attack / decay characteristics
- optional beat-to-beat variation
- superficial/middle/deep response values
- confidence/representation notes
- source notes and version

The schema must distinguish between:

- classical/domain description
- haptic approximation
- measured/validated behavior

### Haptics

Native iOS Core Haptics implementation.

Responsibilities:

- convert PulseModel data into CHHapticPattern events/parameter curves
- start/stop/restart engine safely
- support real-time parameter exploration
- expose device capability/error state
- provide deterministic test patterns

### Waveform

Produces a visual representation from the same or derived envelope used by haptics.

The visual waveform is an educational visualization, not a diagnostic arterial pressure waveform unless explicitly sourced from measured data.

### Learning

Presents:

- pulse definition
- classical description
- representable tactile dimensions
- limitations of the phone simulation
- guided exploration

### Training

Modes:

- A/B comparison
- blind multiple choice
- targeted confusion-pair practice
- review based on past errors

### Persistence

V1 should remain local-first. Store:

- settings
- haptic calibration preferences
- practice history
- confusion matrix / error counts

No account or cloud backend is required for initial V1.

## Proposed source layout

```text
Sources/
  App/
  PulseDomain/
  Haptics/
  Waveform/
  Learning/
  Training/
  Persistence/
Resources/
  PulseModels/
Tests/
```

## Platform strategy

The pulse-domain schema must not depend on Core Haptics types. iOS-specific mapping belongs in `Haptics/`. A future Android renderer can consume the same domain model and degrade gracefully according to device vibration capabilities.

## Validation ladder

1. Unit-test pulse model parsing and envelope generation.
2. Validate visual waveform deterministically.
3. Validate Core Haptics engine behavior on a supported iPhone.
4. Calibrate a small set of primitive tactile dimensions.
5. Only then encode the complete 28-pulse catalog.
6. Perform domain review and iterative real-device comparison.
