# Project State

Last updated: 2026-10-11

## Current phase

Phase 0 — prior-art research and product/technical architecture.

## Completed

- Repository created and GitHub App write access confirmed.
- Initial GitHub prior-art review completed.
- Decision made to build V1 for iPhone using native Swift + SwiftUI + Core Haptics.
- Decision made to keep pulse models platform-independent for future Android support.
- Project continuity rules established in `AGENTS.md`.

## Prior-art conclusion

Relevant open-source projects exist for:

- TCM pulse acquisition and classification
- Apple Watch/HealthKit-based pulse or health analysis
- Core Haptics/AHAP heartbeat patterns
- Cross-platform haptic rendering

No reviewed project currently provides the same combined scope:

- 28 pulse qualities
- iPhone tactile rendering
- superficial/middle/deep learning model
- synchronized waveform + haptic model
- comparison training
- blind identification
- confusion/error-focused review

Therefore the project should reuse proven haptic techniques but implement its own pulse-learning model and curriculum.

## Planned V1 architecture

- SwiftUI application shell
- Core Haptics renderer
- platform-independent `PulseModel`
- synchronized visual waveform renderer
- learning screen
- parameter exploration screen
- pairwise comparison screen
- blind test engine
- local training statistics

## Development/test environment

Primary real-device target:

- iPhone 11
- iOS 26.x

Primary Mac currently runs macOS Ventura through OpenCore Legacy Patcher. Real-device haptic validation will require a macOS/Xcode combination capable of running Xcode 26 or newer; this is an environment task, not an application architecture blocker.

## Not yet done

- No Swift project generated yet.
- No Core Haptics prototype committed yet.
- No canonical 28-pulse parameter schema finalized.
- No clinical/domain review of pulse parameter mappings yet.
- No real-device haptic calibration performed yet.

## Next exact step

Design the V0.1 pulse-domain schema and implement a minimal iPhone haptic laboratory before building the full 28-pulse catalog.

The first prototype should support only a few deliberately distinguishable patterns (for example slow/fast, strong/weak, regular/irregular) so the haptic engine can be validated independently of TCM terminology.

## Risks / open questions

1. Phone haptics cannot reproduce vessel compliance, tissue depth, spatial artery motion, or true finger pressure response.
2. Some traditional pulse qualities may be only partially representable through Taptic Engine dimensions.
3. Pulse definitions need domain validation; classical descriptions alone should not be treated as a measured ground truth.
4. Simulator-only validation is insufficient for haptic quality.
5. The development Mac may need an OCLP-supported Sequoia installation for Xcode 26.
