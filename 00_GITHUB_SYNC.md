# GitHub Sync Configuration

## Repository
- **URL:** https://github.com/kinglex1/PhyLo-Founder-Sprints
- **Branch:** main

## Token
```
[YOUR_GITHUB_TOKEN]
```
**Important:** Replace `[YOUR_GITHUB_TOKEN]` with your actual GitHub Personal Access Token before pushing.

## Sync Instructions for All Agents

### To Push Work to GitHub:
```bash
cd /workspace/dashboard
git add -A
git commit -m "[AGENT-ID] Task description"
git push https://[YOUR_GITHUB_TOKEN]@github.com/kinglex1/PhyLo-Founder-Sprints.git main
```

### To Pull Latest from GitHub:
```bash
cd /workspace/dashboard
git pull https://[YOUR_GITHUB_TOKEN]@github.com/kinglex1/PhyLo-Founder-Sprints.git main
```

### First Time Setup (if .git doesn't exist):
```bash
cd /workspace/dashboard
git init
git config user.email "agent@project-central.ai"
git config user.name "Project Central Agent"
git remote add origin https://github.com/kinglex1/PhyLo-Founder-Sprints.git
git branch -M main
git add -A
git commit -m "Initial commit"
git push https://[YOUR_GITHUB_TOKEN]@github.com/kinglex1/PhyLo-Founder-Sprints.git main --force
```

## Last Synced
2026-05-26 - Initial push completed
