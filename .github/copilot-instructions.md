# Copilot Instructions for LDB.AI (Liga de Boxeo)

## Project Overview

This is the **Liga de Boxeo (LDB.AI)** website, a Next.js-based platform for a boxing league. The project emphasizes:

- Production-grade code with no placeholders
- Brand consistency with dark/gold color scheme
- Full AI automation and health verification
- Responsive design across all devices

## Tech Stack

- **Framework:** Next.js 14 with App Router
- **Language:** TypeScript (strict mode)
- **Styling:** Tailwind CSS + Framer Motion
- **UI Components:** Shadcn/UI + Lucide React Icons
- **Hosting:** Vercel (auto-deploy from GitHub)
- **Package Manager:** npm

## Code Style & Conventions

### TypeScript
- Use TypeScript for all new files
- Enable strict type checking
- Prefer interfaces over types for object shapes
- Use proper typing for React components (FC, ReactNode, etc.)

### React & Next.js
- Use functional components with hooks
- Follow Next.js 14 App Router conventions
- Place pages in `src/pages/` or `app/` directory
- Use server components by default, client components when needed
- Import from `next/image` for images, `next/link` for navigation

### Styling
- Use Tailwind CSS utility classes
- Follow the brand color scheme:
  - Primary gold: `#DAA520`
  - Background blacks: `#000`, `#0A0A0A`
  - Dark gradients for backgrounds
- Ensure full responsive design (mobile-first approach)
- Use Framer Motion for animations

### Components
- Create reusable components in `src/components/`
- Use clear, descriptive component names
- Keep components focused and single-purpose
- Export components as named exports

## Build & Development

### Setup
```bash
npm install
npm run dev
```

### Build Commands
- **Development:** `npm run dev` - Starts dev server on port 3000
- **Build:** `npm run build` - Creates production build
- **Start:** `npm start` - Runs production server
- **Lint:** `npm run lint` - Runs ESLint

### Testing
- All code must build successfully with `npm run build`
- Health endpoints must return 200 status
- Verify responsive design on multiple screen sizes

## Health Verification

The project includes health check endpoints:

- **`/api/health`** - Returns JSON with service health status
- **`/api/health/badge`** - Generates dynamic CI badge

Expected response format:
```json
{
  "status": "healthy",
  "uptime": "99.99%",
  "response_time": "58ms"
}
```

## CI/CD & Deployment

### GitHub Actions Workflows
The project uses three main workflows (to be created in `.github/workflows/`):

1. **`health-check.yml`** - Runs on PRs and commits to main/dev
   - Builds project
   - Runs linters
   - Checks health endpoints

2. **`preview.yml`** - Deploys to Vercel preview environment
   - Triggered on PR creation
   - Adds deployment preview URL

3. **`production.yml`** - Promotes to production
   - Triggered on merge to main
   - Tags releases with build ID

### Deployment Process
1. Commit to `dev` branch
2. CI runs health checks
3. On success, preview deploys to Vercel
4. Merge to `main` promotes to production

## Asset Management

### File Organization
- **Logos:** `/public/brand/logo.png` (transparent PNG)
- **Wallpapers:** `/public/wallpaper.jpg` (dark gradient, boxing theme)
- **Icons:** Use Lucide React for UI icons
- **Fonts:** System fonts or web fonts via Next.js font optimization

### Asset Guidelines
- Use optimized images (WebP when possible)
- Use Next.js Image component for automatic optimization
- Maintain brand consistency in all visual assets
- No blocking or obstructive foreground elements

## Important Rules

1. **No Placeholders:** All code, assets, and content must be production-ready
2. **Brand Alignment:** Stick to the dark/gold color scheme
3. **Responsive First:** All UI must work on mobile, tablet, and desktop
4. **Type Safety:** Maintain strict TypeScript typing
5. **Performance:** Optimize images, use lazy loading, minimize bundle size
6. **Accessibility:** Follow WCAG guidelines, use semantic HTML

## File Structure

```
root/
├── .github/
│   ├── workflows/          # CI/CD workflows
│   └── copilot-instructions.md
├── public/
│   ├── brand/             # Logos and brand assets
│   └── wallpaper.jpg      # Hero backgrounds
├── src/
│   ├── components/        # Reusable UI components
│   ├── pages/            # Page components
│   └── utils/            # Helper functions
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── README.md
```

## Future Features

When implementing new features, consider:
- YouTube API integration for fight videos
- AI-driven fighter roster with stats
- Interactive training camp widgets
- Partner data API for events
- Real-time fight updates

## Questions & Clarifications

If uncertain about:
- **Styling:** Refer to existing components and Tailwind config
- **Routing:** Check Next.js 14 App Router documentation
- **Components:** Review existing components in `src/components/`
- **Build issues:** Check `package.json` scripts and dependencies

## Credits

- **Architect:** Eddie Barberiz Jr.
- **AI Engineers:** Claude Sonnet 4, GPT-5
- **Hosting:** Vercel
