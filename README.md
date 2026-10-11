# 28 Pulse Learning

An iPhone-first tactile learning system for the 28 traditional Chinese pulse qualities.

## Goal

Build a learning tool that turns pulse-quality models into synchronized haptic and visual waveforms, then teaches users through exploration, comparison, blind identification, and error-focused review.

The project is **not** intended to claim that a phone can fully reproduce a real radial pulse. The phone haptics are a training abstraction for selected perceptual dimensions such as rate, rhythm, strength, sharpness, pulse width, regularity, and relative response at superficial/middle/deep levels.

## Platform strategy

- V1: iPhone, native Swift + SwiftUI + Core Haptics
- V2: Android after the pulse model and training design are stable
- Pulse definitions must remain platform-independent so multiple renderers can reuse the same model

## Core product layers

1. Learn a pulse quality
2. Explore parameters interactively
3. Compare confusing pairs
4. Blind identification
5. Review based on confusion/error history

## Project continuity

Before making changes, read:

1. `AGENTS.md`
2. `PROJECT_STATE.md`
3. `docs/ARCHITECTURE.md`
4. `docs/DECISIONS.md`
5. `docs/RESEARCH_EXISTING_PROJECTS.md`

`PROJECT_STATE.md` is the canonical current-status file and must be updated after meaningful development batches.

## Current status

Research and architecture phase. No production app code has been committed yet.
