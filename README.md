# Hannibál HSE — Website

Replacement site for hannibalhse.com, migrated from Wix to Cloudflare Pages.

---

## Phase 1 Setup Instructions

Follow these steps in order. Each step is a one-time action.

---

### Step 1 — Create a GitHub account (if you don't have one)

1. Go to https://github.com
2. Click **Sign up** and create a free account
3. Suggested username: `hannibalhse` or similar

---

### Step 2 — Create the GitHub repository

1. Log in to GitHub
2. Click the **+** icon (top right) → **New repository**
3. Repository name: `hannibalhse-website`
4. Set visibility to **Public** (required for free Cloudflare Pages deployment)
5. Do NOT initialise with a README (the files are already prepared)
6. Click **Create repository**

---

### Step 3 — Upload the site files to GitHub

Option A — via GitHub web interface (simplest):
1. In the new empty repository, click **uploading an existing file**
2. Drag and drop all the files and folders from this project
3. Scroll down, add a commit message: `Initial site structure — Phase 1`
4. Click **Commit changes**

Option B — via Git command line:
```bash
cd path/to/hannibalhse
git init
git add .
git commit -m "Initial site structure — Phase 1"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/hannibalhse-website.git
git push -u origin main
```

---

### Step 4 — Create a Cloudflare account

1. Go to https://cloudflare.com
2. Click **Sign up** → create a free account
3. You do not need to add a domain or payment method at this stage

---

### Step 5 — Connect GitHub to Cloudflare Pages

1. In the Cloudflare dashboard, go to **Workers & Pages** (left sidebar)
2. Click **Create** → **Pages** → **Connect to Git**
3. Authorise Cloudflare to access your GitHub account
4. Select the `hannibalhse-website` repository
5. Click **Begin setup**

---

### Step 6 — Configure the build settings

On the configuration screen:
- **Project name:** `hannibalhse`
- **Production branch:** `main`
- **Framework preset:** None (leave blank — this is plain HTML)
- **Build command:** leave empty
- **Build output directory:** leave empty (or enter `/`)
- Click **Save and Deploy**

---

### Step 7 — Verify the temporary URL

After deployment (~30 seconds):
1. Cloudflare will show a URL like `https://hannibalhse.pages.dev`
2. Open it in a browser
3. You should see the Hannibál HSE homepage

This is the URL to use for all testing and stakeholder review throughout Phases 2–6.
The Wix site remains completely untouched at this point.

---

### Step 8 — Add images (Phase 2 prerequisite)

Before the full site can be built, the following images must be downloaded from the
live Wix site and placed in `/assets/images/`:

| Filename to save as          | Source URL (Wix CDN)                                                        |
|------------------------------|-----------------------------------------------------------------------------|
| `banner-header.jpg`          | https://static.wixstatic.com/media/93cdd4_2c1cab71f0064a36815a8f0797cf8cd4~mv2.jpg |
| `banner-header-2.jpg`        | https://static.wixstatic.com/media/93cdd4_fc3a3ddb55d243d6bb096a19d4598bd8~mv2.jpg |
| `logo.jpg`                   | https://static.wixstatic.com/media/93cdd4_e02d2d87ab6446c1a3a2a9903e2f428a~mv2.jpg |

A full image inventory will be provided as part of Phase 2 deliverables.

---

## Repository Structure

```
hannibalhse-website/
├── index.html                        ← Homepage (/)
├── assets/
│   ├── css/
│   │   └── style.css                 ← Shared stylesheet for all pages
│   └── images/                       ← All site images (to be populated)
├── tev%C3%A9kenys%C3%A9gek/
│   └── index.html                    ← /tevékenységek/
├── sziklam%C3%A1sz%C3%A1s/
│   └── index.html                    ← /sziklamászás/
├── t%C3%BAras%C3%AD/
│   └── index.html                    ← /túrasí/
├── fut%C3%A1s-terepfut%C3%A1s/
│   └── index.html                    ← /futás-terepfutás/
├── copy-of-sziklam%C3%A1sz%C3%A1s/
│   └── index.html                    ← /copy-of-sziklamászás/
├── tags%C3%A1g/
│   └── index.html                    ← /tagság/
├── tagoknak/
│   └── index.html                    ← /tagoknak/
├── csatlakozn%C3%A9k/
│   └── index.html                    ← /csatlakoznék/
├── blog/
│   └── index.html                    ← /blog/ (post index)
├── post/
│   └── [slug]/index.html             ← /post/[post-title]/ (individual posts)
├── admin/                            ← /admin/ (landing page for admin section)
│   └── index.html
├── egyes%C3%BCleti-adatok/
│   └── index.html                    ← /egyesületi-adatok/
├── alapszab%C3%A1ly/
│   └── index.html                    ← /alapszabály/
├── adatkezel%C3%A9s/
│   └── index.html                    ← /adatkezelés/
├── robots.txt                        ← Enables Google indexing
├── sitemap.xml                       ← All 13 pages listed for Google
└── _redirects                        ← Cloudflare Pages redirect rules
```

---

## Making changes after launch

### Updating page content
Edit the relevant `.html` file in GitHub (click the file → pencil icon → edit → commit).
Changes go live within ~30 seconds.

### Publishing a new blog post
Blog posts are managed via Decap CMS (configured in Phase 4).
Authors log in at `https://www.hannibalhse.com/admin/` with their GitHub account.

---

## Contact / Maintainer

Hannibál Hegyisport Egyesület  
hannibalhse.com
