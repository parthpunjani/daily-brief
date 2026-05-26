# The Daily Brief — Australian Business Intelligence

A self-hosted, AI-powered daily financial briefing. Opens like a newspaper. Refreshes on demand. Secured with AES-256 encryption.

---

## What it does

Every time you open it (or hit Refresh), Claude researches and writes a fresh Australian business briefing covering:
- **Lead story** — the day's biggest business/market event
- **Live market data** — ASX 200, AUD/USD, Gold, Oil, RBA rate
- **Corporate news** — 4 key ASX stories with analysis
- **Policy & Economy** — RBA, inflation, government policy
- **What to watch** — upcoming events and risks

---

## Setup (5 minutes)

### Step 1 — Get your Anthropic API key
1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up / log in → API Keys → Create key
3. Copy the key (starts with `sk-ant-`)
4. Add $5–10 credit (each briefing costs ~$0.01–0.03)

### Step 2 — Put the file on GitHub Pages

1. Go to [github.com](https://github.com) and sign in (or create a free account)
2. Click **+** → **New repository**
3. Name it: `daily-brief` (must be public for free GitHub Pages)
4. Click **Create repository**
5. Click **uploading an existing file**
6. Drag and drop `index.html` from this folder
7. Click **Commit changes**
8. Go to **Settings** → **Pages** (left sidebar)
9. Under "Source" select **Deploy from a branch** → branch: `main` → folder: `/ (root)`
10. Click **Save**
11. Wait ~60 seconds, then your URL will appear:
    ```
    https://YOUR-USERNAME.github.io/daily-brief/
    ```

### Step 3 — Add to your phone home screen

**iPhone (Safari):**
1. Open the URL in Safari
2. Tap the Share icon → **Add to Home Screen**
3. Name it "Daily Brief" → Add

**Android (Chrome):**
1. Open the URL in Chrome
2. Tap ⋮ menu → **Add to Home screen**

**Desktop:**
- Bookmark the URL or pin the tab

---

## Security model

| What | How |
|------|-----|
| API key storage | AES-256-GCM encrypted with PBKDF2 (250,000 iterations) |
| Key derivation | Your passcode + random salt → encryption key |
| What leaves your device | Only your prompt, sent directly to `api.anthropic.com` over HTTPS |
| Server involvement | None. This is a static HTML file. |
| Passcode verification | SHA-256 hash stored locally, never transmitted |
| If someone steals your device | Without your passcode, the encrypted key is unreadable |

Your API key is **never** sent to GitHub, any proxy, or any third party. The only outbound connection is from your browser directly to `api.anthropic.com`.

**Content Security Policy** is set in the HTML to block any other outbound connections.

---

## Usage & cost

Each briefing call uses ~3,000–4,000 tokens. At current Anthropic pricing (~$0.003/1K tokens input, $0.015/1K output), each briefing costs roughly **$0.01–0.03 AUD**.

$5 of API credit = ~200–500 daily briefings.

---

## Refresh

Hit the **↻ Refresh** button in the top bar at any time to generate a new briefing without reloading the page.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| "API error 401" | API key is wrong or expired — re-enter it |
| "API error 429" | Rate limited — wait 60 seconds and retry |
| "API error 402" | No credit — top up at console.anthropic.com |
| Blank page | Check browser console for errors |
| Forgot passcode | Click "Sign out", re-enter API key and a new passcode |
