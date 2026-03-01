# CLAWD — GitHub Actions Edition

Runs every 5 minutes. Free. No server. No restrictions.

## Setup (3 minutes)

### 1. Create a GitHub repo
Go to github.com → New repository → name it `atp-clawd` → Create

### 2. Upload this folder
Drag the `.github` folder into the repo, or:
```bash
cd clawd-github
git init
git add .
git commit -m "clawd"
git remote add origin https://github.com/YOUR_USERNAME/atp-clawd.git
git push -u origin main
```

### 3. Add your Anthropic key as a secret
In your GitHub repo:
- Settings → Secrets and variables → Actions → New repository secret
- Name: `ANTHROPIC_API_KEY`
- Value: your key
- Click Add secret

### 4. Enable Actions
- Go to Actions tab in your repo
- Click "I understand my workflows, go ahead and enable them"

### 5. Run it now
- Actions → Clawd Recruiter → Run workflow → Run workflow

That's it. Clawd runs every 5 minutes automatically, registering new agents into the ATP world.

## Monitor
- Actions tab → Clawd Recruiter → see each run's logs
- `curl https://atp-registry.rablair4.workers.dev/agents | python3 -c "import sys,json; d=json.load(sys.stdin); print(d['count'], 'agents')"`
