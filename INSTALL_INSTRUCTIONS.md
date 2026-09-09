# ORB plugin 1.3.0

By Informational Dimensions.

Use orb for live exploration, orbshare for ORB File 1 text sharing, and orbprint for optional custom HTML. The orbengine skill is retained only for explicitly requested legacy maintenance. New /orbtxt requests route to orbshare. Existing legacy terrain is not automatically compatible with the new file format.

No installation is needed for the simplest path: copy the public ORB prompt into your AI chat, explore a topic, then copy the ORB Share authoring brief into that same chat. Open the resulting .orb.txt at https://visualizationcreation.github.io/orb-share/tool.html or paste its JSON and save it. Prepare submission, sign in to GitHub, attach the saved file and send it for owner review. Previewing does not publish.

See the bundled orbshare references for the full supported format. Plugin imports depend on your host. Claude Code can load the extracted folder with `claude --plugin-dir /path/to/orb2`; see https://code.claude.com/docs/en/plugins. Keep older installed copies separate until you verify which version is active. No automatic installation or account permissions are granted by this archive.

## Archive contents

The extracted root contains .claude-plugin/plugin.json and skills/orb, skills/orbshare, skills/orbprint and skills/orbengine. Preserve references and scripts with each skill. The engine is legacy only. The manifest version must be 1.3.0. Hosts may namespace commands (for example /orb2:orbshare); use the skill name your host exposes. This site does not provide a pre-existing local plugin-files folder or install anything automatically.
