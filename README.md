# MoltBot - Auto Reply GitHub Issues

AI-powered bot that automatically responds to GitHub issues by moltgram using claude API.

## Features

- 🤖 Auto-reply to new issues
- 💬 Respond to issue comments
- 🏷️ Auto-label issues (bug, enhancement, question, etc.)
- 🧠 Context-aware responses using Claude AI

## Setup

### Step 1: Get Claude API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Create an API key
3. Copy the key (starts with `sk-ant-...`)

### Step 2: Add Secret to GitHub

1. Go to your repo: `https://github.com/moltgram/moltgram-frontend`
2. Click **Settings** → **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Name: `ANTHROPIC_API_KEY`
5. Value: paste your Claude API key
6. Click **Add secret**

### Step 3: Add Workflow File

1. In your repo, create folder: `.github/workflows/`
2. Add file `auto-reply-issue.yml` (copy from this folder)
3. Commit and push

```bash
cd moltgram-frontend
mkdir -p .github/workflows
cp auto-reply-issue.yml .github/workflows/
git add .github/workflows/auto-reply-issue.yml
git commit -m "Add MoltBot auto-reply workflow"
git push
```

### Step 4: Create Labels (Optional)

Create these labels in your repo for auto-labeling:

| Label | Color | Description |
|-------|-------|-------------|
| `bug` | `#d73a4a` | Something isn't working |
| `enhancement` | `#a2eeef` | New feature or request |
| `question` | `#d876e3` | Further information requested |
| `api` | `#0075ca` | API related |
| `frontend` | `#7057ff` | Frontend related |
| `documentation` | `#0075ca` | Documentation improvements |
| `needs-triage` | `#fbca04` | Needs review |

Go to: `https://github.com/moltgram/moltgram-frontend/labels`

## How It Works

1. User opens new issue → MoltBot replies with helpful response
2. User comments on issue → MoltBot responds to follow-up
3. MoltBot auto-detects issue type and adds labels

## Customization

Edit the `system` prompt in workflow file to customize MoltBot's personality and knowledge.


## Troubleshooting

**Bot not responding?**
- Check Actions tab for errors
- Verify `ANTHROPIC_API_KEY` secret is set
- Check API key is valid

**Labels not added?**
- Create labels manually first in repo settings
