## 🎯 Project Overview

This is a production-ready React SPA leveraging:

- **Vite** for blazing-fast development and optimized builds
- **TypeScript** for type safety and developer experience
- **Zephyr Cloud** for zero-config deployment and CDN distribution
- **vite-plugin-zephyr** for seamless CI/CD integration

## 🏗️ Architecture

### Build Pipeline

```
Source Code → TypeScript Compilation → Vite Build → Zephyr Plugin → CDN Deploy
```

The project uses a **build-time deployment strategy** where `npm run build` triggers:

1. TypeScript compilation (`tsc -b`)
2. Vite production build (tree-shaking, code-splitting, minification)
3. Zephyr plugin activation (manifest generation + asset upload)
4. Automatic deployment to global edge network

### Key Technical Decisions

**Why Vite?**

- Native ES modules for instant HMR
- Rollup-based production builds for optimal bundling
- Plugin ecosystem for extensibility

**Why Zephyr Cloud?**

- Git-native deployment (no separate CI/CD needed)
- Automatic versioning per commit
- Instant rollbacks via Chrome extension
- Zero infrastructure management

**TypeScript Integration:**

- Strict mode enabled for maximum type safety
- Path aliases support via `tsconfig.app.json`
- Separate config for Node.js tooling (`tsconfig.node.json`)

## 🚀 Quick Start

### Development

```bash
npm run dev    # Starts dev server at http://localhost:5173
```

### Production Build + Deploy

```bash
npm run build  # Compiles + Builds + Deploys to Zephyr Cloud
```

### Preview Build Locally

```bash
npm run preview  # Serves production build at http://localhost:4173
```

## 🔄 Deployment Workflow

### Initial Setup

```bash
# 1. Connect GitHub repository
git remote add origin git@github.com:USERNAME/REPO.git
git push -u origin main

# 2. First deployment (triggers browser login)
npm run build
# → Zephyr authentication flow
# → Automated deployment
# → Live URL: https://your-app-ze.zephyrcloud.app
```

### Continuous Deployment

```bash
# Make changes → Commit → Deploy
git add .
git commit -m "feat: new feature"
npm run build  # Auto-deploys new version
```

link preview: https://eduardo-mota-81-react-vite-ts-challenge-em-eduard-e0bdc63d3-ze.zephyrcloud.app/
