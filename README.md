# PlantScore — Vercel Deployment

A mobile-first plant display audit app powered by Claude AI.

## Project structure

```
plantscore/
├── api/
│   └── messages.js      ← Vercel serverless proxy (keeps API key server-side)
├── public/
│   └── index.html       ← Full PlantScore app (single file)
├── vercel.json          ← Routing config
└── README.md
```

## Deploy to Vercel

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "Initial PlantScore deploy"
git remote add origin https://github.com/YOUR_USERNAME/plantscore.git
git push -u origin main
```

### 2. Deploy on Vercel
1. Go to [vercel.com](https://vercel.com) and sign in
2. Click **New Project** → Import your GitHub repo
3. Leave all build settings as default
4. Click **Deploy**

### 3. Add your API key
1. In your Vercel project → **Settings** → **Environment Variables**
2. Add: `ANTHROPIC_API_KEY` = `your_anthropic_api_key_here`
3. Click **Save** then **Redeploy**

### 4. Done
Vercel gives you a permanent URL like `https://plantscore.vercel.app`
Bookmark it on every device or add to your phone's home screen.

## Local development
```bash
npm install -g vercel
export ANTHROPIC_API_KEY=your_key_here
vercel dev
```
Then open http://localhost:3000

## Features
- Setup screen: site name, zone, auditor name
- Audit tab: camera capture + file upload, AI scoring per image
- Notes tab: per-zone notes included in summaries
- History tab: all assessments grouped by zone with thumbnails
- Report tab: download full PDF audit report (client-side, no server)
- Zone management: switch zones mid-audit at any time
- Zone summary + site summary AI generation
