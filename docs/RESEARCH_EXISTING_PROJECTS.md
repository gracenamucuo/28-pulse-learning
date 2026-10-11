# Existing Project Research

Research date: 2026-10-11

## Summary

Open-source prior art exists for TCM pulse acquisition/classification and for rich phone haptics, but no reviewed repository currently combines the complete learning scope of this project.

## Relevant repositories

### ZengWeiTHU/TCM_Pulse_Diagnosis

Direction: TCM pulse-diagnosis hardware/instrument project, including Arduino/C++ work.

Useful to us:

- evidence that pulse work often benefits from dedicated hardware
- possible future reference for acquisition/physical simulation concepts

Not directly reusable for:

- iPhone tactile learning
- 28-pulse Core Haptics rendering
- comparison/blind training

### SPA3K/tcm-pulse-web

Direction: Apple Health/ECG feature extraction and TCM pulse classification/analysis.

Useful to us:

- structured pulse taxonomy
- explicit distinction between pulse properties that can and cannot be inferred from simple wearable data
- terminology and knowledge-structure references

Not directly reusable for:

- tactile playback
- superficial/middle/deep phone simulation
- haptic training

Important caution: classification heuristics in third-party projects are not automatically clinical ground truth.

### SPA3K/qihuang-watch

Direction: SwiftUI/HealthKit health-analysis app.

Useful to us:

- Swift project organization references
- XcodeGen-based project generation pattern

Not a haptic pulse simulator.

### XcodesOrg / general Core Haptics examples / heartbeat AHAP projects

Direction: mature examples for custom haptic patterns, heartbeat patterns, AHAP playback, and cross-platform fallbacks.

Useful to us:

- do not reinvent low-level pattern playback
- reference implementation ideas for heartbeat-like envelopes
- proof that custom AHAP/Core Haptics patterns are practical

## Gap this project targets

No reviewed project provides the same combined product:

```text
28 traditional pulse qualities
        +
parameterized tactile model
        +
Core Haptics iPhone playback
        +
synchronized educational waveform
        +
superficial/middle/deep abstraction
        +
A/B comparison
        +
blind identification
        +
error-focused training
```

## Reuse strategy

Reuse concepts and proven platform techniques, not product assumptions.

- Reuse Core Haptics patterns/engine practices.
- Reuse project-generation and test patterns where licenses permit.
- Use existing pulse taxonomies as research references.
- Build our own versioned pulse-learning schema and training system.
- Record license/source provenance before copying any code or data.
