# Tern

A macOS terminal for working with coding agents, built on [Ghostty](https://ghostty.org):
Warp-style tabs and panes in a sidebar, live terminals you can move between panes, tabs and
windows, a Markdown editor beside your terminals, and a `tern` command line that agents (and you)
can drive everything from.

This repository only hosts releases. Apple Silicon Macs, macOS 13 or later.

## Install

Paste this into Terminal:

```sh
curl -fsSL https://github.com/alejoacelas/tern/releases/latest/download/install.sh | bash
```

It downloads the latest release (and checks it against the release's checksum), puts `Tern.app`
in `/Applications` (or `~/Applications`), clears the download quarantine so macOS opens it
without asking, links the `tern` command into `~/.local/bin`, makes Tern the app for Markdown
files, and opens it. Nothing else needs to be installed first.

Run `tern doctor` to see what Tern can find on this machine (`claude`, `codex`, `git`).

## Updates

Tern checks this repository's latest release in the background, verifies a new version's
signature, and installs it when you quit Tern. "Check for Updates…" in the Tern menu, or
`tern update` (`--check` to only look, `--now` to install and relaunch at once), do the same on
demand. Tern never quits by itself to install an update.

## Uninstall

```sh
rm -rf /Applications/Tern.app ~/.local/bin/tern ~/Library/Application\ Support/Tern
```

## License

MIT, like Ghostty: see [LICENSE](LICENSE). Fonts embedded in the app are under the licenses in
[licenses/](licenses/).
