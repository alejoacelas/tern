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

## Agents

`tern claude "task"` and `tern codex "task"` start a Claude Code or Codex session that works in
the background and opens in its own interface in a new tab once its first turn is done. Agents can
supervise other agents with `tern agent` (`tern agent --help` explains it in one screen): start
sessions, wait for them, steer them with messages, read their replies, and show one to you.
`tern agent open SESSION` shows a session read-only in a pane, with a Take Over button.

To know what agents do in its terminals, Tern installs a small plugin for Claude Code and one for
Codex when it starts (in `~/.claude` and `~/.codex`, with the agents' own commands). They report
to Tern only inside Tern and do nothing anywhere else. `tern agent plugins` shows their state.

## Updates

Tern checks this repository's latest release in the background. When there's a newer version it
asks first, in a note at the bottom of the sidebar (Download, Later, Skip), and downloads nothing
until you say yes. "Check for Updates…" in the Tern menu, or `tern update`, also count as a yes.
A downloaded update's signature is verified, and it installs when you quit Tern (`tern update
--now` installs and relaunches at once). `tern update --check` looks for a newer version and
`tern update --status` says where things stand. Tern never quits by itself to install an update.

## Uninstall

```sh
tern agent plugins remove
rm -rf /Applications/Tern.app ~/.local/bin/tern ~/Library/Application\ Support/Tern
```

## License

MIT, like Ghostty: see [LICENSE](LICENSE). Fonts embedded in the app are under the licenses in
[licenses/](licenses/).
