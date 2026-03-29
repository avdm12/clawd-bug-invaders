---
name: invaders
description: >
  Launch Clawd Invaders, a retro Space Invaders browser game starring Clawd the pixel crab.
  Use this skill when the user types /invaders, asks to play the bug game, wants to play an
  arcade game, mentions Clawd Invaders, or asks for an easter egg.
allowed-tools: Bash
disable-model-invocation: true
---

# Clawd Invaders Launcher

Launch the pre-built Clawd Invaders game in the user's default browser.

## Steps

1. Copy the game file to a temporary location using the plugin root path:
   ```bash
   cp "${CLAUDE_SKILL_DIR}/game.html" /tmp/clawd-invaders.html 2>/dev/null || cp ~/.claude/skills/invaders/game.html /tmp/clawd-invaders.html
   ```

2. Open in the default browser using platform detection:
   ```bash
   if [[ "$OSTYPE" == "darwin"* ]]; then
     open /tmp/clawd-invaders.html
   elif [[ "$OSTYPE" == "linux-gnu"* ]]; then
     xdg-open /tmp/clawd-invaders.html
   elif [[ "$OSTYPE" == "msys" ]] || [[ "$OSTYPE" == "cygwin" ]]; then
     start /tmp/clawd-invaders.html
   fi
   ```

3. Print a fun launch message:
   "Clawd Invaders launched! Defend the codebase from bugs! Arrow keys to move, Space to shoot."
