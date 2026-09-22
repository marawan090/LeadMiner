# DevMind // Git & Tech Lead Miner

A clean, single-page application (SPA) for engineering intelligence, GitHub public data extraction, and developer discovery.

## 🚀 Public Vercel Deployment

This application is built as a zero-dependency, zero-backend static Single Page Application. It deploys out-of-the-box on **Vercel**, **Cloudflare Pages**, or **Netlify** with zero build configuration.

### Deploying to Vercel in 60 Seconds:
1. Push this repository to GitHub / GitLab / Bitbucket.
2. In the [Vercel Dashboard](https://vercel.com/new), select **Import Project** and point to your repository.
3. Keep the default settings:
   - **Framework Preset**: Other
   - **Root Directory**: `./`
   - **Build Command**: *(leave empty)*
   - **Output Directory**: *(leave empty)*
4. Click **Deploy**. Vercel will immediately serve `index.html` on your production URL.

---

## ⚡ Public Rate Limit First & Graceful GitHub PAT Fallback

- **Works Out-of-the-Box**: No upfront configuration required. Users can start searching immediately using GitHub's unauthenticated public API (default limit: 60 requests/hr).
- **Graceful Interception**: If an unauthenticated search reaches GitHub's rate limit (`403 Forbidden` / `X-RateLimit-Remaining: 0`), the app gracefully prompts the user with an option to connect their free Personal Access Token (PAT).
- **Client-Side BYOK (Bring Your Own Key)**:
  - Entering a GitHub PAT unlocks **5,000 requests/hour**.
  - Tokens are stored **strictly inside the user's browser** (`localStorage` key `leadminer_gh_pat`).
  - Tokens are never logged or transmitted to any server or third party.
  - Users can clear/wipe their token anytime with one click.

---

## 🛠 Core Features
- **Targeted Lead Search**: Search engineers by title/role, location, tech stack, and follower count.
- **Deep Commit Mining**: Scans public events and commit author headers (`/events/public`) to extract author emails.
- **LinkedIn & Google X-Ray**: Direct LinkedIn detection and one-click Google X-Ray search fallback for pinpoint profile discovery.
- **Priority Tier Classification**: Automated classification into Tier A (CTO, VP, Head of), Tier B (Lead, Staff, Principal), and Tier C.
- **CSV Export**: Clean spreadsheet export with UTF-8 BOM encoding for seamless Arabic and international character support in Microsoft Excel.
