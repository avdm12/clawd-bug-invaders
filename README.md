# Clawd Invaders

A retro Space Invaders game starring **Clawd**, the Claude Code pixel crab mascot. Defend the codebase from bugs!

![Clawd Invaders gameplay](clawd-invaders.gif)

Built as a Claude Code plugin — install it and type `/invaders` to play.

## Installation

### Option A: Plugin (recommended)

```
/plugin marketplace add avdm12/clawd-invaders
/plugin install clawd-invaders@avdm12
```

Then play with `/clawd-invaders:invaders` (plugin skills are namespaced as `plugin-name:skill-name`).

### Option B: Direct install (for `/invaders` without namespace)

```bash
git clone https://github.com/avdm12/clawd-invaders.git /tmp/clawd-invaders
mkdir -p ~/.claude/skills/invaders
cp /tmp/clawd-invaders/skills/invaders/* ~/.claude/skills/invaders/
```

Then play with just `/invaders` in any session.

## Game Features

- **10 waves** of increasingly difficult bug invaders
- **3 enemy types**: green beetles (10pts), purple moths (20pts), red centipedes (30pts)
- **Mystery bug** bonus target (50-300pts)
- **Wave 10 boss fight** against the Mega Bug (500pts)
- **Full chiptune audio** via Web Audio API (shoot, hit, explosions, march beat, jingles)
- **CRT scanline effect** with vignette for retro arcade feel
- **High score** saved to localStorage
- **Victory screen** — "CODEBASE DEFENDED!"

## Controls

| Key | Action |
|-----|--------|
| Arrow keys / A, D | Move left / right |
| Space | Shoot |
| Enter | Start / Restart |

Touch controls supported on mobile.

## How It Works

The plugin bundles a self-contained HTML5 Canvas game (~41KB, zero external dependencies). When `/invaders` is invoked, Claude copies the game to `/tmp/` and opens it in the default browser.

## Repository Structure

```
clawd-invaders/
├── .claude-plugin/
│   ├── plugin.json           # Plugin metadata
│   └── marketplace.json      # Marketplace catalog
├── skills/
│   └── invaders/
│       ├── SKILL.md           # Skill definition
│       └── game.html          # Self-contained game
├── README.md
└── LICENSE
```

## Color Palette

The game uses Claude's brand colors:

| Color | Hex | Use |
|-------|-----|-----|
| Clawd Orange | `#D77757` | Player character |
| Crail | `#C15F3C` | Laser, accents |
| Pampas | `#F4F3EE` | UI text |
| Cloudy | `#B1ADA1` | Secondary text |

## License

MIT
