# MIDI Sequencer — Product Requirements Document

## Overview

A browser-based (or desktop) MIDI sequencer that lets users compose, arrange, and play back step-sequenced MIDI patterns without needing a DAW.

---

## Goals

- Allow musicians and hobbyists to quickly sketch MIDI patterns
- Provide an intuitive, low-friction interface for step sequencing
- Export patterns as standard MIDI files for use in other tools

## Non-Goals

- Full DAW functionality (audio recording, mixing, effects)
- VST/AU plugin hosting
- Cloud sync or collaboration features (v1)

---

## Users

- Hobbyist musicians experimenting with composition
- Producers sketching beat or melody ideas
- Developers building on top of MIDI tooling

---

## Core Features

### 1. Step Sequencer Grid
- Configurable grid: rows = notes/pitches, columns = steps (default 16)
- Toggle individual steps on/off
- Adjustable number of steps per pattern (8, 16, 32, 64)

### 2. Playback
- Play, pause, and stop controls
- Adjustable BPM (tempo)
- Loop mode (loop current pattern continuously)

### 3. Instruments / Tracks
- Multiple tracks (at least 4 in v1), each with an independent pattern
- Per-track: MIDI channel assignment, note range, and velocity

### 4. Pattern Management
- Create, duplicate, delete, and rename patterns
- Chain patterns into a song arrangement

### 5. MIDI Output
- Send MIDI to connected hardware or virtual MIDI devices
- Export patterns as `.mid` files

### 6. Basic UI Controls
- Keyboard shortcuts for play/stop, tempo nudge, step toggle
- Visual playhead showing current step during playback

---

## Nice-to-Have (v2+)

- Per-step velocity and note length editing
- Probability per step (stochastic sequencing)
- MIDI input recording (capture live playing into a pattern)
- Chord mode (trigger multiple notes per step)
- Swing/groove quantization
- Undo/redo history

---

## Technical Considerations

- **Platform**: TBD — browser (Web MIDI API) or desktop (Electron / native)
- **MIDI**: Web MIDI API for browser; node-midi or similar for Node/Electron
- **State management**: patterns stored as plain JSON for easy import/export
- **Audio clock**: use `AudioContext` (Web Audio API) for tight timing in browser

---

## Open Questions

- [ ] Browser-only vs. desktop app vs. both?
- [ ] Should the sequencer include a built-in synth/sampler, or output MIDI only?
- [ ] What is the target step resolution — 16th notes only, or variable subdivisions?
- [ ] Any accessibility requirements (screen reader, color-blind modes)?
- [ ] Monetization model — free, freemium, one-time purchase?

---

## Success Metrics

- User can create and play back a 16-step pattern within 2 minutes of opening the app
- Exported `.mid` file plays correctly in a standard DAW
- Playback timing jitter < 5ms

---

## Milestones

| Phase | Scope | Target |
|-------|-------|--------|
| v0.1 | Single-track 16-step grid, play/stop, BPM control | — |
| v0.2 | Multi-track, MIDI output, export `.mid` | — |
| v0.3 | Pattern chaining, velocity editing | — |
| v1.0 | Polished UI, keyboard shortcuts, documentation | — |
