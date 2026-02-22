---

## Step 3 — Deploy to Vercel (Free)

1. Go to [vercel.com](https://vercel.com) and sign up with your GitHub account
2. Click **"Add New Project"**
3. Import your GitHub repository
4. Before clicking Deploy, go to **"Environment Variables"** and add:
   - **Key:** `ANTHROPIC_API_KEY`
   - **Value:** `sk-ant-...` (your key from Step 2)
5. Click **Deploy** — Vercel builds it in ~30 seconds
6. You'll get a live URL like `https://bracket-guru-xyz.vercel.app` 🎉

---

## Step 4 — Test It

Open your Vercel URL and ask the bot:
- *"Who should I pick to win the national championship?"*
- *"Best upset picks in the first round?"*
- *"Tell me about Houston's defense this year"*

---

## Updating the Bot

Any time you push changes to GitHub, Vercel automatically redeploys. No manual steps needed.

To change what the bot knows or how it responds, edit the `systemPrompt` variable in `api/chat.js`.

---

## Customization Tips

**Change the bot's name:** Edit `Bracket Guru` in `index.html` (search for "BracketGuru" and "Bracket Guru")

**Add conversation memory:** Currently each message is standalone. To add memory, store previous messages in the frontend and send them as an array to the API.

**Add live stats:** Sign up for a free ESPN API or SportsRadar trial, fetch current rankings, and inject them into the system prompt in `api/chat.js`.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "Network error" | Make sure `vercel.json` is in the repo root |
| "API key not configured" | Check the Environment Variable is set in Vercel dashboard |
| Bot gives outdated info | Claude's training has a cutoff — for live data, integrate a stats API |
| Vercel build fails | Check the Vercel logs for the specific error |
