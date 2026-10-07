# 🚀 Ghousia's Portfolio - Deployment & Hosting Guide

This guide outlines step-by-step instructions to deploy your pixel-art software engineering portfolio to **GitHub Pages**, **Vercel**, and **Netlify**.

---

## 📁 Project Directory Structure

```text
ghousia's_portfolio/
├── index.html                           # Main HTML structure, styles, and logic
├── avatar.jpg                           # Pixel avatar portrait
├── Gemini_Generated_Image_81apgc81apgc81ap.png # Retro hero background graphic
├── project1.jpg                         # Cyber Arcade Engine thumbnail
├── project2.jpg                         # Core Telemetry Matrix thumbnail
├── project3.jpg                         # Echo Flow AI Agent thumbnail
├── README.md                            # Portfolio documentation
└── DEPLOYMENT.md                        # Deployment instructions
```

---

## Option 1: Deploy to GitHub Pages (Free & Recommended)

GitHub Pages provides zero-configuration static site hosting directly from your repository.

### Step 1: Initialize Git and Commit
Open PowerShell or your terminal inside this folder (`c:\Users\admin\Desktop\ghousia's_portfolio`):

```bash
# 1. Initialize a new Git repository
git init

# 2. Add all portfolio files
git add .

# 3. Create your initial commit
git commit -m "feat: initial release of pixel art portfolio"
```

### Step 2: Push to GitHub
1. Go to [GitHub.com](https://github.com) and click **New Repository**.
2. Name your repository (e.g., `portfolio` or `<your-username>.github.io`).
3. Set the repository to **Public**.
4. Link and push your local code:

```bash
# Replace with your GitHub repository URL
git remote add origin https://github.com/<your-username>/portfolio.git
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Navigate to your repository on GitHub.
2. Click **Settings** > **Pages** (in the left sidebar).
3. Under **Build and deployment**:
   - **Source**: `Deploy from a branch`
   - **Branch**: Select `main` and `/ (root)`
4. Click **Save**.
5. Your website will be live in ~60 seconds at:  
   `https://<your-username>.github.io/portfolio/` (or `https://<your-username>.github.io` if named after your username).

---

## Option 2: Deploy to Vercel (Instant Deploy & Custom Domains)

1. Sign up or log in to [Vercel.com](https://vercel.com).
2. Click **Add New...** > **Project**.
3. Import your GitHub repository.
4. Keep the default settings (Framework Preset: *Other*, Root Directory: `./`).
5. Click **Deploy**.
6. Vercel will provide an instantaneous production URL with free SSL (e.g. `ghousia-portfolio.vercel.app`).

---

## Option 3: Deploy to Netlify (Drag & Drop or Git)

### Method A: Git Integration
1. Log in to [Netlify.com](https://www.netlify.com).
2. Click **Add new site** > **Import an existing project**.
3. Select GitHub and pick your repository.
4. Click **Deploy portfolio**.

### Method B: Instant Drag & Drop
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag and drop the entire `ghousia's_portfolio` folder onto the browser window.
3. Your site will immediately go live with a custom Netlify URL.

---

## 🔧 Post-Deployment Configurations

### 1. Connecting a Real Email Service (Resend / Formspree)
To receive actual emails from your contact form:
- Sign up at [Resend.com](https://resend.com) or [Formspree.io](https://formspree.io).
- If using Formspree, update the form tag in `index.html`:
  ```html
  <form id="portfolio-contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  ```

### 2. Connecting Real OpenAI / Gemini API in Chat
To enable live AI responses in the companion chat:
- Deploy a lightweight serverless edge function (e.g., via Vercel Edge API or Cloudflare Workers) that calls `https://api.openai.com/v1/chat/completions` with your API key stored securely in environment variables.

---

## ✅ Quality & Compatibility Checklist
- [x] **Theme Switcher**: Detects default OS dark/light mode with CSS media queries + manual toggle.
- [x] **Responsive Layout**: Tested across desktop, tablet, and mobile with slide-out sidebar drawer.
- [x] **SEO & Metadata**: Title, author, meta description, and semantic HTML5 hierarchy.
- [x] **Accessibility (a11y)**: ARIA labels on all interactive controls, buttons, modals, and social links.
- [x] **Asset Optimization**: Local assets with pixel rendering and fallback styling.
