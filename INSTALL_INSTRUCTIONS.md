# Installing the orb2 plugin in Claude

The plugin is a standard Claude plugin: a folder holding `.claude-plugin/plugin.json`
(the manifest) and `skills/` (orb, orbprint, orbengine). Both `orb2.plugin` and
`orb2.zip` in this folder are the same zip archive of it; `plugin-files\orb2\` is
the unpacked copy, ready to use as-is.

---

## Option A — Cowork / the Claude desktop app  (easiest)

1. Open a Cowork chat.
2. Drag `orb2.plugin` into the chat (or attach it) and say: **"install this plugin."**
3. Or skip the file entirely and say:
   "Install the plugin from the folder `C:\Users\<you>\Desktop\Orb Plugin\plugin-files\orb2`."
4. Verify: ask **"what plugins do I have?"** — `orb2` should appear.
5. Use it: type `/orb` (live session), `/orbprint` (standalone HTML orb),
   or `/orbengine` (author .orb.txt terrain).

## Option B — Claude Code (terminal)

Plugins install from a *marketplace*, which can simply be a local folder that
contains plugin folders. `plugin-files\` here is exactly that.

From the shell:

    claude plugin marketplace add "C:\Users\<you>\Desktop\Orb Plugin\plugin-files"
    claude plugin install orb2

Or from inside a running session:

    /plugin marketplace add C:\Users\<you>\Desktop\Orb Plugin\plugin-files
    /plugin install orb2

Then restart the session. `/orb` shows up in the available skills.

---

## Troubleshooting

- **"Marketplace add" complains about the path** — point it at the folder that
  CONTAINS `orb2`, not at `orb2` itself. If it wants a manifest, create
  `plugin-files\.claude-plugin\marketplace.json` containing:

      { "name": "nathan-local", "plugins": [ { "name": "orb2", "source": "./orb2" } ] }

- **`/orb` doesn't trigger** — plugins load at session start; open a fresh chat.
- **Skill fires but behaves oddly** — make sure the whole folder copied, especially
  `skills\orbengine\references\` (placement is computed by a script that must travel
  with the skill).
- **Sharing with someone else** — send them `orb2.plugin` plus this file. Nothing
  else is needed; the plugin is fully self-contained.

---

orb2 v1.2.1 — the Informational Dimensions orb navigator. Up is broader, down is
deeper, left and right go around, forward and backward run along consequence.
