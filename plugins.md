# Installed plugins

Herdr plugins installed on this machine, in `~/.config/herdr/plugins.json`
install order. Each is pinned to a specific commit at install time; rerunning
the install command moves the pin to the source's current default branch tip.

| Plugin id | Source | Pinned commit | Install command |
| --- | --- | --- | --- |
| `annotate` | `github:plannotator/herdr-annotate` | `bccf884b874f5f39ccbef1bb6ac67625c5fb5d54` | `herdr plugin install plannotator/herdr-annotate` |
| `herdr-sidebar` | `github:alexarthurs/herdr-sidebar` (subdir `plugins/herdr-sidebar`) | `4faeea73503bcfb7e5ba72ef0c683649f64f74e5` | `herdr plugin install alexarthurs/herdr-sidebar/plugins/herdr-sidebar` |
| `herdr-navigator` | `github:thanhdat77/herdr-navigator` (ref `v0.3.3`) | `03b803a00341d58382b6cda70a7cd618af5b8806` | `herdr plugin install thanhdat77/herdr-navigator` |
| `gh-pr` | `github:wyattjoh/herdr-plugin-gh-pr` | `6fe22de9a90c569f2186595cfddc3707f55ba1bd` | `herdr plugin install wyattjoh/herdr-plugin-gh-pr` |
| `persiyanov.reviewr` | `github:persiyanov/herdr-reviewr` | `4c090225af706bf3aaa24b39fea890a72994f40f` | `herdr plugin install persiyanov/herdr-reviewr` |

## Notes

- `annotate`, `herdr-sidebar`, and `persiyanov.reviewr` build with a fetch or
  build script at install time (`bun`, `cargo`, or a fetched binary,
  depending on the plugin); their own `herdr-plugin.toml` documents the
  required toolchain.
- `herdr-navigator` and `herdr-sidebar` build with `cargo build --release`;
  Rust must be on `PATH` before install.
- Keybindings for every plugin action are recorded in
  [config/config.toml](./config/config.toml), not restated here.
