# DM Mono with Fira Code Ligatures

Automates building DM Mono fonts with Fira Code ligatures via Ligaturizer.
Runs on macOS with git and Homebrew.

## Usage

```bash
make
```

The Makefile will:

- Clone Ligaturizer (plus only the `fonts/fira` submodule) and DM Mono.
- Patch Ligaturizer options to target DM Mono and drop selected ligatures.
- Run the Ligaturizer build.
- Copy the ligaturized DM Mono font files into `fonts/`.
- Remove the cloned sources.

## Dropped ligatures

These ligatures from Fira Code are intentionally omitted:

- `&&`
- `;;`
- `.?`
- `?:`
- `?=`
- `?.`
- `??`

## Output

Ligaturized fonts land in `fonts/`:

- `LigaDMMono-Light.ttf`
- `LigaDMMono-LightItalic.ttf`
- `LigaDMMono-Regular.ttf`
- `LigaDMMono-Italic.ttf`
- `LigaDMMono-Medium.ttf`
- `LigaDMMono-MediumItalic.ttf`
