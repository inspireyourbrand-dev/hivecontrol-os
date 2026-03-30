# HiveClaw — GitHub Upload Guide

> Step-by-step instructions to upload HiveClaw to https://github.com/inspireyourbrand-dev

## Prerequisites

You need:
- **Git** installed (`git --version` to check)
- **GitHub CLI** installed (`gh --version` to check) — or you can use the GitHub web UI
- Logged into GitHub CLI (`gh auth login`) or have a personal access token

If you don't have the GitHub CLI:
```bash
# macOS
brew install gh

# Windows
winget install GitHub.cli

# Linux
sudo apt install gh

# Then authenticate
gh auth login
```

---

## Option A: Using GitHub CLI (Fastest)

Open a terminal, navigate to the HiveClaw folder, and run these commands in order:

### Step 1: Navigate to the project folder
```bash
cd /path/to/hiveclaw
```
(Replace with the actual path where your HiveClaw folder is on your computer)

### Step 2: Initialize Git
```bash
git init
git branch -M main
```

### Step 3: Create the GitHub repository
```bash
gh repo create inspireyourbrand-dev/hiveclaw \
  --public \
  --description "HiveClaw — OpenClaw soft fork with HiveControl OS multi-agent mission control and HiveWorkflow natural-language automation" \
  --source . \
  --remote origin
```

### Step 4: Stage all files
```bash
git add -A
```

### Step 5: Create the initial commit
```bash
git commit -m "feat: HiveClaw v0.1.0 — HiveControl OS + HiveWorkflow

Initial release of HiveClaw, an OpenClaw soft fork featuring:
- HiveControl OS: 9-screen web dashboard for multi-agent swarm management
- HiveWorkflow: Natural-language workflow builder with hardware-aware agent spawning
- Agent hierarchy: Orion orchestrator + 7 specialist agents
- Governor mode: API budget management and throttling
- Cross-screen event bus for live updates across all screens
- Full documentation, playbooks, and install scripts

Built by HivePowered.Ai"
```

### Step 6: Push to GitHub
```bash
git push -u origin main
```

### Step 7: Create the v0.1.0 release
```bash
gh release create v0.1.0 \
  --title "HiveClaw v0.1.0 — HiveControl OS" \
  --notes "## What's Included

### HiveControl OS (9 screens)
- **Dashboard** — System health, agent activity, alerts
- **Tasks** — Kanban board with drag-drop, priority, agent assignment
- **Calendar** — Cron jobs, heartbeats, scheduled operations
- **Memory** — Searchable journal with timeline, filters, pinned entries
- **Projects** — Progress tracking with linked tasks and docs
- **Documents** — Searchable library with preview panel
- **Team** — Agent org chart with role cards and mission statement
- **Office** — 2D pixel-art agent visualization
- **HiveWorkflow** — Chat with Orion, workflow decomposition, guided steps

### HiveWorkflow Engine
- Natural-language workflow decomposition (14 capability patterns)
- Hardware-aware agent spawning (CPU/RAM/GPU profiling)
- Dynamic agent creation with 10 templates
- Split-panel guided steps for human intervention
- Cross-screen event bus for live updates

### Infrastructure
- 8 agent definitions (Orion + 7 specialists)
- Governor mode (API budget management)
- Install, sync, and build scripts
- Playbooks for agent spawning, incident recovery, third-party vetting
- MIT License

Built by [HivePowered.Ai](https://www.hivepowered.ai)"
```

### Step 8: Add topic tags for discoverability
```bash
gh repo edit inspireyourbrand-dev/hiveclaw \
  --add-topic ai \
  --add-topic agents \
  --add-topic multi-agent \
  --add-topic swarm \
  --add-topic dashboard \
  --add-topic automation \
  --add-topic openclaw \
  --add-topic self-hosted \
  --add-topic workflow \
  --add-topic local-first
```

### Done!
Your repo is live at: **https://github.com/inspireyourbrand-dev/hiveclaw**

---

## Option B: Using GitHub Web UI

If you prefer the web interface:

### Step 1: Create the repository
1. Go to https://github.com/new
2. Repository name: `hiveclaw`
3. Description: "HiveClaw — OpenClaw soft fork with HiveControl OS multi-agent mission control"
4. Set to **Public**
5. Do NOT initialize with README (we already have one)
6. Click **Create repository**

### Step 2: Push from your computer
Open a terminal in the HiveClaw folder:

```bash
cd /path/to/hiveclaw

git init
git add -A
git commit -m "feat: HiveClaw v0.1.0 — HiveControl OS + HiveWorkflow"
git branch -M main
git remote add origin https://github.com/inspireyourbrand-dev/hiveclaw.git
git push -u origin main
```

### Step 3: Create a release
1. Go to https://github.com/inspireyourbrand-dev/hiveclaw/releases/new
2. Tag: `v0.1.0`
3. Title: "HiveClaw v0.1.0 — HiveControl OS"
4. Write release notes (copy from the gh command above)
5. Click **Publish release**

---

## After Upload: Recommended Next Steps

1. **Add a social preview image** — Go to Settings → Social Preview and upload a screenshot of the Dashboard screen

2. **Pin the repository** — Go to your profile and pin `hiveclaw` so it appears prominently

3. **Share the link** — Post to:
   - OpenClaw Discord: https://discord.com/invite/clawd
   - Reddit r/selfhosted, r/artificial
   - Twitter/X with tags: #OpenSource #AI #MultiAgent #SelfHosted

4. **Set up GitHub Pages** (optional) — To let people preview HiveControl OS in their browser:
   - Settings → Pages → Source: Deploy from branch → main → /hivecontrol
   - This makes the dashboard viewable at `https://inspireyourbrand-dev.github.io/hiveclaw/`

---

## File Summary (what you're uploading)

```
46 files, ~860KB total

hivecontrol/           — HiveControl OS (9 screens + app shell + libraries)
hiveworkflow/          — HiveWorkflow engine, hardware monitor, agent spawner
agents/                — 9 agent definitions (AGENTS.md + 8 individual specs)
skills/                — Governor mode, heartbeat, third-party vetting
playbooks/             — Incident recovery, agent spawning, vetting
scripts/               — Install, sync upstream, build scripts
branding/              — HivePowered theme CSS + logo SVG
docs/                  — Architecture, contributing, fork strategy
tasks/                 — Todo tracking, lessons learned
README.md              — Project overview with install instructions
LICENSE                — MIT
package.json           — npm metadata
hiveclaw.config.json   — Default configuration
.gitignore             — Standard ignore rules
```
