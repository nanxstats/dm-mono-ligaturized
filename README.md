# DM Mono with Fira Code Ligatures

Patches DM Mono with Fira Code ligatures via Ligaturizer.
Runs on macOS with git and Homebrew.

## Setup

Install the ligaturized fonts from `fonts/` using your OS font manager.

### VS Code

In VS Code, press `Cmd` + `Shift` + `P`, search for
`Preferences: Open User Settings (JSON)`. In the opened `settings.json`,
set font family to `Liga DM Mono` and enable ligatures:

```json
"editor.fontFamily": "'Liga DM Mono', monospace",
"editor.fontLigatures": "'calt', 'liga'",
"terminal.integrated.fontFamily": "'Liga DM Mono', monospace",
```

### Ghostty

Open Ghostty settings (`Cmd` + `,`) and set font family to `Liga DM Mono`:

```json
font-family = Liga DM Mono
```

Press `Cmd` + `Shift` + `,` to reload the terminal with the new configuration.

## Build

```bash
make
```

The Makefile will:

- Clone Ligaturizer (plus only the `fonts/fira` submodule) and DM Mono.
- Patch Ligaturizer options to target DM Mono and drop selected ligatures.
- Run the Ligaturizer build.
- Copy the ligaturized DM Mono font files into `fonts/`.
- Remove the cloned sources.

### Dropped ligatures

These ligatures from Fira Code are intentionally omitted:

- `&&`
- `;;`
- `.?`
- `?:`
- `?=`
- `?.`
- `??`

### Output

Ligaturized fonts land in `fonts/`:

- `LigaDMMono-Light.ttf`
- `LigaDMMono-LightItalic.ttf`
- `LigaDMMono-Regular.ttf`
- `LigaDMMono-Italic.ttf`
- `LigaDMMono-Medium.ttf`
- `LigaDMMono-MediumItalic.ttf`
