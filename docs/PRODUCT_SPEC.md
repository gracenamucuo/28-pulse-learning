# Product Specification

## Product intent

Help learners build a tactile vocabulary for traditional Chinese pulse qualities using repeatable phone haptics, guided comparisons, and blind practice.

## Non-goals for V1

- medical diagnosis
- replacing real pulse palpation
- claiming that Taptic Engine reproduces vascular mechanics
- automatic health recommendations
- cloud accounts or social features

## Primary user flows

### Learn

Select a pulse quality and see:

- name
- concise description
- classical metaphor/source note
- tactile dimensions represented by the app
- limitations of the simulation
- live visual waveform
- touch/hold to feel the pattern

### Explore

Adjust a small set of perceptual parameters in real time:

- tempo
- intensity
- sharpness
- pulse width
- regularity/variation
- superficial/middle/deep response

The app should make cause-and-effect obvious: changing a parameter immediately changes the tactile output and corresponding visualization.

### Compare

Practice commonly confused pairs or dimensions, for example:

- slow vs fast
- strong vs weak
- regular vs irregular
- later domain pairs such as slippery vs rough or wiry vs tight, only after their mappings are validated

### Blind test

Randomly play a pattern without showing its identity, ask the learner to identify it, then reveal the answer and key differentiating dimensions.

### Review

Track recurring confusions and prioritize future practice accordingly.

## Safety and wording

The app must describe its output as a tactile learning model or approximation, not as a clinical reproduction of a human pulse.

## V0.1 success criteria

Before adding all 28 named pulse qualities, the prototype must demonstrate on a real iPhone that users can reliably perceive differences among a small set of primitive patterns:

- slower vs faster
- weaker vs stronger
- softer vs sharper
- regular vs intentionally irregular

Only after this engine-level milestone should the project proceed to full traditional pulse mappings.
