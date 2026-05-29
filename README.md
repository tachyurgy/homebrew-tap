# tachyurgy/homebrew-tap

Homebrew tap for [**hey-claude**](https://github.com/tachyurgy/hey-claude) — say
*"Hey Claude, &lt;task&gt;"* and dispatch a [Claude Code](https://code.claude.com)
background agent. A fully on-device voice wake word for macOS.

## Install

```bash
brew install tachyurgy/tap/hey-claude
```

That's shorthand for:

```bash
brew tap tachyurgy/tap
brew install hey-claude
```

Then:

```bash
hey-claude doctor     # first-run check: mic, claude, model
hey-claude train      # get a free "hey claude" wake-word model (no mic)
hey-claude            # start listening
```

## What the formula installs

- **`portaudio`** — microphone capture (system dependency)
- **`python@3.12`** — a dedicated virtualenv for hey-claude
- the Python ML stack (`numpy`, `onnxruntime`, `openwakeword`, `mlx-whisper`),
  built into that venv at install time

It does **not** install [Claude Code](https://code.claude.com) itself — the
formula's caveats point you there. You need `claude` ≥ 2.1.139 on your PATH for
`claude --bg`.

## Formulae

| Formula | Description |
|---|---|
| [`hey-claude`](Formula/hey-claude.rb) | On-device "Hey Claude" voice wake word → `claude --bg` |

## Maintenance

The formula is bumped automatically: publishing a release on the
[hey-claude repo](https://github.com/tachyurgy/hey-claude) triggers a workflow
that opens a version + sha256 bump PR here. See
[RELEASE.md](https://github.com/tachyurgy/hey-claude/blob/main/RELEASE.md).

> Note: a Homebrew tap and the release tarball it points at must be **public**
> for `brew install` to work.

## License

MIT — see [LICENSE](LICENSE). hey-claude itself is also MIT.
