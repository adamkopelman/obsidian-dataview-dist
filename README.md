# Dataview 0.5.70 — release build for second-brain

> **This is not the official Dataview repository.** It holds the unmodified release files of
> **[Dataview](https://github.com/blacksmithgu/obsidian-dataview)** by Michael Brenan (blacksmithgu), MIT-licensed, so that
> [second-brain](https://github.com/adamkopelman/second-brain) can pin them as an optional git
> submodule at `.obsidian/plugins/dataview`. For documentation (https://blacksmithgu.github.io/obsidian-dataview/), support, bug reports
> and newer versions go to **[blacksmithgu/obsidian-dataview](https://github.com/blacksmithgu/obsidian-dataview)** — all credit belongs to its authors.

In second-brain, Dataview powers the live `Dashboard.md` (required for it).

## Why this repo exists
Obsidian loads a community plugin from `main.js`, `manifest.json` and `styles.css` in
`<vault>/.obsidian/plugins/dataview/`. Upstream keeps its sources in git and publishes those built
files only as release assets, so the upstream repository can't be used as that folder directly.
This repo contains exactly those three files from release [`0.5.70`](https://github.com/blacksmithgu/obsidian-dataview/releases/tag/0.5.70), byte for byte, plus
this README, upstream's license and ignore rules. Nothing was modified.

| File | sha256 |
| --- | --- |
| `main.js` | `6bb1cf7010afad830e73575fca0e2bfbd3279c562e3d9d24f2d2f45161eb7d00` |
| `manifest.json` | `9235db47112da81b85591c79ecb9ae2574e5e72207056e976472f90616286185` |
| `styles.css` | `3306dd9032e00f989ba7233a37fd255bc4d3f4340cee661762e952f3f6aa1de9` |

Upstream's 0.5.70 release ships a `manifest.json` that still says `"version": "0.5.68"`; it is kept exactly as released.

## Your settings stay local
Obsidian saves the plugin's settings to `data.json` in this folder; `.gitignore` ignores it and
everything else the plugin writes here, so your settings (including any API keys) are never
committed. second-brain's own settings for this plugin are not stored here: they live in the vault at
`.claude/skills/gtd-setup/scaffold/plugin-data/dataview/data.json` and are copied into this
folder by `python .claude/skills/gtd-setup/apply.py .` (never over settings you already have).

## Alternative: install from Obsidian
Skip this submodule and install **Dataview** from Settings → Community plugins → Browse; Obsidian
puts it in the same folder.

## Updating
```sh
gh release download <tag> --repo blacksmithgu/obsidian-dataview --pattern main.js --pattern manifest.json --pattern styles.css --clobber
```
Update the version and hashes above, commit, and bump the submodule in second-brain.

## License
MIT — [`LICENSE`](LICENSE) is copied verbatim from
[blacksmithgu/obsidian-dataview at `0.5.70`](https://github.com/blacksmithgu/obsidian-dataview/blob/0.5.70/LICENSE.txt) (Copyright (c) 2021 Michael Brenan).
