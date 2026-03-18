# Concept2Application AI Tool — Netlify Deployment

## Files in this folder
```
index.html                  ← The main app
netlify.toml                ← Routes /api/chat to the function
netlify/functions/chat.js   ← Serverless function (holds your API key securely)
```

---

## Step-by-Step Deployment (Netlify)

### 1. Get an Anthropic API Key
- Go to https://console.anthropic.com
- Sign in or create an account
- Navigate to "API Keys" and create a new key
- Copy it — you'll need it in step 4

### 2. Upload to GitHub (optional but recommended)
- Create a free account at https://github.com
- Create a new repository (e.g. "concept2application")
- Upload all files in this folder to the repository

### 3. Deploy to Netlify
- Go to https://netlify.com and create a free account
- Click "Add new site" → "Import an existing project"
- Connect your GitHub account and select your repository
- OR if you didn't use GitHub: click "Deploy manually" and drag this entire folder into Netlify

### 4. Add Your API Key (IMPORTANT)
- In your Netlify dashboard, go to your site
- Click "Site configuration" → "Environment variables"
- Click "Add a variable"
- Key: `ANTHROPIC_API_KEY`
- Value: paste your Anthropic API key
- Click "Save"

### 5. Redeploy
- Go to "Deploys" in your Netlify dashboard
- Click "Trigger deploy" → "Deploy site"
- Wait ~1 minute for it to finish

### 6. Open Your Site
- Netlify gives you a free URL like `https://your-site-name.netlify.app`
- Open it — the tool should be fully working!

---

## Troubleshooting
- **"API key not configured" error** → Make sure you added ANTHROPIC_API_KEY in environment variables and redeployed
- **Function not found** → Make sure the `netlify/functions/chat.js` file is present and the `netlify.toml` is in the root folder
- **Blank page** → Check the browser console (F12) for errors
