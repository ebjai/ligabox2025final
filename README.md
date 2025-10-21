# Liga de Boxeo 2025 Final (LDB.AI)

## Current Status

**⚠️ Project Planning Phase**

This repository is currently in the planning and documentation phase. The README below outlines the intended architecture and deployment strategy for the Liga de Boxeo (LDB.AI) website.

**What exists now:**
- Project documentation and technical specifications
- Planned architecture and build process

**What's coming:**
- Next.js 14 application implementation
- Component development
- CI/CD pipeline setup
- Vercel deployment configuration

---

## Overview

This document outlines the **complete system build and deployment process** for the **Liga de Boxeo (LDB.AI)** website. It ensures consistency across design, development, health verification, continuous integration (CI), preview, and production promotion.

---

## 🔧 Tech Stack

* **Framework:** Next.js 14 + TypeScript
* **UI:** Tailwind CSS + Framer Motion + Shadcn/UI + Lucide React Icons
* **Hosting:** Vercel (auto-deploys via GitHub CI)
* **Automation:** Claude Sonnet 4 (Claude.ai + VS Code Copilot integration)
* **Version Control:** GitHub main + dev branches
* **Assets:** Stored in `/public/` for logos, wallpapers, and metadata
* **CI/CD:** GitHub Actions — continuous integration & deployment pipelines
* **Monitoring:** Health endpoint `/api/health` + badge `/api/health/badge`

---

## 🧱 Planned Folder Structure

The following structure will be implemented once development begins:

```
root/
├── .github/workflows/
│   ├── health-check.yml           # Runs tests and health verification
│   ├── preview.yml                # Deploys preview branch to Vercel
│   ├── production.yml             # Promotes verified build to production
├── public/
│   ├── brand/logo.png             # Main logo
│   ├── wallpaper.jpg              # Hero wallpaper background
├── src/
│   ├── components/                # Reusable UI components (Brand, Hero, etc.)
│   ├── pages/                     # Route pages
│   │   ├── Home2035.tsx           # Main landing page with hero + AI bar
│   └── utils/                     # Helper scripts and constants
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── README.md (this file)
```

---

## ⚙️ Planned Build Workflow

### 1. **Initial Project Setup** (To Be Implemented)

Once the project is initialized, the following steps will be used:

* Clone repository and install dependencies:

  ```bash
  git clone https://github.com/ebjai/ligabox2025final
  cd ligabox2025final
  npm install
  ```
* Run local development server:

  ```bash
  npm run dev
  ```

  The app will be available at **[http://localhost:3000](http://localhost:3000)**

### 2. **Development Approach**

The project will be built using modern best practices:

* Full Next.js + Tailwind configuration
* Component-based architecture (Hero, AI widgets, Brand, etc.)
* Style composition (dark gradient backgrounds, typography, responsiveness)
* CI/CD and health test scaffolding

> All implementations will use production-ready code with no placeholders.

---

## 🧠 Planned Hero Section Structure

The hero layout will represent the front-facing entry of the LDB.AI site:

* **Top Section:** Logo + slogan + CTA buttons
* **AI Widget Bar:** AI-driven search and data interface
* **Visual:** Wallpaper background (dark gold hue aligned with LDB brand)

Design Requirements:

* No blocking ropes or unnecessary foregrounds
* Dark tones matching logo gold (#DAA520) and background blacks (#000, #0A0A0A)
* Fully responsive (desktop, tablet, mobile)

---

## 🩺 Planned Health Verification

Health endpoints will ensure deployment integrity once implemented:

### `/api/health` (To Be Implemented)

Will return JSON response verifying uptime, response time, and status code.

### `/api/health/badge` (To Be Implemented)

Will generate dynamic badge for CI workflow.

Example planned response:

```json
{
  "status": "healthy",
  "uptime": "99.99%",
  "response_time": "58ms"
}
```

---

## 🔄 Planned Continuous Integration (CI)

GitHub Actions will automate verification and deployment once configured:

### `health-check.yml` (To Be Implemented)

* Will run on pull requests and commits to `main` or `dev`
* Check build + lint + unit tests
* Ping `/api/health` to verify service health
* Block promotion if any check fails

### `preview.yml` (To Be Implemented)

* Build and deploy to Vercel preview environment
* Add environment badge and commit reference

### `production.yml` (To Be Implemented)

* Promote verified build from preview → production after passing all checks
* Tag release with build ID and timestamp

---

## 🚀 Planned Deployment Process

Once the application is built, the deployment process will be:

1. Commit changes to `dev` branch
2. CI runs `health-check.yml`
3. On success, `preview.yml` triggers a Vercel preview deployment
4. Once verified, merge into `main`
5. `production.yml` promotes deployment to live domain

---

## 🧩 Planned Asset Management

Once implemented, assets will be organized as:

* **Logos:** `/public/brand/logo.png` (transparent background preferred)
* **Wallpaper:** `/public/wallpaper.jpg` (dark gradient, boxing ring perspective)
* **Favicon:** Auto-generated by Vercel from logo.png

File naming and format consistency will be maintained throughout development.

---

## 🧠 Development Guidelines

When development begins:

* Do **not** use placeholders for assets or text
* All hero components must use actual brand data
* Maintain responsive layout using Tailwind's grid/flex utilities
* Keep background effects subtle and brand-aligned
* All AI widgets should be real and functional (no mockups)

---

## 🔍 Implementation Checklist

Once development is complete, verify:

✅ Code builds without error on `npm run build`
✅ Health endpoint returns 200 and `status: healthy`
✅ CI badge displays success
✅ Preview deploy verified on Vercel
✅ Production domain updated

---

## 🧩 Future Integrations

* YouTube API for live fight video feeds
* AI-driven fighter roster with stats + rankings
* Interactive widgets for training camp insights
* Partner data API for event results and sponsorships

---

## 🧾 Credits

* **Architect:** Eddie Barberiz Jr.
* **AI Engineer:** Claude Sonnet 4 (Anthropic)
* **Collaborative AI:** GPT-5 (OpenAI)
* **Hosting:** Vercel
* **Version Control:** GitHub
* **Framework:** Next.js 14 + Tailwind CSS

---

## 🧭 Getting Started

This README serves as the planning and specification document for the Liga de Boxeo (LDB.AI) website project.

**Next Steps:**

1. Initialize Next.js 14 project with TypeScript
2. Set up Tailwind CSS and component libraries
3. Implement core components (Hero, Brand, AI widgets)
4. Configure CI/CD pipelines
5. Deploy to Vercel

**Project Status:** Documentation and Planning Phase

For questions or contributions, please refer to the repository issues and discussions.
