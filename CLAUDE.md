# CLAUDE.md

This file gives AI assistants context about this repository's purpose, structure, and conventions.

## Repository Overview

This is the **GitHub profile repository** (`jbaker75/jbaker75`). The `README.md` at the root is automatically rendered on the owner's GitHub profile page. It doubles as a project planning space for personal coding projects.

## File Structure

```
jbaker75/
├── README.md    # GitHub profile page content
├── poa.txt      # Plan of action for Csound IDE projects
└── CLAUDE.md    # This file
```

## Project Goals (from poa.txt)

The primary focus is building **simple Csound IDEs/editors** across multiple platforms. Each implementation should support:

- Load, edit, and save `.csd` files or raw Csound code
- Execute Csound and display output to the user
- Play audio output from Csound
- View waveforms (graphical capability)
- Standard IDE look and feel: scrollable panes, modular panes, etc.

### Target Platforms / Technologies

| Technology | Notes |
|---|---|
| Matlab Interface | Native Matlab GUI tooling |
| Python / TKinter | Standard cross-platform Python GUI |
| Java Interface | Swing or JavaFX |
| C/C++ simple UI | Lightweight native UI |
| C/C++ JUCE | Audio-focused framework |
| Python / Textualize | Terminal UI (Textual framework) |

### Constraints

- Must be **multiplatform**
- Target **Csound 7.0** where possible
- Graphical capabilities required (waveform display at minimum)
- Use AI as a tool, but learn each platform's APIs from documentation
- UI tooling must be **out of the box** for the given technology (no extra UI deps beyond the primary framework)
- Standard IDE look and feel

### Nice-to-Have

- External MIDI support (keyboard input)

### Inspiration

- Csound Web IDE (expand on it)

## Development Conventions

### Branching

- Default branch: `main`
- Feature/task branches follow the pattern: `claude/<short-description>-<id>` (e.g., `claude/add-claude-documentation-jUDLd`)
- Always develop on a dedicated branch; never commit directly to `main`

### Commit Style

- Imperative mood, present tense: "Add poa.txt", "Update README"
- Keep messages concise (one line for small changes; add a blank line + details for larger ones)
- No ticket/issue references required for this personal repo

### README.md

The `README.md` renders directly on the GitHub profile. Keep it:
- Concise and personal in tone
- Free of technical jargon aimed at profile visitors
- Updated to reflect current interests and projects as they evolve

### poa.txt

This is a living planning document. Update it when:
- A new implementation target is added or removed
- Constraints or goals change
- A platform implementation is completed or abandoned

## Working With Csound

Csound `.csd` files use an XML-like structure with `<CsoundSynthesizer>`, `<CsOptions>`, `<CsScore>`, and `<CsInstruments>` sections. When helping with Csound-related code:

- Prefer Csound 7.x API/opcodes unless a platform requires an older version
- The Csound API is available as a C library with bindings for Python (`ctcsound`), Java, and others
- JACK or PortAudio are typical audio backends for desktop implementations

## Notes for AI Assistants

- This repo currently contains **no source code** — only planning docs and the profile README. New implementations will each likely live in their own repository or subdirectory.
- When adding new platform implementations, create a subdirectory per technology (e.g., `csound-tkinter/`, `csound-juce/`).
- Do not modify `README.md` content without explicit instruction, as it directly affects the public GitHub profile.
- Keep `poa.txt` as plain text; do not convert it to Markdown.
