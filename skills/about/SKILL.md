---
name: about
description: |
  Provides information about the bitwize-music plugin, its version, and its
  creator. Use when the user asks about the plugin, its purpose, version, or
  capabilities.
triggers:
  - "about"
od:
  mode: design-system
  category: audio-music
  upstream: "https://github.com/bitwize-music-studio/claude-ai-music-skills/tree/HEAD/skills/about"
  license: "CC0-1.0"
---
> Vendored from [bitwize-music-studio/claude-ai-music-skills](https://github.com/bitwize-music-studio/claude-ai-music-skills/tree/HEAD/skills/about) under CC0-1.0. Only the frontmatter was normalized for OpenDesign; the instructions below are upstream's.

Read the version from `${CLAUDE_PLUGIN_ROOT}/.claude-plugin/plugin.json` (the `version` field), then display:

## About bitwize-music

**Version:** (version from plugin.json)

**Who Am I**

I'm bitwize—a hacker who loves music and experimenting with new technology. When AI music generation tools started getting good, I couldn't resist seeing what was possible.

**Website:** https://www.bitwizemusic.com/

**Behind the Music:** https://www.bitwizemusic.com/behind-the-music/

**Discord:** https://discord.gg/dMURByGF

**Share What You Make:** Tag [@bitwizemusic](https://x.com/bitwizemusic) on X/Twitter with anything interesting you create!
